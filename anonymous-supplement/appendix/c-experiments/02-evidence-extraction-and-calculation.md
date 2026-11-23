# C.2. Example of $E_{k}$ Extraction and Calculation across Reasoning Steps

[Appendix contents](../../README.md) · [Appendix C contents](README.md)

## Case Overview and Extraction Mechanism

To illustrate the dynamic evolution of the candidate evidence set $E_{k}$ across reasoning steps, we present a representative sample involving complex multi-table reasoning from IR-TabQA:

- **Question:** *“Please calculate the total inventory quantity and the corresponding total inventory value for the traditional Chinese medicine with the generic name 'Sanqi Powder' across all time periods.”*
- **Tabular Context:** This query spans three separate inventory tables corresponding to time ranges of 180–360 days, 360 days or more, and a general inventory table.

### Extraction of Candidate Evidence States.

We extract candidate evidence $E_k$ from the normalized executable program. Each program is segmented by explicit step markers, and the $k$-th segment is aligned with the corresponding reasoning step. Before execution, all raw cells in the candidate tables are assigned unique cell IDs. During execution, the system parses the AST of the complete program and maintains a variable dependency graph, where each variable is associated with a provenance set indicating the raw cells that contribute to its current value.

For source-data refinement steps ($k\in\mathcal{S}^{src}$), the provenance set is updated according to the semantics of the operation. Reading a table assigns the variable to all cells in that table; selecting columns restricts the provenance to the selected columns; row filtering restricts it to the retained rows; cell localization maps the variable to the selected cell or cells. In multi-table operations, introducing a new table expands the current candidate evidence state, while subsequent filtering contracts it. Therefore, $E_k$ is defined as the raw-cell scope retained after executing the $k$-th source-data step.

For calculation refinement steps ($k\in\mathcal{S}^{cal}$), operations such as summation, averaging, ratio computation, comparison, and aggregation produce derived values rather than original table cells. These derived values are not added to $E_k$ as new evidence. Instead, their provenance is defined as the union of the raw-cell provenance of their input variables. Since such steps do not directly change the retained raw evidence scope, we set $E_k=E_{k-1}$ for evidence-reward computation, and verify the correctness of derived values through the final solution reward.

The ground-truth evidence set $G$ is annotated with $|G| = 11$ minimal raw cells: 3 rows $\times$ 3 columns (9 cells) from Table 1, and 1 row $\times$ 2 columns (2 cells) from Table 3. Table 2 contains no matching records and contributes zero to the final calculation, as verified by execution.

## Comparison of Three Typical Reasoning Trajectories

### Trajectory A (Table [12](#table-12)): Efficient Refinement Trajectory

The model loads all three tables at once and performs subsequent column and row filtering, efficiently reaching the minimal candidate set in 3 source-data steps.

### Table 12

Trajectory A Step-wise Dynamics

| Step ($k$) | Step Description | $E_k$ Scope | $\lvert E_k\rvert$ | $\lvert E_k \cap G\rvert$ | Coverage $C_k$ | Density $D_k$ | Info Gain $\Phi_k$ |
| ---: | --- | --- | ---: | ---: | ---: | ---: | ---: |
| 0 | Initial state | Empty set $\emptyset$ | 0 | 0 | 0.000 | 0.000 | – |
| 1 | Load three tables | All cells ($84\times 21 + 9\times 21 + 21\times 12$) | 2205 | 11 | 1.000 | 0.323 | +0.661 |
| 2 | Keep key columns | 3 cols each for Table 1 & 2, 2 cols for Table 3 | 321 | 11 | 1.000 | 0.430 | +0.054 |
| 3 | Filter “Sanqi Powder” | 3 rows in Table 1, 0 in Table 2, 1 in Table 3 | 11 | 11 | 1.000 | 1.000 | +0.285 |
| 4 | Summation calculation | Calculation step (does not update $E_k$) | 11 | 11 | 1.000 | 1.000 | 0 |
| 5 | Output answer | Output step (does not update $E_k$) | 11 | 11 | 1.000 | 1.000 | 0 |

### Trajectory B (Table [13](#table-13)): Progressive Multi-Step Trajectory

The model processes the first two tables before reading and filtering the third table. Although longer, the system accurately captures intermediate rewards.

### Table 13

Trajectory B Step-wise Dynamics

| Step ($k$) | Step Description | $E_k$ Scope | $\lvert E_k\rvert$ | $\lvert E_k \cap G\rvert$ | Coverage $C_k$ | Density $D_k$ | Info Gain $\Phi_k$ |
| ---: | --- | --- | ---: | ---: | ---: | ---: | ---: |
| 0 | Initial state | Empty set $\emptyset$ | 0 | 0 | 0.000 | 0.000 | – |
| 1 | Load first two tables | All cells in Table 1 & 2 ($84\times 21 + 9\times 21$) | 1953 | 9 | 0.818 | 0.304 | +0.533 |
| 2 | Retain key columns | 3 cols each for Table 1 & 2 | 279 | 9 | 0.818 | 0.409 | +0.043 |
| 3 | Filter “Sanqi Powder” | 3 rows in Table 1, 0 in Table 2 | 9 | 9 | 0.818 | 1.000 | +0.242 |
| 4 | Local calculation | Calculation step (does not update $E_k$) | 9 | 9 | 0.818 | 1.000 | 0 |
| 5 | Load third table | Identified 9 cells + All cells in Table 3 ($21\times 12$) | 261 | 11 | 1.000 | 0.446 | +0.091 |
| 6 | Retain key columns (T3) | Identified 9 cells + 2 cols for Table 3 ($21\times 2$) | 51 | 11 | 1.000 | 0.629 | +0.091 |
| 7 | Filter “Sanqi Powder” (T3) | Final 11 source cells | 11 | 11 | 1.000 | 1.000 | +0.186 |
| 8 | Aggregate final result | Calculation step (does not update $E_k$) | 11 | 11 | 1.000 | 1.000 | 0 |
| 9 | Output answer | Output step (does not update $E_k$) | 11 | 11 | 1.000 | 1.000 | 0 |

### Trajectory C (Table [14](#table-14)): Erroneous Truncation Trajectory

The model mistakenly drops necessary columns during Step 2, leading to missing support evidence.

### Table 14

Trajectory C Step-wise Dynamics

| Step ($k$) | Step Description | $E_k$ Scope | $\lvert E_k\rvert$ | $\lvert E_k \cap G\rvert$ | Coverage $C_k$ | Density $D_k$ | Info Gain $\Phi_k$ |
| ---: | --- | --- | ---: | ---: | ---: | ---: | ---: |
| 0 | Initial state | Empty set $\emptyset$ | 0 | 0 | 0.000 | 0.000 | – |
| 1 | Load three tables | All cells | 2205 | 11 | 1.000 | 0.323 | +0.661 |
| 2 | **Incorrect column filtering** | Drops quantity/amount cols, retains irrelevant ones | 321 | 0 | 0.000 | 0.000 | **-0.500** |
| 3 | Subsequent operations | Missing source cells; unrecoverable | – | – | – | – | Outcome Penalty |

We can draw the following three conclusions from the comparative analysis of the above three trajectories:

1. **Complementarity of Coverage and Density:** Loading new tables (e.g., Step 1 in Trajectory A, Step 5 in Trajectory B) primarily increases Coverage $C_{k}$, whereas column selection and row filtering (e.g., Steps 2 and 3 in Trajectory A) enhance Density $D_{k}$ by removing irrelevant context.

2. **Fair Reward for Valid Cross-Table Retrieval:** In Trajectory B (Step 5), loading the third table expands $|E_{k}|$ from 9 to 261, temporarily dropping density $D_{k}$ from 1.000 to 0.446. However, because this step recovers missing gold evidence ($C_{k}$ increases from $9/11$ to $11/11$), the formulation yields a positive gain ($\Phi_{5} = +0.091$), successfully avoiding penalization of valid cross-table retrieval.

3. **Immediate Penalty for Evidence Loss:** In Trajectory C, erroneously dropping required columns causes $C_{k}$ to collapse to 0, immediately incurring a negative step gain ($\Phi_{2} = -0.500$) despite the reduction in candidate space size.

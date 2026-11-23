# B.8. Details of Procedure for Gold Evidence Annotation

[Appendix contents](../../README.md) · [Appendix B contents](README.md)

To accurately quantify information refinement during tabular reasoning, we annotate the gold evidence set $G$ for all verified SFT samples in IR-TabQA. Each sample consists of four components: a question $q$, a candidate table set $\mathcal{T}$, a structured reasoning trace, an executable Python code unit $u$, and a verified final answer $a$. The goal of this annotation process is to determine the minimal set of raw table cells required to solve the question and support the final answer.

The annotation pipeline consists of three sequential stages:

1. **Non-Calculation Step Localization and Dependency Tracing:**
   Annotators first identify the source-data refinement steps ($k \in S^{\text{src}}$) within the Python code based on the structured reasoning trace, including table path selection, column selection, row filtering, and cell localization. Using syntactic and semantic dependencies within the code, we trace backward from the final answer variable to the raw table cells involved, yielding an initial candidate evidence set $G$.

2. **Backtracing Derived Intermediate Values:**
   For calculation refinement operations ($k \in S^{\text{cal}}$) such as summation, averaging, comparisons, and ratio evaluations, derived intermediate values themselves are excluded from $G$. Instead, the annotation system traces back through the computational logic to extract the underlying raw source cells upon which these input variables depend, incorporating them into $G$.

3. **Three-Dimensional Human Verification:**
   The initial candidate set $G$ undergoes rigorous verification by two independent annotators based on three key criteria:

   - **Necessity:** Every cell in $G$ must be essential for solving the question or supporting the final answer, ensuring all redundant cells are removed.
   - **Completeness:** $G$ must fully cover all source cells required for filtering conditions, cross-table joins, logical comparisons, and numerical calculations, leaving no necessary evidence omitted.
   - **Consistency:** $G$ must maintain absolute alignment with the final answer, code execution results, and the logical steps in the reasoning trace.

Disagreements between annotators are resolved by a senior adjudicator. Combining executable abstract syntax tree dependency tracing with expert human verification, this pipeline ensures high reliability and reproducibility of $G$, establishing a solid benchmark for calculating step-level information gain.

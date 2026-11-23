# B.10. Step Definitions in TableQA Reasoning

[Appendix contents](../../README.md) · [Appendix B contents](README.md)

To support step-wise analysis, we decompose a complete TableQA reasoning process into five core steps. Each step corresponds to a local reasoning function that progressively narrows the candidate space and moves the model closer to the final answer. Table [10](#table-10) summarizes the meaning of each step. In practice, a trajectory does not necessarily contain all steps, and intermediate steps may appear multiple times depending on the complexity of the question.

### Table 10

Definition of the five reasoning paradigms used in our step-wise TableQA reasoning trace.

| Paradigm | Description |
| --- | --- |
| Path Selection | Identify the relevant table or reasoning path for the current question. |
| Column Filtering | Select the columns relevant to the question semantics and subsequent reasoning. |
| Row Filtering | Filter rows by applying question-specific conditions and retaining only the rows that satisfy the constraints. |
| Operation Execution | Execute table operations over the selected rows and columns, such as aggregation, comparison, sorting, and counting. |
| Answer Generation | Produce the final answer based on the remaining evidence and the execution result. |

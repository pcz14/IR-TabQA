# B.2. Details of Table and Question Difficulty Classification Criteria

[Appendix contents](../../README.md) · [Appendix B contents](README.md)

We design three difficulty levels to obviously distinct both the questions and table structures, yielding nine different difficulty types in total.
Specifically, for question difficulty, as defined in Table [8](#table-8), we propose three prompt templates for each difficulty level (see Appendix [B.4](04-question-generation-prompts.md)) to generate question of each difficulty seperately.
For table structure difficulty, we propose three dimensions (multi-table, multi-sheet, complex headers) to two annotators for independent annotation, as shown in Table [9](#table-9).

### Table 8

Question difficulty levels.

| Difficulty | Defination |
| --- | --- |
| Easy | The question can be answered directly by retrieving values from the table without requiring any computation or filtering. |
| Medium | The question requires simple computation, filtering, or conditional matching, typically solvable with a single-step operation. |
| Hard | The question involves more than two steps of reasoning, complex calculations, or comprehensive analysis, potentially including multi-condition filtering, cross-table integration, and logical inference. |

### Table 9

Table structure difficulty levels. ✓ = Yes, ✗ = No, *any* = either Yes or No. Multi-Table are always considered hard.

| Multi-Table | Multi-Sheet | Complex Header | Difficulty |
| --- | --- | --- | --- |
| ✗ | ✗ | ✗ | Easy |
| ✗ | ✓ | ✗ | Medium |
| ✗ | ✗ | ✓ | Medium |
| ✗ | ✓ | ✓ | Hard |
| ✓ | any | any | Hard |

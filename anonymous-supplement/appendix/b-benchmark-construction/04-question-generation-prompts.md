# B.4. Prompts Library and Seed Questions for Question Generation

[Appendix contents](../../README.md) · [Appendix B contents](README.md)

## Easy Question Prompt

The three prompt templates in the prompt library for easy question generation are shown below:

`````text
You are a professional expert in question generation based on tabular data, with expertise in designing questions grounded in table content. Below are 3 seed questions related to a table, along with the table description. Based on the analytical complexity and the reasoning pattern of the seed questions, please generate 3 new questions. Make sure that each question can be answered based solely on the provided table. Please read the following carefully:

## Seed Questions:
[SEED QUESTION 1]
[SEED QUESTION 2]
[SEED QUESTION 3]


## Tabular Data:
[TABLE DESCRIPTION]

## Task Requirements:

Please refer to both the tabular data and the seed question to generate 3 new questions. Ensure that the generated questions meet the following criteria:
1.	Each question must be directly related to the provided tabular data and answerable based on that data.
2.	The questions should be simple, involving only one main subject and requiring just a single-step calculation or retrieval to answer.
3.	Each question must be semantically complete, clearly worded, and consistent with natural human expression.
4.	The questions should not be exact repetitions or too similar to the seed questions—ensure novelty and diversity in phrasing.
5.	The three questions must not be similar to each other; the questioning strategies should be flexible and varied.

## Output Format:

Question 1:...
Question 2:...
Question 3:...

Do not include any other content in the output.
`````

`````text
You are a domain expert in designing table-based questions for data comprehension and analysis. Provided below are 3 sample (seed) questions and a textual description of a data table. Your task is to create 3 new questions that align in reasoning level and format with the seed questions, while introducing novel content and structure.

## Seed Questions:
[SEED QUESTION 1]
[SEED QUESTION 2]
[SEED QUESTION 3]

## Table Description:
[TABLE DESCRIPTION]

## Instructions:

Use both the table context and the sample questions to inspire your generation. Ensure that the new questions follow these rules:
1.	Each question should rely strictly on the information present in the table description.
2.	Avoid multi-step reasoning—keep the logic shallow, using only one operation like filtering, lookup, or basic calculation.
3.	Ensure the questions are clear, natural, and precise in language, without ambiguity.
4.	The new questions should not simply restate or paraphrase the seed questions. Strive for originality in both content and style.
5.	The three questions should each focus on a different fact or angle from the table.

## Output Format:

Question 1:...
Question 2:...
Question 3:...

Only include the questions—do not provide any explanations or commentary.
`````

`````text
You are a skilled question generation expert specialized in tabular reasoning. Below are three reference questions and a corresponding table description. Your goal is to create 3 new and distinct questions inspired by the style and complexity of the reference items.

## Reference Questions:
[SEED QUESTION 1]
[SEED QUESTION 2]
[SEED QUESTION 3]

## Table Context:
[TABLE DESCRIPTION]

## Guidelines:

Use the reference questions and the table description to craft 3 original, answerable questions that meet the following criteria:
1.	Questions must be grounded solely in the table—no external knowledge should be required.
2.	Keep each question simple, focusing on direct retrieval or one-step aggregation.
3.	Language should be fluent, concise, and free of awkward constructions.
4.	Do not echo the seed questions in structure or focus—diversify your approach.
5.	Each question should target a different element, attribute, or data entry in the table.

## Output Format:

Question 1:...
Question 2:...
Question 3:...

Only output the questions. Do not add any headings, explanations, or formatting notes.
`````

The 5 Seed Questions are shown below:

`````text
Seed Question 1: What is the total amount of the in-station cable project?

Seed Question 2: What was the corporate income tax revenue in 2021?

Seed Question 3: What was Hu Lianjie’s score in the chemistry subject?

Seed Question 4: What was Shandong Province’s expenditure on agricultural support in 1980 (in ten thousand yuan)?

Seed Question 5: What was the industrial added value of the non-ferrous metal mining and dressing industry in 2006 (in 100 million yuan)?
`````

## Medium Question Prompt

The three prompt templates in the prompt library for medium question generation are shown below:

`````text
You are a professional expert in question generation based on tabular data, with expertise in designing questions grounded in table content. Below are 3 seed questions related to a table, along with the table description. Based on the analytical complexity and the reasoning pattern of the seed questions, please generate 3 new questions. Make sure that each question can be answered based solely on the provided table. Please read the following carefully:

## Seed Questions:
[SEED QUESTION 1]
[SEED QUESTION 2]
[SEED QUESTION 3]

## Tabular Data:
[TABLE DESCRIPTION]

## Task Requirements:

Please refer to both the tabular data and the seed questions to generate 3 new questions. Ensure that the generated questions meet the following criteria:
1.	Each question must be directly related to the provided tabular data and answerable based on that data.
2.	The difficulty level of the new questions should be comparable to that of the seed questions in terms of reasoning depth.
3.	Each question must be semantically complete, clearly worded, and consistent with natural human expression.
4.	The questions should not be exact repetitions or too similar to the seed questions—ensure novelty and diversity in phrasing.
5.	The three questions must not be similar to each other; the questioning strategies should be flexible and varied.

## Output Format:

Question 1:...
Question 2:...
Question 3:...

Do not include any other content in the output.
`````

`````text
You are a skilled question designer with deep experience in generating reasoning-based questions from tabular data. Below are 3 example seed questions along with a description of the table they are based on. Your goal is to craft 3 new questions that reflect the same level of reasoning complexity and use similar logic types. Each question must be fully grounded in the table and answerable without external knowledge.

## Seed Questions:
[SEED QUESTION 1]
[SEED QUESTION 2]
[SEED QUESTION 3]

## Table Description:
[TABLE DESCRIPTION]

## Guidelines:

Use the table description and the seed questions as references. The questions you generate should fulfill the following conditions:
1.	Each question must be clearly tied to the information in the table and solvable using the table alone.
2.	Maintain a medium reasoning level—such as involving one layer of condition, filtering, grouping, or a basic calculation.
3.	The wording of each question should be natural, specific, and unambiguous.
4.	Avoid closely mirroring the structure or content of the seed questions; introduce variety in phrasing and focus.
5.	The three questions should each highlight a different reasoning pattern or aspect of the data.

## Output Format:

Question 1:...
Question 2:...
Question 3:...

Only output the three questions—no extra explanation or commentary.
`````

`````text
You are a tabular data reasoning expert. Given the 3 seed questions and a description of a table, your task is to generate 3 new questions that demonstrate a similar level of analytical thinking. The questions should be based only on the data provided in the table and should encourage intermediate-level reasoning.

## Seed Questions:
[SEED QUESTION 1]
[SEED QUESTION 2]
[SEED QUESTION 3]

## Table Description:
[TABLE DESCRIPTION]

## Generation Criteria:

Create 3 new questions that meet all of the following criteria:
1.	All questions must be directly answerable from the data provided in the table.
2.	Aim for medium complexity—questions that may involve conditional selection, simple aggregation, or single-layer logic chains.
3.	Ensure natural phrasing and semantic completeness for each question.
4.	Do not repeat patterns from the seed questions; diversify the questioning angles.
5.	Each question should target a different aspect or relationship in the table to ensure coverage diversity.

## Output Format:

Question 1:...
Question 2:...
Question 3:...

Please return only the questions—exclude any analysis or notes.
`````

The 5 Seed Questions are shown below:

`````text
Seed Question 1: What is the total estimated duration of all ongoing projects?

Seed Question 2: What is the sum of earnings per share and net assets per share for Gree Electric?

Seed Question 3: How many projects have outstanding payments exceeding 10,000 yuan?

Seed Question 4:  What is the ratio of the current price-to-earnings (P/E) ratio to the price-to-book (P/B) ratio for Kweichow Moutai?

Seed Question 5:  In the 2017 early first batch undergraduate science admissions in Guangdong Province, which university had the highest minimum score among first-choice applicants?
`````

## Hard Question Prompt

The three prompt templates in the prompt library for hard question generation are shown below:

`````text
You are a professional expert in question generation based on tabular data, skilled in uncovering latent value from complex datasets and designing logically coherent, analytically rich question tasks. You will be provided with 3 seed questions and the corresponding table data. Please carefully read the following content:

## Seed Questions:
[SEED QUESTION 1]
[SEED QUESTION 2]
[SEED QUESTION 3]

## Tabular Data:
[TABLE DESCRIPTION]

## Task Requirements:

With reference to both the tabular data and the style of the seed questions, please generate 3 new questions. Ensure that each question meets the following criteria:
1.	Mathematical Reasoning: Aim to design questions that involve computations such as summation, averaging, difference, and ratio analysis.
2.	Sorting and Ranking: Include questions that require sorting or ranking by one or more dimensions, either ascending or descending.
3.	Horizontal and Vertical Reasoning: Create questions that focus not only on a single row or column, but also involve reasoning across multiple rows and columns.
4.	Data Mining Perspective: Design questions from angles such as extreme value comparison or proportion analysis, rather than simple data lookup.
5.	Logical Depth: Questions should reflect inferential reasoning, such as associating multiple variables or analyzing changes over time.
6. STEM-Oriented Complexity: The new question should be a science/math-type problem involving multi-step reasoning and calculation.
7.	Explicit Subject: Each question must have a clear subject, which should correspond to an element present in the tabular data.
8.	Computational Feasibility: Ensure that each question can be answered through Python-based tabular data processing. Avoid theoretical questions that cannot be answered through computation.


## Output Format:

Question 1:...
Question 2:...
Question 3:...

Do not include any other content in the output.
`````

`````text
You are a high-level expert in generating advanced analytical questions based on structured tabular data. You will be provided with 3 seed questions and a table description. Your task is to generate 3 new, computationally feasible questions that reflect similar reasoning complexity while offering novel perspectives.

## Seed Questions:
[SEED QUESTION 1]
[SEED QUESTION 2]
[SEED QUESTION 3]

## Table Description:
[TABLE DESCRIPTION]

## Question Design Criteria:

Each question you create must fulfill the following constraints:
1.	Involve multi-step analytical operations such as multi-attribute comparisons, derived metric calculations, or multi-column aggregations.
2.	Encourage reasoning across multiple dimensions—horizontal (row-based), vertical (column-based), or temporal (if applicable).
3.	Introduce complexity via ranking, conditional filtering, or chaining multiple logical steps.
4.	Explore relationships, changes, or patterns (e.g., growth rates, top/bottom contributors, proportional shifts).
5.	Ensure clarity in wording with a concrete subject tied to table attributes.
6.	Questions must be answerable purely via tabular operations (e.g., using pandas or SQL). No open-ended or subjective items.

## Output Format:

Question 1:...
Question 2:...
Question 3:...

Exclude any explanatory notes or extra content.
`````

`````text
You are a specialist in high-difficulty question generation from structured tables, with a focus on constructing multi-step, computation-driven analytical tasks. Given 3 example questions and a table description, generate 3 new, non-trivial questions that challenge logical reasoning and data synthesis.

## Seed Questions:
[SEED QUESTION 1]
[SEED QUESTION 2]
[SEED QUESTION 3]

## Tabular Context:
[TABLE DESCRIPTION]

## Instructions:

Please ensure each generated question satisfies the following conditions:
1.	Requires combining information across multiple rows/columns, potentially involving filtering, aggregation, ranking, or cross-variable comparison.
2.	Includes math-based reasoning such as growth computation, ratio inference, delta tracking, or trend evaluation.
3.	Reflects real-world data analysis challenges, such as identifying maximum-impact items or tracing category-wise contributions.
4.	The questions must contain a well-defined analytical focus and be executable in practice via common data processing tools.
5.	Each question should be distinct in logic path from both the seed questions and the other generated questions.

## Output Format:

Question 1:...
Question 2:...
Question 3:...

Return only the 3 questions. Do not add any explanation or metadata.
`````

The 5 Seed Questions are shown below:

`````text
Seed Question 1: In the 2015 pre-interview qualification review list for public institution recruitment in Dandong City, calculate the standard deviation of test scores for each position and identify the position with the greatest score fluctuation.

Seed Question 2: In 2023, first filter out cities with fewer than 2 million insured individuals, then identify the city with the highest share of cumulative balance relative to the provincial total.

Seed Question 3: Based on the table data, calculate the average difference between the designed and measured longitudinal elevation values for each stake location. Then rank the locations by this average difference in descending order and identify the location with the largest average discrepancy.

Seed Question 4: Sort the monthly outbound quantities in ascending order, then calculate the difference between the average outbound quantity of the last three months and that of the first three months.

Seed Question 5: Calculate the compound annual growth rate (CAGR) of the total import and export value of agricultural products in Shandong Province from 2010 to 2023, and compare it with the CAGR of general trade import and export value. Specifically, compute the total import and export values for both categories by year, then calculate and compare their CAGRs to determine which category grew faster.
`````

# B.5. Details of Procedure for Question Annotation

[Appendix contents](../../README.md) · [Appendix B contents](README.md)

We randomly assign each question to two annotators, whose selection criteria and qualifications are detailed in Section [B.3](03-annotation-team.md).

Each annotator assesses the quality of question candidate based on the following aspects: **a) scope compliance**: the question must be answerable using tabular data, without requiring any extraneous domain knowledge. Temporal and spatial references must be strictly confined within the boundaries of the dataset. **b) thematic focus**: the question should concentrate on a single analytical dimension to derive evidence-bound conclusions, rather than enabling the generation of multi-thematic reports across divergent analytical directions. **c) conceptual distinctiveness**: multiple questions derived from the same table must address non-overlapping thematic aspects with clearly differentiated analytical objectives. **d) structural and cognitive diversity**: across a set of questions for the same table, annotators must vary the linguistic phrasing and the logical operations required (e.g., comparison, aggregation, trend analysis, or extremum identification). Avoid repetitive sentence templates; each question should represent a distinct way of querying the data to ensure the model's robustness across diverse natural language inputs.

In cases where the evaluation results of the two annotators are inconsistent, the results will be handed over to a third annotator for the final judgment. Through this rigorous quality assurance procedure, we obtained 5,523 high-quality, comprehensive questions.

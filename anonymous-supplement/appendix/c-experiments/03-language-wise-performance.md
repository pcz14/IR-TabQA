# C.3. Language-wise Performance

[Appendix contents](../../README.md) · [Appendix C contents](README.md)

Table [15](#table-15) presents the language-wise results on IR-TabQA. Overall, reasoning models show clear advantages over non-reasoning models in both English and Chinese, highlighting the importance of explicit multi-step reasoning for TableQA. The performance gap between the two languages varies across models, suggesting that bilingual table reasoning remains non-trivial even for strong LLMs. Our method improves over the corresponding base models in both languages, with especially notable gains in Chinese, indicating that information-guided stage-aware training benefits cross-lingual reasoning robustness.

### Table 15

Language-wise performance on IR-TabQA. **Bold**/underlined fonts denote the best/second-best results, and results in purple indicate the best results among open-source LLMs.

| Model | English | Chinese |
| --- | ---: | ---: |
| ***No Reasoning Models*** |  |  |
| **Open-Source Models** |  |  |
| Qwen2.5-72B-Instruct [\[29\]](https://arxiv.org/abs/2412.15115) | 53.55 | 50.75 |
| Qwen3-8B (no-thinking) [\[46\]](https://arxiv.org/abs/2505.09388) | 43.23 | 39.35 |
| Qwen3-32B (no-thinking) [\[46\]](https://arxiv.org/abs/2505.09388) | 49.03 | 56.07 |
| Llama-3.3-70B-Instruct [\[9\]](https://arxiv.org/abs/2407.21783) | 38.10 | 37.48 |
| Telechat3-36B [\[12\]](https://arxiv.org/abs/2401.03804) | 53.51 | 49.42 |
| **Closed-Source Models** |  |  |
| GPT-4o [\[25\]](https://arxiv.org/abs/2410.21276) | 54.25 | 58.80 |
| **Table-Specific Models** |  |  |
| TableGPT2-7B [\[34\]](https://arxiv.org/abs/2411.02059) | 45.16 | 39.81 |
| TableLLM-7B [\[53\]](https://doi.org/10.18653/v1/2025.findings-acl.538) | 15.51 | 12.06 |
| TableLlama-7B [\[52\]](https://doi.org/10.18653/v1/2024.naacl-long.335) | 17.70 | 10.02 |
| ***Reasoning Models*** |  |  |
| **Open-Source Models** |  |  |
| QWQ-32B [\[30\]](https://qwenlm.github.io/blog/qwq-32b/) | 55.48 | 53.11 |
| Qwen3-8B (thinking) [\[46\]](https://arxiv.org/abs/2505.09388) | 43.23 | 54.63 |
| Qwen3-32B (thinking) [\[46\]](https://arxiv.org/abs/2505.09388) | 56.77 | 60.19 |
| DeepSeek-R1-Dist-Qwen-7B [\[11\]](https://doi.org/10.1038/s41586-025-09422-z) | 16.13 | 8.80 |
| DeepSeek-R1-Dist-Qwen-14B [\[11\]](https://doi.org/10.1038/s41586-025-09422-z) | 36.13 | 42.59 |
| DeepSeek-R1-Dist-Qwen-32B [\[11\]](https://doi.org/10.1038/s41586-025-09422-z) | 54.84 | 52.78 |
| Deepseek-R1 [\[11\]](https://doi.org/10.1038/s41586-025-09422-z) | 55.11 | 56.30 |
| **Closed-Source Models** |  |  |
| Doubao-1.5-thinking-pro | 59.50 | **68.06** |
| ***TabEIRL (ours)*** |  |  |
| Qwen3-8B-Think-SFT-TabEIRL | 67.32 ★ | 68.74 ★ |

★ indicates scores highlighted in purple in the LaTeX table.

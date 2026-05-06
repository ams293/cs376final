# CS 376 Project: Evaluating LLM Response Quality Across Typologically Diverse Languages
**By Anna St. Clair and Alayna Smith**

## Overview
This project investigates whether GPT-4o's response quality varies across typologically distinct languages. The same multiple-choice questions are posed in seven languages representing different grammatical word orders (SVO, SOV, VSO), and accuracy is compared across them.

## Languages Tested
| Language | Word Order |
|----------|------------|
| English  | SVO        |
| French   | SVO        |
| Japanese | SOV        |
| Korean   | SOV        |
| Bengali  | SOV        |
| Arabic   | VSO        |
| Swahili  | SVO        |

## Dataset
Questions are drawn from the [openai/MMMLU](https://huggingface.co/datasets/openai/MMMLU) dataset on Hugging Face — a multilingual version of MMLU where each language config contains the same questions in the same order, enabling fair cross-language comparison.

## Notebook Structure
| Section | Description |
|---------|-------------|
| 0 — Preamble & Imports | Install and import all dependencies |
| 1 — Configuration | Experiment parameters (languages, model, sample size) |
| 2 — Dataset Loading | Load and verify cross-language alignment |
| 3 — Tokenization Utilities | Compute token fertility and subword fragmentation metrics |
| 4 — Prompt Runner | Send prompts to GPT-4o and collect results |
| 4b — Failure Mode Analysis | Inspect questions where the model failed in one language but not another |
| 5 — Scoring & Confidence Intervals | Per-language accuracy with 95% CIs |
| 6 — Visualizations | Six charts saved to `figures/` |

## Outputs
- `results/` — per-language CSVs and a combined `all_results.csv`
- `figures/` — six PNG charts including accuracy by language, token fertility, and correlation plots

## Requirements
- Python 3.10+
- OpenAI API key (stored as `OPENAI_API_KEY` in Colab Secrets)
- Dependencies are auto-installed in Section 0: `openai`, `datasets`, `tiktoken`, `pandas`, `numpy`, `scipy`, `matplotlib`, `seaborn`

## Usage
1. Open the notebook in Google Colab
2. Add your `OPENAI_API_KEY` to Colab Secrets
3. Run all cells in order

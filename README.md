# Survey Insights Pipeline

An end-to-end workflow that turns a raw survey export into decision-ready insight: labelled summary tables, charts, segment comparisons, and a reporting workbook that circulates to people who never touch the code.

Built around one principle: **write a function per question type, not a code block per question.** Most surveys contain dozens of questions in only three shapes (single choice, multi-select, Likert matrix), so three small functions cover the whole instrument and any future survey with the same shapes.

## The two notebooks

**`01_descriptive_analysis.ipynb`** answers "what did people say?" It filters to completed responses, summarizes every question type with reusable functions, and exports all summary tables to a single timestamped Excel workbook.

**`02_segment_analysis.ipynb`** answers "does it depend who you ask?" It joins responses to an organization attribute table and compares priorities across size, remoteness, and region. In the real engagement this is based on, this step changed the recommendation: priorities that looked settled at the topline diverged meaningfully between rural and urban contexts, which meant the policy product needed differentiated options rather than a single answer.

## A note on the data

All data in this repository is **synthetic**, generated to demonstrate the workflow. It mirrors the structure of a real provider survey I analyzed professionally, but contains no real respondents, organizations, or results.

## Run it yourself

```bash
pip install -r requirements.txt
jupyter notebook 01_descriptive_analysis.ipynb
```

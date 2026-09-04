# Transformer-Based Sentiment Classification

MSc Data Science project comparing **fine-tuned, zero-shot and few-shot transformer approaches for three-class sentiment classification**.

The project evaluates BERT, BART and FLAN-T5 for classifying customer reviews as **negative, neutral or positive**, with particular attention to model performance, class imbalance, prompt sensitivity and failure modes.

---

## Project Overview

Transformer models can be applied to text classification in several different ways, ranging from traditional supervised fine-tuning to zero-shot and prompt-based approaches.

This project compares three strategies:

- **BERT-tiny** – supervised fine-tuning;
- **BART-MNLI** – zero-shot classification; and
- **FLAN-T5** – few-shot prompt-based classification.

The aim was not only to identify the strongest performing approach, but also to investigate how the different modelling strategies behaved across sentiment classes.

---

## Approaches Evaluated

### BERT-tiny

BERT-tiny was fine-tuned directly on the labelled sentiment dataset.

The analysis included:

- tokenisation and preprocessing;
- supervised fine-tuning;
- training and validation monitoring;
- class-level performance evaluation; and
- threshold tuning.

### BART-MNLI

BART-MNLI was evaluated as a **zero-shot classifier**, allowing sentiment labels to be predicted without task-specific fine-tuning.

This provided a comparison between a pre-trained natural language inference model and the supervised BERT approach.

### FLAN-T5

FLAN-T5 was evaluated using a **few-shot prompting strategy**.

Example classifications were supplied within the prompt before the model was asked to classify unseen reviews.

Additional experiments investigated whether changes to the prompt and class labels affected model behaviour.

---

## Evaluation

The models were evaluated using:

- Accuracy
- Weighted F1-score
- Macro F1-score
- Per-class precision, recall and F1-score
- Confusion matrices
- Bootstrap confidence intervals
- Threshold analysis
- Prompt-sensitivity analysis

Macro F1 was particularly useful because the sentiment classes were not equally represented and performance on the minority classes was important.

---

## Results

| Model / Approach | Accuracy | Weighted F1 | Macro F1 |
|---|---:|---:|---:|
| BERT-tiny | 0.7998 | 0.8260 | 0.7104 |
| BERT-tiny with threshold tuning | 0.8334 | 0.8428 | 0.7217 |
| **BART-MNLI zero-shot** | **0.8688** | **0.8676** | **0.7311** |
| FLAN-T5 few-shot | 0.8306 | 0.7917 | 0.5635 |

### Key Findings

- **BART-MNLI achieved the strongest overall performance** despite being used without task-specific fine-tuning.
- Threshold tuning improved BERT-tiny performance compared with the original classification threshold.
- FLAN-T5 achieved relatively strong overall accuracy but substantially lower Macro F1.
- The FLAN-T5 few-shot approach failed to predict the **neutral class**, highlighting an important difference between overall accuracy and balanced class-level performance.
- Further prompt experiments were used to investigate whether this behaviour resulted from label wording or a broader tendency towards binary sentiment outputs.
- The comparison demonstrated that more extensive task-specific training does not automatically guarantee stronger performance than zero-shot transformer approaches.

---

## Error Analysis

A key part of the project involved examining where the models failed rather than relying only on overall performance metrics.

The FLAN-T5 results were particularly interesting because the model tended to produce positive or negative predictions while failing to identify neutral reviews.

This was investigated through additional prompt and label experiments to determine whether the behaviour could be improved through prompt design.

The results demonstrate the importance of examining:

- class-level performance;
- confusion matrices;
- minority-class behaviour; and
- prompt sensitivity

when evaluating transformer-based classifiers.

---

## Repository Structure

```text
transformer-sentiment-classification/
│
├── README.md
├── .gitignore
│
├── notebooks/
│   └── AI and Applied Machine Learning Task 2 Code.ipynb
│
└── AI and Applied Machine Learning Report.pdf
```

---

## Repository Contents

### `notebooks/`

**`AI and Applied Machine Learning Task 2 Code.ipynb`**

Contains the complete NLP analysis, including:

- data preparation;
- sentiment class exploration;
- BERT-tiny fine-tuning;
- threshold optimisation;
- BART-MNLI zero-shot classification;
- FLAN-T5 few-shot classification;
- prompt experiments;
- model evaluation;
- confusion matrices; and
- bootstrap analysis.

### Coursework Report

The accompanying **AI and Applied Machine Learning Report** contains the full academic write-up and interpretation of the experiments.

The report contains two coursework tasks. **Task 2 corresponds to the transformer-based sentiment classification project presented in this repository.**

---

## Technologies

### Programming Language

- Python

### Natural Language Processing

- Hugging Face Transformers
- BERT
- BART
- FLAN-T5
- Tokenisation
- Prompt engineering

### Machine Learning and Evaluation

- PyTorch
- Scikit-learn
- Pandas
- NumPy
- Accuracy
- F1-score
- Confusion matrices
- Bootstrap confidence intervals

---

## Skills Demonstrated

This project demonstrates experience in:

- Natural Language Processing;
- transformer models;
- supervised fine-tuning;
- zero-shot classification;
- few-shot learning;
- prompt engineering;
- multi-class classification;
- class imbalance analysis;
- model evaluation;
- error analysis;
- threshold optimisation;
- bootstrap analysis; and
- communicating comparative machine learning results.

---

## Academic Context

This repository contains work completed as part of an **MSc Data Science AI and Applied Machine Learning module**.

The repository has been included in my data science portfolio to demonstrate practical experience applying and evaluating modern transformer-based NLP approaches.

---

## Author

**Gabriella Davis**

MSc Data Science

GitHub: `gabriella-davis0505`

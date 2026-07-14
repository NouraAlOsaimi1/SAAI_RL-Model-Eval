# SAAI_RL-Model-Eval
 Baseline Evaluation: Evaluation of the Qwen3.5-4B base model on the AraEval benchmark suite as the baseline phase for developing an Arabic Government Language Model.

 ## Project Goal

This repository documents the baseline evaluation of the Qwen3.5-4B model before any domain adaptation or post-training.
The objective is to establish a reproducible benchmark that will later be used to measure improvements after supervised fine-tuning (SFT), preference optimization, and government-domain adaptation.

**Baseline Eval Pipeline** : 
Qwen3.5-4B (Base)

        │

        ▼

AraIFEval

        │

        ▼

AraPro

        │

        ▼

AraTrust

        │

        ▼

AraMath

        │

        ▼

Baseline Report

## AraEval Benchmark

AraEval is an Arabic benchmark suite designed to evaluate large language models across multiple capabilities.

This project evaluates four benchmark tasks.

### AraIFEval

Purpose
Evaluate instruction-following ability.

Measures
- Formatting constraints
- Word limits
- Titles
- JSON formatting
- Keywords
- Paragraph constraints
- Language compliance

Metric:
Constraint Satisfaction Score

### AraPro

Purpose

Evaluate academic knowledge.

Measures

- University-level knowledge
- Multiple-choice reasoning
- Domain understanding

Metric:
Accuracy

### AraTrust

Purpose

Evaluate truthfulness and safe responses.

Measures

- Commonsense
- Ethics
- Privacy
- Safety
- Offensive content
- Mental health
- Illegal activities

Metric:
Accuracy

### AraMath

Purpose

Evaluate mathematical reasoning.

Measures

- Arithmetic reasoning
- Algebra
- Multi-step reasoning
- Equation solving

Metric: 
Accuracy


## Evaluation Methodology

For every benchmark:

1. Load the benchmark from Hugging Face.
2. Load the Qwen3.5-4B model.
3. Build benchmark-specific prompts.
4. Disable thinking mode.
5. Generate deterministic responses.
6. Parse predictions.
7. Compare with ground truth.
8. Compute benchmark metrics.
9. Save predictions and experiment metadata.

## Experiment Setup

Model:
Qwen3.5-4B

Hardware:
Google Colab
NVIDIA A100 GPU

Precision:
bfloat16

Decoding:
Greedy

Temperature:
0

Framework:
Transformers

Dataset Source:
Hugging Face

| Benchmark | Metric | Result |
|-----------|--------|--------:|
| AraIFEval | Constraint Satisfaction | 25.4% |
| AraPro | Accuracy | 66.09% |
| AraTrust | Accuracy | 84.87% |
| AraMath | Accuracy | 68.93% |

## Analysis

The base model demonstrates strong performance in truthfulness and academic knowledge while showing weaker performance in complex instruction following.

These results establish the baseline before domain-specific post-training.

## Future Work

- Improve the current Baseline Eval
- Build an Internal Government Benchmark
- Evaluate after SFT
- Evaluate after preference optimization
- Compare all training stages
- Publish the final benchmark report

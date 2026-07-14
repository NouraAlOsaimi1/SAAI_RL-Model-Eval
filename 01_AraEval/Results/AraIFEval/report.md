# AraIFEval Evaluation Report

## Benchmark

AraIFEval evaluates instruction-following capabilities of Arabic Large Language Models.

Unlike traditional QA benchmarks, AraIFEval measures whether the model follows multiple constraints simultaneously rather than simply generating factually correct answers.

Examples of constraints include:

- word limits
- paragraph counts
- titles
- JSON formatting
- keyword frequency
- forbidden words
- highlighted sections
- ending phrases
- quotation formatting
- language constraints

---

# Model

Qwen/Qwen3.5-4B

---

# Dataset

humain-ai/AraIFEval

Split: train

Total samples: **536**

---

# Experiment Setup

| Parameter | Value |
|-----------|-------|
| Temperature | 0.0 |
| Sampling | False |
| Max New Tokens | 512 |
| Thinking Mode | Disabled |
| GPU | NVIDIA Tesla T4 |
| Torch dtype | bfloat16 |

---

# Baseline Statistics

| Metric | Value |
|--------|------:|
| Samples | 536 |
| Average Runtime | 16.711 sec |
| Average Word Count | 140.75 |
| Minimum Words | 98 |
| Maximum Words | 182 |

---

# Overall Constraint Score

**Overall Constraint Satisfaction Score**

0.254

---

# Constraint Results

| Constraint | Score |
|-------------------------------|------:|
| number_words_at_most | 0.674 |
| title | 0.816 |
| keyword_frequency | 0.138 |
| repeat_prompt | 0.231 |
| number_bullets | 0.365 |
| postscript | 0.426 |
| number_paragraphs | 0.020 |
| number_words_at_least | 0.128 |
| check_end | 0.167 |
| include_keywords | 0.135 |
| response_language | 0.112 |
| minimum_number_highlighted_section | 0.682 |
| number_sentences_at_least | 0.420 |
| forbidden_words | 0.517 |
| json_format | 0.833 |
| quotation | 0.425 |
| letter_frequency | 0.163 |
| number_placeholder | 0.429 |
| first_word_in_i-th_paragraph | 0.030 |
| multiple_sections | 0.225 |
| two_responses | 0.250 |
| number_sentences_at_most | 0.773 |
| no_commas | 0.200 |

---

# Observations

The model successfully generated fluent Arabic responses and generally respected high-level formatting instructions.

Strong performance was observed on:

- JSON formatting
- Title generation
- Maximum word constraints
- Sentence count limits

However, the model struggled with complex compositional constraints requiring precise control over the generated text.

Examples include:

- exact keyword frequency
- paragraph ordering
- first-word constraints
- language-specific formatting
- multiple simultaneous constraints

These weaknesses reduced the overall constraint satisfaction score.

---

# Example

Prompt:

> نشأة نظرية التقليد في تفسير السلوك الإجرامي...

Prediction:

The model generated a coherent Arabic article with an appropriate title and respected the maximum word limit.

However, it failed to satisfy the required keyword frequency constraint, demonstrating the difference between producing a high-quality answer and fully complying with all requested instructions.

---

# Conclusion

AraIFEval reveals that Qwen3.5-4B possesses strong Arabic generation capabilities but exhibits limitations in fine-grained instruction following.

The model performs well on structural constraints but struggles with strict compositional requirements involving multiple simultaneous conditions.

These findings establish a useful baseline for future post-training and instruction-tuning experiments.

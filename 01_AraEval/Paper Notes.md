AraEval: An Arabic Multi-Task Evaluation Suite for Large Language Models

1. Authors
Alhanoof Althnian, Norah A. Alzahrani, Shaykhah Z. Alsubaie, Eman Albilali, Ahmed Abdelali, Nouf M. Alotaibi, M Saiful Bari, Yazeed Alnumay, Abdulhamed Alothaimen, Maryam Saif, Shahad D. Alzaidi, Faisal Abdulrahman Mirza, Yousef Almushayqih, Mohammed Al Saleem, Ghadah Alabduljabbar, Abdulmohsen Al-Thubaity, Areeb Alowisheq, and Nora Al-Twairesh  
(Collaborative effort between HUMAIN, the Saudi Data and AI Authority (SDAIA), and King Saud University)

2. Year : 2025 (Presented at EMNLP 2025)

3. Main Goal
To introduce a native, comprehensive evaluation suite that rigorously measures the advanced cognitive and functional capabilities of foundation models—specifically focusing on knowledge retention, logical reasoning, truthfulness, and instruction-following within the Arabic language and cultural context.

4.Why was AraEval created?
Existing evaluation suites for Arabic LLMs heavily relied on translated English benchmarks (such as translated MMLU) or limited knowledge-based question answering datasets. These existing benchmarks suffered from:

Translation Artifacts: Awkward phrasing, unnatural syntax, and loss of cultural context.

Low Token Density/Coverage: Inadequate representation of native Arabic tokenization.

Narrow Evaluation Scope: Focus on simple factual recall rather than complex reasoning, instruction compliance, or safety/truthfulness.

AraEval was created from scratch to provide a native Arabic benchmark reflecting the linguistic, cultural, and normative nuances of Arabic-speaking communities.


5. What problem does it solve?
Language Disparity & Bias: Overcomes the heavy bias toward English and high-resource languages in LLM benchmarks.

Evaluation Reliability: Replaces translated benchmark noise with native, high-quality Arabic data.

Diagnostic Granularity: Solves the inability of simple accuracy metrics to pinpoint why a model fails (e.g., whether it struggles with logical inference, math, factual hallucination, or prompt structure).

6. Main Contributions
Large-Scale Native Dataset: Created 24,378 novel, native Arabic samples across multiple key evaluation dimensions.

Superior Token Density: Achieves significantly higher Arabic token coverage than legacy datasets like ArabicMMLU and translated MMLU suites.

Diagnostic Capability: Enables fine-grained error analysis to diagnose specific model weaknesses in reasoning, instruction compliance, and domain knowledge.

Cultural & Normative Alignment: Formulated tasks that reflect regional topics, Islamic context, Arab history, and localized commonsense scenarios.

7. Tasks Included
Linguistic Understanding & Knowledge: Factual recall across domain-specific subjects (science, history, literature, Islamic studies, domain expertise).

Reasoning Capabilities: Multi-step logical inference, commonsense reasoning, and mathematical problem-solving.

Truthfulness & Safety: Evaluation of model hallucinations, factual consistency, and normative/cultural alignment.

Instruction-Following: Measuring fine-grained compliance with multi-constraint user prompts written natively in Arabic.


8. Metrics Used
Standard Accuracy / Multiple-Choice Selection Metrics across structured task categories.

Exact Match (EM) and compliance scoring for instruction-following tasks.

Diagnostic Performance Profiles: Sub-domain task performance breakdown to measure model balance across capability dimensions.


9. How is the benchmark organized?
The benchmark is hierarchically structured into 4 core evaluation pillars:

Knowledge

Reasoning

Truthfulness

Instruction-Following

Each pillar is sub-divided into multi-task evaluation sets covering domain-specific subjects and task types.


10. How many datasets?
A unified suite composed of multi-task evaluation sets spanning the 4 major pillars and across diverse subject domains (science, history, religion, mathematics, logic, etc.).

11. How many samples?
24,378 novel samples in total.

12. Evaluation Methodology
Utilizes zero-shot and few-shot standardized prompting methodologies.

Evaluates model generation output against ground-truth native benchmarks using automated scoring pipelines and token-level evaluation wrappers.

13. Strengths
Natively Curated: Completely free from translation errors and western-centric bias.

High Token Coverage: Provides realistic token density for Arabic LLM tokenizers.

Comprehensive Dimensions: Moves beyond surface QA to test truthfulness, math, logic, and instruction compliance.

Robust Diagnostic Insights: Pinpoints model failure modes clearly.

**Standardized**

Allows fair comparison between different models.

14. Weaknesses
AraEval does not specifically evaluate:

Saudi government services.
Official Saudi regulations.
Administrative procedures.
Government document generation.
Ministry-specific terminology.

It measures general Arabic capabilities, not domain expertise.

Relation to Our Project?!
Our project starts from Qwen3.5-4B.

Before changing the model, we need to understand:

Can it reason well?
Can it follow Arabic instructions?
Does it hallucinate?
Does it understand Arabic text?
Is it a strong enough base model?

AraEval answers these questions.

However, it cannot tell us whether the model understands: 
Saudi government regulations.
Ministry workflows.
Government forms.
Citizen services.

That is why later stages require additional benchmarks.


So The Purpose here :
Baseline evaluation of Qwen3.5-4B before any continued pretraining, SFT, or alignment.

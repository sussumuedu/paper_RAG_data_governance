# paper_RAG_data_governance
Research artifacts for evaluating the impact of Retrieval-Augmented Generation on response quality in health data governance.

# Evaluating Retrieval-Augmented Generation for Health Data Governance

This repository contains research artifacts related to a comparative study evaluating the use of Retrieval-Augmented Generation (RAG) in the domain of health data governance.

The study investigates whether a RAG-based architecture improves the perceived quality of responses when compared with responses generated without retrieval support. The evaluation focuses on a specialized domain in which answers must be accurate, complete, contextually appropriate, useful, and clear for health data governance tasks.

## Study Overview

Large Language Models (LLMs) have shown potential for supporting information retrieval, synthesis, and interpretation in healthcare-related domains. However, their use in specialized and regulatory contexts remains challenging due to risks such as hallucination, incomplete contextualization, and limited alignment with domain-specific documents.

Retrieval-Augmented Generation (RAG) has been proposed as a strategy to mitigate these limitations by combining LLM generation with semantic retrieval from external document collections. In this study, we evaluate whether RAG adds practical value to responses related to health data governance.

## Objective

The objective of this study is to assess whether responses generated with RAG present higher perceived quality than responses generated without RAG in the context of health data governance.

## Study Design

The study follows a comparative evaluation design.

A set of 30 questions related to health data governance was created. For each question, two responses were generated:

- one response using Retrieval-Augmented Generation;
- one response without retrieval support.

This resulted in 60 responses organized into 30 comparable pairs.

The responses were evaluated under a double-blind design. Evaluators did not know whether each response had been generated with or without RAG. Within each pair, responses were randomized and presented as alternatives A and B.

## Evaluation

The evaluation involved three independent evaluators:

- two human experts with experience in health data governance;
- one automated evaluator following the LLM-as-a-judge paradigm.

Each response was assessed using five ordinal Likert-scale dimensions:

- Accuracy
- Completeness
- Adherence
- Utility
- Clarity

In addition, for each pair of responses, evaluators indicated a global preference among:

- WITH RAG
- WITHOUT RAG
- Tie

In total, the study produced:

- 900 ordinal judgments;
- 90 comparative preference judgments.

## Statistical Analysis

Ordinal quality scores were analyzed using cumulative link mixed models (CLMM), with one model fitted for each evaluation dimension. The models estimated the association between the experimental condition and higher Likert-scale ratings.

Global preference judgments were analyzed using a multinomial logistic model to compare preference patterns across evaluators.

The analysis considered both the direction and magnitude of estimated effects, as well as statistical uncertainty.


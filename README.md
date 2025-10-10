# CodeGenie AI Explainer and Code Generator
**Project Overview**

The CodeGenie AI Explainer and Code Generator project aims to build an intelligent system that can read, interpret, and generate explanations for source code using Natural Language Processing (NLP) and deep-learning techniques.In this first milestone, we design and implement a Code Explainer pipeline that processes code, extracts meaningful structure, and compares how different transformer-based models interpret code semantics.This forms the foundation for upcoming milestones, which will focus on generating human-like explanations and summaries for code.
**Objectives**
Build a code-understanding pipeline using Python and NLP models.
Parse Python code using Abstract Syntax Tree (AST) to extract structure.
Generate embeddings using MiniLM, DistilRoBERTa, and MPNet.
Compare embeddings to understand semantic differences between models.
Visualize results through plots and clustering graphs.
Document methodology and results in a clear, reproducible notebook.
**Approach & Methodology**

**Step 1 – Dataset Preparation**

Collected 10+ Python code snippets covering loops, functions, recursion, and classes.
Saved each snippet as a text block within the Colab notebook.

**Step 2 – Code Parsing**
Used Python’s built-in ast library to parse the code and extract:
Function definitions
Class declarations
Import statements
Control-flow patterns
This transforms raw code into a structured tree that represents code logic.

**Step 3 – Tokenization**
Tokenized each snippet using custom regex-based logic and nltk tools.
Converted code into standardized tokens for feeding into transformer models.

**Step 4 – Embedding Generation**
Passed the processed tokens into pretrained transformer models:
MiniLM-L6-v2
DistilRoBERTa-base
MPNet-base-v2
Extracted vector embeddings representing each code snippet’s semantic meaning.

**Step 5 – Model Comparison**
Calculated cosine similarity between embeddings of different snippets.
Observed which models yield higher similarity for logically identical functions.
Used PCA and t-SNE for dimensionality reduction.

**Step 6 – Visualization**
Plotted:
Embedding clusters
Similarity heatmaps
Model comparison graphs
Visualizations created with matplotlib, seaborn, and plotly.

**Step 7 – Interpretation**
Analyzed visual patterns:
MiniLM → efficient but slightly coarse clusters.
DistilRoBERTa → stronger contextual grouping.
**Goal of This Milestone**
This milestone lays the groundwork for:
Developing a code-to-text explanation system in Milestone 2.
Enabling semantic search across codebases.
Understanding how different transformer models perceive programming logic.
By completing Milestone 1, we have successfully:
Built a reproducible code-explainer pipeline.
Understood model behaviour on structured text.
Visualized and compared embeddings effectively.

MPNet → produced the most semantically coherent embeddings.

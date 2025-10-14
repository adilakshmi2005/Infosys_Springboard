# CodeGenie AI Explainer and Code Generator
# Milestone 1: Building the Code Explainer Pipeline
# Overview

The CodeGenie AI Explainer and Code Generator is an innovative project under the Infosys Springboard Internship Program.
It explores how Artificial Intelligence, particularly Natural Language Processing (NLP), can understand, explain, and represent code just like humans do.

This milestone marks the foundation of an AI-powered code understanding system.
We focused on designing a Code Explainer Pipeline that interprets source code through multiple NLP models, visualizes their understanding, and compares their semantic embeddings.

# Objective

“To make machines understand code — not just execute it.”
Milestone 1 focuses on:
Parsing and tokenizing Python code using AST (Abstract Syntax Tree).
Generating embeddings using pretrained NLP models:
MiniLM
DistilRoBERTa
MPNet
Comparing and visualizing model outputs.
Building a reusable, modular code analysis pipeline.

# Why This Project Matters

Traditional compilers execute code, but they don’t understand it.
In contrast, AI models like transformers can represent both syntax and semantics, enabling:

Automated code summarization
Bug detection and intent prediction
Smart AI code assistants (like GitHub Copilot)
This project lays the groundwork for the next generation of AI-driven code intelligence tools.

# Approach & Methodology

Step 1: Code Preparation

Collected 10 Python snippets representing various programming constructs:
Loops, Recursion, OOP, Data Structures, Exception Handling, etc.

Step 2: Code Parsing with AST

Used Python’s ast module to break down each code snippet.
Extracted functions, classes, imports, and control flow elements.
Visualized the internal structure using tree diagrams.

Step 3: Tokenization

Converted code into tokens using regex + nltk.
Cleaned and standardized identifiers for fair comparison.

Step 4: Embedding Generation

Processed tokenized snippets through three sentence-transformer models:

# Model	Description
MiniLM	Lightweight and efficient
DistilRoBERTa	Balanced performance
MPNet	Deep semantic understanding

Step 5: Model Comparison & Visualization

Used cosine similarity, PCA, and t-SNE for visual comparisons.
Created heatmaps and scatter plots to show how models interpret code similarity.

# Tools & Technologies

Category	Libraries
Parsing	ast, inspect, tokenize
Tokenization	nltk, re
Embeddings	sentence-transformers
Visualization	matplotlib, seaborn, plotly, PCA, t-SNE
Environment	Google Colab
Version Control	GitHub

# Conclusion

This milestone achieved its goal of building a functional, interpretable Code Explainer pipeline.
Through parsing, embedding, and visualization, we’ve proven that transformer-based NLP models can understand source code meaningfully —
laying a solid foundation for the next stage: AI-powered Code Generation and Explanation.

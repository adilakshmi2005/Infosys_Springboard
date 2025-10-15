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

---

# Model Visualizations and Insights

# MiniLM – Cosine Similarity Matrix
This heatmap shows the **pairwise cosine similarity** between the embeddings of different code snippets using the **MiniLM** model.

<img width="523" height="457" alt="image" src="https://github.com/user-attachments/assets/66f8de4b-7d39-43b0-b1d5-f33cce049e3f" />

# MiniLM – Embedding Visualization (PCA)
A **PCA projection** showing how MiniLM clusters similar code snippets in embedding space.

<img width="720" height="470" alt="image" src="https://github.com/user-attachments/assets/de6c5634-6a01-4a0f-a770-e9dcab70b3e3" />

# DistilRoBERTa – Embedding Visualization
DistilRoBERTa demonstrates stronger **semantic grouping**, clustering functionally similar snippets closer together.

<img width="798" height="470" alt="image" src="https://github.com/user-attachments/assets/4d2c7e46-ff90-424f-93ca-91a7051ac51e" />

# MPNet – Embedding Visualization
MPNet shows **deeper semantic understanding**, with distinct clusters for structurally and logically related snippets.

<img width="818" height="470" alt="image" src="https://github.com/user-attachments/assets/3cecc075-be4d-491a-9156-5739d3c060ea" />

# Model Embedding Correlation Comparison
This plot compares the **correlation between model embeddings**, showing how closely each model’s understanding aligns with others.

<img width="536" height="393" alt="image" src="https://github.com/user-attachments/assets/0c37b97c-6372-412a-af7f-62c45997d30b" />

# Clustering Similarity Between Models
A combined visualization comparing **clustering patterns** across all three models — MiniLM, DistilRoBERTa, and MPNet — indicating how similar their semantic grouping is.

<img width="536" height="393" alt="image" src="https://github.com/user-attachments/assets/85da3292-e769-4f09-b2ab-84d439b91014" />

# Conclusion

This milestone achieved its goal of building a functional, interpretable Code Explainer pipeline.
Through parsing, embedding, and visualization, we’ve proven that transformer-based NLP models can understand source code meaningfully —
laying a solid foundation for the next stage: AI-powered Code Generation and Explanation.


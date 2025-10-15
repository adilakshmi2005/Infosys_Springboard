# CodeGenie-AI-Explainer-and-Code-Generator
# Milestone 2 – AI Code Generator with Interactive UI and Visualizations

# Abstract
In the world of modern software development, Artificial Intelligence is redefining how programmers write and understand code.
This milestone of the CodeGenie Project focuses on building an AI-powered system capable of automatically generating Python code from natural language prompts.
By integrating multiple pretrained models from Hugging Face, this project not only generates functional code but also evaluates its quality, maintainability, and complexity, providing clear visual comparisons and interactive exploration.

# Objective
The primary aim of this milestone is to:
Design and implement a multi-model AI code generation system.
Develop an interactive interface for testing and comparing models dynamically.
Evaluate generated code based on software quality metrics such as complexity, maintainability, and lines of code.
Create data visualizations that highlight model performance and insights.
Ultimately, this milestone demonstrates how AI can assist in intelligent programming and code quality analysis.

# Models Utilized

Three advanced transformer-based models were used for generating and analyzing Python code:
Model	Parameters	Source	Characteristics
DeepSeek-Coder-1.3B	1.3 Billion	deepseek-ai/deepseek-coder-1.3b-instruct	Lightweight, fast, and efficient for small tasks
Phi-2 (2.7B)	2.7 Billion	microsoft/phi-2	Generates highly maintainable and concise code
Gemma-2B-IT	2 Billion	google/gemma-2b-it	Balanced between code clarity and verbosity

# Methodology and Workflow
Step 1 — Environment Setup

Used Google Colab (GPU runtime) for faster execution.
Installed libraries:
transformers, torch, radon, matplotlib, ipywidgets, pandas
Connected to Hugging Face Hub using access tokens for model loading.
Models were loaded with torch_dtype=torch.bfloat16 and device_map="auto" to optimize GPU memory usage.

Step 2 — Code Generation and Evaluation

Each model was prompted with natural-language inputs such as:
“Write a Python function to check if a number is prime.”
“Generate a Python program to reverse a string.”
After generation:
The output code was cleaned and formatted.
Syntax validation was performed using compile().
Radon library was used to calculate:
Cyclomatic Complexity → measures logical complexity
Maintainability Index (MI) → indicates code readability
Lines of Code (LOC) → measures code length
Maintainability Grade (A–C) → derived from MI
Metric Interpretation
Metric	Ideal Range	Description
Cyclomatic Complexity	Lower is better	Measures branching and control flow complexity. Simple code → lower value.
Maintainability Index (MI)	80–100 → Excellent	Higher value = code easier to read, understand, and modify.
Grade (A/B/C)	A → Excellent	Letter grade based on MI (A ≥ 80, B = 60–79, C ≤ 59).
LOC (Lines of Code)	Moderate count preferred	Reflects code size and verbosity.

Step 3 — Interactive UI using ipywidgets

To make testing user-friendly, an interactive UI was built inside Colab using ipywidgets.
UI Features:
Text area to input any custom prompt.
Checkboxes to select one or multiple models.
A “ Generate Code” button to run code generation instantly.
Real-time display of:
Generated Python code from each model
Calculated metrics
A comparative DataFrame table
This allows quick experimentation and model benchmarking in a single notebook interface.

Step 4 — Visualization with Matplotlib

Performance comparisons were visualized through colorful bar charts for better analysis.
Charts Created:
Maintainability Index Comparison
Cyclomatic Complexity Comparison
Lines of Code (LOC) Comparison

Example Results:
| Model    | Avg Complexity | Maintainability Index | Grade | LOC |
| -------- | -------------- | --------------------- | ----- | --- |
| DeepSeek | 8.0            | 79.99                 | A     | 30  |
| Phi-2    | 4.0            | 94.13                 | A     | 11  |
| Gemma    | 4.0            | 81.32                 | A     | 30  |

Insights:

Phi-2: Best maintainability, simplest and shortest code.
DeepSeek: Generates longer, structured, but more complex code.
Gemma: Balanced results with good readability.
Example Prompt & Output

Prompt: Write a Python function to check if a number is prime.

DeepSeek Output Example:

def is_prime(n):
    if n <= 1:
        return False
    elif n <= 3:
        return True
    elif n % 2 == 0 or n % 3 == 0:
        return False
    i = 5
    while i * i <= n:
        if n % i == 0 or n % (i + 2) == 0:
            return False
        i += 6
    return True
Metrics:
Avg Complexity: 8.0 | Maintainability Index: 79.99 | Grade: A | LOC: 30

# Technologies Used
| Category             | Tools                                      |
| -------------------- | ------------------------------------------ |
| Programming Language | **Python 3**                               |
| AI Libraries         | **Hugging Face Transformers**, **PyTorch** |
| Metrics Evaluation   | **Radon**                                  |
| Visualization        | **Matplotlib**                             |
| UI Development       | **ipywidgets**                             |
| Platform             | **Google Colab (GPU Runtime)**             |

# Key Insights

Phi-2 generated code with highest maintainability and clarity.
DeepSeek produced logically rich but longer code.
Gemma balanced between concise logic and structure.
All models achieved Grade A maintainability → indicating overall excellent code quality.

The project successfully automates code generation + analysis + visualization in a single system.

# Challenges Faced

Handling incomplete or truncated code outputs from models.
Removing hidden non-printable tokens from model text outputs.
Managing GPU memory while loading multiple models.
Fixing the metadata.widgets rendering issue for GitHub upload.

# Goal of Milestone 2

Implement an AI-driven code generator using multiple models
Build an interactive and intuitive UI in Google Colab
Evaluate generated code using standard software metrics
Visualize model performance with detailed charts
Document insights and comparisons clearly for final submission

# Conclusion

This milestone demonstrates the successful integration of AI, software metrics, and interactive tools into a single intelligent system.
By combining multiple models, code evaluation, and visualization, this project showcases how AI can assist developers in writing, analyzing, and improving code automatically.
It highlights the potential of AI-driven software tools to make coding more efficient, intelligent, and maintainable.ission
<img width="609" height="470" alt="image" src="https://github.com/user-attachments/assets/a8e3a92e-f0f2-47ad-ba6c-87193d2b1e4c" />



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
| Model                      | Parameters | Source                                     | Description                                                                                                                                                  |
| -------------------------- | ---------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|  **DeepSeek-Coder-1.3B** | 1.3B       | `deepseek-ai/deepseek-coder-1.3b-instruct` | A lightweight and efficient model built for **precise code understanding** and **logical structure generation**. Performs well on step-by-step coding tasks. |
|  **Phi-2 (2.7B)**        | 2.7B       | `microsoft/phi-2`                          | Known for its **clarity and accuracy**, this Microsoft model produces **short, maintainable, and clean** Python code, ideal for real-world applications.     |
|  **Gemma-2B-IT**         | 2B         | `google/gemma-2b-it`                       | A Google model fine-tuned for **instruction-based tasks**. It generates **balanced and readable** code, with excellent structure and descriptive comments.   |


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

# Visualization Results

Visualizing model performance helps to easily compare their quality, readability, and structure.
The following charts were generated using Matplotlib, based on the evaluated metrics (Maintainability Index, Code Complexity, and Lines of Code).

# Maintainability Index Comparison

This chart compares how readable and maintainable the generated code is for each model.
Higher maintainability index = more readable and maintainable code.
Phi-2 achieved the highest maintainability, showing excellent code structure.

<img width="609" height="470" alt="image" src="https://github.com/user-attachments/assets/d01aac86-07ae-4fb3-8584-82ba1d3dfd09" />

Observation:
Phi-2 produced shorter, cleaner, and highly maintainable code (MI ≈ 94).
DeepSeek and Gemma also achieved Grade A, showing good readability but slightly more verbosity.

# Code Complexity Comparison

This bar chart represents the cyclomatic complexity for each model’s generated code.
Lower complexity = simpler and more efficient logic.
Phi-2 and Gemma both maintained minimal complexity values (≈ 4), while DeepSeek had slightly higher complexity due to detailed branching.

<img width="600" height="470" alt="image" src="https://github.com/user-attachments/assets/d4c25ac6-645d-4c41-a7d3-753cc1193a19" />

Observation:
All three models maintained good logical structures.
DeepSeek’s longer algorithms increased its complexity, whereas Phi-2 generated more concise and optimized functions.

# Lines of Code (LOC) Comparison

This chart visualizes the number of lines of code each model generated for the same prompt.
Fewer lines usually mean more concise code.
Phi-2 had the least LOC, showing compactness and simplicity.

<img width="600" height="470" alt="image" src="https://github.com/user-attachments/assets/db081f9c-b43a-4dec-b095-4a172324b203" />

Observation:
Phi-2 again led in efficiency with minimal LOC (~11),
while DeepSeek and Gemma produced longer yet structurally rich code (~30 LOC).

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



# Course Overview - Foundations of Attention

Foundations of Attention is a 4 week long, self-paced individual or mentor-led course, where you will learn about the mathematics that underpins the recent advances in generative AI. In the final project, you will implement the attention mechanism, that powers recent advancements in transformer-based large language models, from scratch using only low-level libraries for numerical manipulation like NumPy and Pandas. This portfolio-ready project will be preceded by a series of learning modules where you will learn about the different components and the mathematical techniques behind them that work together as a whole to power the attention mechanism.

## Time Commitment

- **Duration**: 4 weeks
- **Estimated effort**: 8-10 hours per week
- **Total course hours**: 32-40 hours
- **Format**: Self-paced with optional mentor support

## Prerequisites

### Required Knowledge

- **Python Programming**:
  - Intermediate proficiency in Python 3.8+
  - Experience with functions, classes, and modules
  - Comfortable reading and writing Python code
  - Familiarity with debugging and error handling

- **Basic Programming Concepts**:
  - Data structures (lists, dictionaries, arrays)
  - Control flow (loops, conditionals)
  - File I/O operations

### Recommended Knowledge

- **Mathematics**:
  - High school algebra (basic operations, equations)
  - Basic understanding of functions and graphs
  - Familiarity with exponential functions
  - *Note: Linear algebra and calculus will be taught from scratch in the course*

- **Tools**:
  - Basic command line/terminal usage
  - Git basics (clone, commit, push) - helpful but not required

### Technical Requirements

- **Software**:
  - Python 3.8 or higher
  - Jupyter Notebook or JupyterLab
  - NumPy and Pandas libraries
  - Git (for accessing course repository)

- **Hardware**:
  - Any modern computer (no GPU required)
  - Minimum 4GB RAM
  - 2GB free disk space

- **IDE Recommendations**:
  - Jupyter Notebook/Lab (primary)
  - VS Code with Python extension
  - PyCharm Community Edition

## Project

The core deliverable of this course is a single Python script that manually implements the mathematical heart of a Large Language Model: the Self-Attention mechanism.

Students will not use any deep learning libraries (like PyTorch or TensorFlow). Instead, they will use NumPy to translate the "Attention Formula" directly into code:

$$Attention(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right)V$$

### Provided Materials

Students will receive a starter repository containing:

1. **attention_starter.py**: A skeleton script with function signatures, type hints, and docstrings.
2. **tests/**: A suite of local unit tests that students can run to verify their work for tensor shape correctness and numerical precision.
3. **data/**: A small JSON file containing pre-calculated word embeddings for testing.

**Note**: In addition to the local tests provided in the repository, the course uses hidden tests on the server to validate final submissions and ensure academic integrity.

### Project Learning Outcomes

After completing this project (and course), you will be able to describe the different components of the attention mechanism using mathematical terminology. You will be able to:

1. **Represent text as mathematical vectors**: To prepare inputs for the project, students will learn to convert discrete words into numeric vectors (embeddings) that preserve semantic meaning.

2. **Measure similarity using the Dot Product**: To implement the QKV portion of the project, students will use dot products to calculate how much "attention" one word should pay to another based on their directional alignment.

3. **Create probability distributions with Softmax**: To implement the softmax portion of the project, students will apply the exponential function and normalization to ensure attention scores sum to 100% (1.0).

4. **Transform data using Matrix Multiplication**: To generate the Query, Key, and Value matrices, students will perform linear transformations (row-by-column multiplication) on data batches.

## Learning Objectives

The course has been divided into 4 modules with separate learning objectives for each module. These learning objectives have been classified as *fact*, *concept*, *skill*, or *principle* based on the KLI taxonomy.

### Module 1: The Intuition of Attention

Discover why modern AI moved from sequential processing to parallel attention by visualizing how models filter signal from noise.

### Module 2: The Geometry of Intelligence

**Note**: This is the only module that has been fully fleshed out for this design assignment.

Master the linear algebra of high-dimensional space to understand how computers quantify meaning using vectors, dot products, and matrix transformations.

| Learning Objective | Knowledge Type | Resources |
|-------------------|----------------|-----------|
| Define high-dimensional vector spaces and their relevance to semantic meaning. | Concept | Illustrated Word2Vec, 3Blue1Brown: Vectors, TensorFlow Embedding Projector |
| Calculate the Dot Product ($a \cdot b$) to measure directional alignment. | Skill | 3Blue1Brown: Dot Products, NumPy dot docs |
| Interpret the Dot Product as a metric for similarity/attention. | Concept | Dot Product in ML (Towards Data Science) |
| Perform Matrix Multiplication (row-by-column) manually and via NumPy broadcasting. | Skill | MatrixMultiplication.xyz, 3Blue1Brown: Matrix Mult, NumPy Broadcasting |
| Visualize Matrix Multiplication as a Linear Transformation (warping space). | Principle | 3Blue1Brown: Linear Trans, Immersive Linear Algebra (Ch 4) |

### Module 3: The Engine of Learning

Demystify the training process by visualizing loss landscapes and using calculus to trace how models learn from their mistakes.

### Module 4: Building the Transformer

Assemble your mathematical toolbox to build the core Self-Attention mechanism from scratch using nothing but NumPy.

## Target Audience (Personas)

Given below are a few personas who might be interested in taking this course.

### The "API Wrapper" Developer

- **Job**: Backend Software Engineer (Python/Node)
- **Age**: 24
- **Degree**: B.S. in Computer Science (2 years ago)
- **Knowledge Profile**:
  - **Strong at**: Python, REST APIs, SQL, reading documentation.
  - **Weak at**: Probability, Calculus, Vector Math.
- **Current Projects**: Stitching together OpenAI APIs and LangChain to make a customer support bot.
- **The Pain Point**: "I feel like a fraud. I'm just calling APIs. When the bot hallucinates or gives a bad answer, I don't know why—I just randomly change the prompt until it works."
- **Future Goal**: "I want to be a real AI Engineer. I want to know how to fix the engine when it breaks, not just sit on top of it."

### The Traditional Data Analyst

- **Job**: Junior Data Scientist
- **Age**: 26
- **Degree**: B.S. in Statistics or Mathematics
- **Knowledge Profile**:
  - **Strong at**: Excel, SQL, Scikit-Learn (Regression/Random Forest), Structured Data.
  - **Weak at**: Neural Networks, Embeddings, Unstructured Data (Text/Images).
- **Current Projects**: Predicting customer churn using Excel/Tabular data.
- **The Pain Point**: "Everyone is moving to Deep Learning and LLMs. I understand p-values and averages, but 'Embeddings' and 'Attention' feel like magic. I feel my skills are becoming obsolete."
- **Future Goal**: "I want to map my existing statistical knowledge to modern AI so I can build NLP and GenAI applications."

## Course Modality

To get the most out of this course, you need to do it with a mentor who can complete the course project on their own. This means they should have deep architectural and mathematical knowledge about the attention mechanism. You can also go through this course on your own, but without feedback from a knowledgeable mentor, the course turns into an interactive textbook.

## Resources

The course repository contains all the files needed for the course, including Jupyter notebooks with embedded presentations, starter code, and local tests.

The course website provides:
- **Course Book**: An HTML version of all Jupyter notebooks (automatically generated from the repository)
- **Certificate Page**: A page where students can upload their completion keys to generate their certificate of completion

## Assessment & Certificate of Completion

### Assessment Structure

The course consists of 4 modules, each with a programming assignment:

**Modules 1-3**: Build foundational skills
- Learn individual components (vectors, dot products, matrix multiplication, softmax)
- Complete focused assignments on specific concepts
- Each assignment builds toward the final implementation

**Module 4 - Final Project**: Implement Complete Self-Attention Mechanism
- Synthesize all learned concepts into a single NumPy implementation
- Build the full attention mechanism from scratch
- Demonstrate mastery of the mathematical foundations

### Assignment Workflow

For each module, you will:

1. **Learn**: Read lessons and watch embedded presentations in Jupyter notebooks
2. **Practice**: Run local tests provided in the repository to verify your understanding
3. **Implement**: Write your solution to the programming assignment
4. **Submit**: Submit your code to the course API server
5. **Validate**: Server runs hidden tests to ensure correctness and academic integrity
6. **Receive Key**: If all hidden tests pass, the server generates and returns a unique completion key for that module
7. **Save Key**: Save your key locally (you'll need all 4 keys for certification)

### Completion Requirements

To earn your certificate of completion:

1. Complete all 4 module assignments (Modules 1-3 + Final Project)
2. Receive all 4 completion keys from the server
3. Upload all 4 keys to the course website's certificate page
4. Server validates your keys and generates your certificate

### Module 4 (Final Project) Evaluation

Your final project implementation will be evaluated based on:

1. **Correctness**: Passing all hidden tests on the server
2. **Code Quality**: Proper use of NumPy operations and adherence to provided function signatures
3. **Numerical Precision**: Accurate implementation of the attention formula with correct mathematical operations

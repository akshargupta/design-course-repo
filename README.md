# Design Course Submission - Foundations of Attention

**Author:** Akshar Gupta
**Project:** Course Design Assignment
**Course Title:** Foundations of Attention
**Submission Date:** December 2025

---

## Overview

This repository contains my complete submission for the design course assignment. I have designed a 4-week online course titled **"Foundations of Attention"** that teaches the mathematical foundations of transformer-based large language models through hands-on implementation.

The course focuses on teaching learners how to implement the self-attention mechanism from scratch using only NumPy, building mathematical understanding through progressive skill development.

---

## Submission Contents

This submission includes the following deliverables:

### 1. Course Overview
📄 **File:** [`course-overview.md`](./course-overview.md)

Complete course specification including:
- Course description and learning objectives
- Time commitment and prerequisites
- 4 module structure with detailed Module 2 breakdown
- Target audience personas (API Wrapper Developer, Traditional Data Analyst)
- Assessment structure and certificate requirements
- Technical requirements and resources

### 2. Design Mockups

#### Tech Stack Diagram
📄 **File:** [`tech-stack-diagram.md`](./tech-stack-diagram.md)

System architecture diagram (Mermaid) showing:
- Course repository structure (GitHub)
- CI/CD pipeline (Quarto + GitHub Actions)
- Frontend components (Jupyter Notebooks, static website)
- Backend API server (hidden tests, certificate generation)
- Student workflow and data flows

#### User Journey Diagrams
📄 **File:** [`user-journey-diagram.md`](./user-journey-diagram.md)

Complete user journey visualization (Mermaid) including:
- Two learning paths: Self-paced vs Mentor-led
- Module completion cycle (repeats 4 times)
- Key differences comparison table
- Mentor touchpoints and emotional journey

### 3. Course Rationale
📄 **File:** [`course-rationale.md`](./course-rationale.md)

Detailed design rationale explaining:
- Target audience analysis and needs assessment
- Learning objectives alignment with KLI taxonomy
- Pedagogical approach and instructional strategies
- Assessment design and hash-based certificate system
- Technology choices and architectural decisions
- Expected learning outcomes and success metrics

### 4. Sample Lesson (Module 2, Lesson 1)
📓 **File:** [`module-2-lesson-1.ipynb`](./module-2-lesson-1.ipynb)

Fully developed Jupyter notebook demonstrating:
- **Learning Objective:** Define high-dimensional vector spaces and their relevance to semantic meaning (Concept)
- Interactive visualizations using Plotly
- Conceptual explanations with examples
- Knowledge check quizzes
- Programming assignment with local tests
- Connection to final project (attention mechanism)

**Note:** This is the only module that has been fully developed for this design assignment, as specified in the course overview.

---

## Course Design Highlights

### Unique Features

1. **Hash-Based Certificate System**: Students submit code to an API that runs hidden tests and returns unique keys. Certificate is generated only when all 4 module keys are uploaded.

2. **Dual Learning Paths**:
   - Self-paced (materials + API validation)
   - Mentor-led (includes code reviews, meetings, feedback loops)

3. **Local-First Development**: Students work offline in Jupyter notebooks, only connecting to server for validation.

4. **Embedded Presentations**: Reveal.js presentations with audio embedded directly in notebooks, automatically published to website via Quarto.

5. **Progressive Skill Building**: Each module builds toward implementing the attention formula in Module 4:
   ```
   Attention(Q, K, V) = softmax(QK^T / √d_k)V
   ```

### Technology Stack

- **Content Delivery**: Jupyter Notebooks, Quarto, GitHub Pages
- **Backend**: API server for hidden tests and certificate generation
- **CI/CD**: GitHub Actions
- **Student Tools**: Python 3.8+, NumPy, Pandas, Plotly

---

## Target Audience

The course is designed for two primary personas:

1. **The "API Wrapper" Developer** (24, Backend Software Engineer)
   - Currently: Building apps with OpenAI API and LangChain
   - Pain point: Feels like a fraud, wants to understand what's under the hood
   - Goal: Become a "real AI Engineer" who can fix the engine

2. **The Traditional Data Analyst** (26, Junior Data Scientist)
   - Currently: Using Excel/Scikit-Learn for structured data
   - Pain point: Deep learning feels like magic, skills becoming obsolete
   - Goal: Map statistical knowledge to modern AI, build NLP applications

---

## Course Structure

**Duration:** 4 weeks
**Effort:** 8-10 hours per week
**Total Hours:** 32-40 hours

### Modules

1. **Module 1: The Intuition of Attention**
   - Why modern AI moved from sequential to parallel processing

2. **Module 2: The Geometry of Intelligence** ⭐ *Fully developed*
   - Lesson 1: Vectors and high-dimensional spaces
   - Lesson 2+: Dot products, matrix multiplication, linear transformations

3. **Module 3: The Engine of Learning**
   - Loss landscapes, gradients, and how models learn

4. **Module 4: Building the Transformer**
   - Final project: Implement self-attention mechanism from scratch

---

## Assessment Approach

Each module requires:
1. Complete programming assignment in Jupyter notebook
2. Run local tests to verify implementation
3. Submit code to API server
4. Pass hidden tests to receive completion key
5. Save key for final certificate generation

**Certificate Requirements:**
- Complete all 4 module assignments
- Receive all 4 completion keys
- Upload keys to course website
- Server validates keys and generates certificate

---

## File Navigation Guide

```
design-course-repo/
│
├── README.md                      ← You are here
│
├── course-overview.md             ← Complete course specification
│
├── course-rationale.md            ← Design decisions and pedagogy
│
├── tech-stack-diagram.md          ← System architecture (Mermaid)
│
├── user-journey-diagram.md        ← User flows for both learning paths
│
└── module-2-lesson-1.ipynb        ← Sample lesson with full implementation
```

---

## Viewing the Submission

### Markdown Files
All markdown files (`.md`) can be viewed directly on GitHub with full formatting, including:
- Mermaid diagrams (rendered automatically)
- Tables and hyperlinks
- Code blocks

### Jupyter Notebook
The notebook (`.ipynb`) can be:
- Viewed on GitHub (with preview)
- Downloaded and run locally in Jupyter Lab/Notebook
- Opened in Google Colab or VS Code

### Mermaid Diagrams
GitHub automatically renders Mermaid diagrams in markdown files. If viewing locally, use a Mermaid-compatible markdown viewer or IDE extension.

---

## Design Philosophy

This course is built on three core principles:

1. **Implementation over Theory**: Students learn by building, not just reading
2. **Progressive Complexity**: Each concept builds naturally on previous ones
3. **Practical Output**: The final project (attention implementation) is portfolio-ready

The design emphasizes **understanding through construction** - by implementing each mathematical component with NumPy, students gain deep intuition for how transformer models actually work.

---

## Contact

For questions about this submission, please contact the course designer through the appropriate channels.

---

**License:** This course design is submitted as part of an educational assignment.

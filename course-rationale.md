# Rationale for the Design of "Foundations of Attention"

This essay contains the rationale for the design decisions that I have made while working on the part-build for the final assignment of the Design course. I will start by describing my motivation for designing this course in the larger context of the technology labour market and the recent shift away from degrees and towards "skills". Then I will talk about the specifics of the course design as described in the design documents folder. I will then talk about the values that are demonstrated in this course design. I will end with talking about some limitations of this course design.

## Context: Shifts in the Technology Labour Market

The motivation for the "Foundations of Attention" course is rooted in a transformation currently reshaping the technology labour market: a move toward "skills-based hiring." Recent large-scale analyses of job vacancies indicate that emerging professions, particularly in Artificial Intelligence (AI) and sustainability, are experiencing labour shortages where industry demand vastly outpaces the supply of qualified talent. Bone et al. (2025) provide evidence that employers are responding to this shortage by prioritizing specific competencies over formal credentials. Their regression analysis reveals that while AI roles command a significant wage premium (23%), the premium traditionally associated with formal degrees for these specific roles is diminishing or disappearing entirely. This suggests that the market currently values the specific ability to engineer AI systems more than the general signaling of a university degree.

This economic reality informed the target audience for this course: professionals who already possess degrees—such as the "API Wrapper Developer" and "Traditional Data Analyst"—but whose skills are becoming obsolete due to the rapid advancement of deep learning. The course is designed to bridge this specific gap, equipping learners with the mathematical competencies required for engineering the underlying technologies.

## Course Design: Backward Design and the KLI Framework

To ensure the course effectively facilitates this transition, the curriculum was structured using the principles of Backward Design as outlined by Wiggins and McTighe (2011). This framework advocates for designing curriculum by first identifying desired results, then determining acceptable evidence, and finally planning learning experiences.

### Personas and Learning Needs

The design process began with a clear identification of the learners. Utilizing methodologies for user-centered design from the Interaction Design Foundation (n.d.), I developed fictional personas to represent the target demographic. These personas, specifically the "API Wrapper Developer" (seeking to understand the "black box" of AI) and the "Traditional Data Analyst" (fearing obsolescence), provided a lens through which to filter content and ensure relevance. These personas were validated through industry research on skill gaps in AI (Bone et al., 2025) and existing literature on practitioner needs in computer science education.

### Backward Design of Modules

Consequently, the course's "Stage 1" desired result was defined not as a theoretical exam, but as a portfolio-ready performance task: the implementation of the self-attention mechanism from scratch using only low-level libraries. With the final project—implementing attention in Module 4—as the desired result, I designed the course backwards. The attention formula requires matrix multiplication, which requires dot products, which requires understanding vectors in high-dimensional space.

The course is structured as a **4-week program**, with each module designed to be completed in approximately one week at 8-10 hours of study:

**Module 1: The Intuition of Attention** provides the conceptual foundation, explaining why modern AI moved from sequential processing to parallel attention mechanisms.

**Module 2: The Geometry of Intelligence** was designed to teach all required linear algebra concepts progressively across multiple lessons. This module contains:
- Lesson 1: Vectors and high-dimensional spaces (foundational concepts)
- Lesson 2: Dot products (measuring similarity)
- Lesson 3: Matrix multiplication (transforming data)
- Lesson 4: Linear transformations (geometric understanding)

**Module 3: The Engine of Learning** addresses the calculus needed for understanding model training, including loss landscapes and gradients.

**Module 4: Building the Transformer** synthesizes all previous learning in the final project, where students implement the complete self-attention mechanism from scratch.

This logical dependency chain ensures that every instructional element directly contributes to the final performance task.

### The KLI Framework

To refine the instructional strategies within these modules, I applied the **Knowledge-Learning-Instruction (KLI) framework** (Koedinger et al., 2012). This theoretical framework argues that different types of knowledge components require different learning processes. Accordingly, the course learning objectives were explicitly classified into *facts*, *concepts*, *skills*, and *principles*.

For example, within Module 2, learning objectives are distributed across lessons according to knowledge type: "Define high-dimensional vector spaces" (Lesson 1) is classified as a *concept* and taught through sense-making visualizations, while "Calculate the Dot Product" (Lesson 2) is a *skill* requiring fluency-building practice exercises. According to Koedinger et al. (2012), skill acquisition (procedural knowledge) requires deliberate practice, while conceptual understanding benefits from multiple representations and interactive exploration.

### Jupyter Notebooks and Implementation-First Learning

The decision to house the entire course within **Jupyter Notebooks** aligns with the need to integrate these diverse learning events. The notebooks serve as a unified environment where instructional text, embedded Reveal.js presentation slides (with audio explanations), Plotly interactive 3D visualizations, and executable code coexist. This format facilitates active learning, allowing students to immediately apply conceptual knowledge through coding assignments within the lesson environment itself.

Critically, the implementation is restricted to **NumPy only**, excluding high-level libraries like PyTorch or TensorFlow. This "implementation over abstraction" approach forces students to manually code each mathematical operation, preventing them from treating attention as a black box and ensuring deep procedural understanding. Students cannot simply invoke `torch.nn.MultiheadAttention`—they must construct it from first principles, line by line.

### Technical Architecture

The technical architecture supports this pedagogy through several integrated components:

- **Jupyter Notebooks** with embedded Reveal.js presentations containing audio explanations
- **Plotly** for interactive 3D visualizations of semantic embedding spaces
- **Backend API** with two endpoints:
  - `/test`: Receives student code, runs hidden validation tests, returns unique hash-based key on success
  - `/certificate`: Validates uploaded keys and generates final certificate
- **Local tests**: Students can run these before submission to verify correctness
- **Hidden tests**: Server-only tests ensure academic integrity
- **Quarto**: Automatically converts notebooks to HTML for web publication
- **GitHub Actions**: CI/CD pipeline that publishes the course as a static website
- **GitHub Pages**: Hosts the open-access course book

This open-source stack ensures the content remains platform-independent and students retain ownership of their work through local-first development.

### Dual Learning Paths

Furthermore, while a self-paced path is available, the design prioritizes a **mentor-led model**. The course offers two distinct learning paths:

In the **self-paced path**, students work independently through Jupyter notebooks, run local tests to verify their understanding, and validate their work via API submissions. This path provides flexibility but relies primarily on automated feedback.

The **mentor-led path** adds structured touchpoints: kickoff meetings to establish goals, regular check-ins during implementation, code reviews *before* API submission, and iterative feedback loops where students revise code based on mentor input. As visualized in the user journey diagrams, the mentor-led path transforms the learning experience from transactional validation to dialogic development.

This decision is grounded in research on project-based learning in computer science, which suggests that students often perceive unguided projects as "chaotic" and benefit significantly from experienced guidance to navigate complex implementation problems (Pucher & Lehner, 2011). The mentor-led journey ensures that students develop deep conceptual understanding rather than just copying code patterns.

## Values: Openness, Ungrading, and Feedback

The technical and pedagogical architecture of this course demonstrates a commitment to specific educational values that resist current trends in the "platformization" of education.

### Open Web Technologies Against Platformization

First, the course embraces **open web technologies** as a stance against the "rentier" model of education described by Komljenovic (2021). In the current digital economy, proprietary platforms often enclose student data and lock institutions into restrictive ecosystems to extract value. By utilizing an open technologies stack—Git for content hosting, Quarto for publishing, and a static website structure—this course ensures that the educational content remains accessible and that learners retain ownership of their work in a local-first development environment. Students can fork the repository, modify the content, and share their implementations without platform mediation or data extraction.

### Ungrading

Second, the assessment strategy reflects the principles of **ungrading**, as advocated by Stommel (2024). Stommel argues that grades often act as extrinsic motivators that harm the learning relationship and encourage compliance over curiosity. Instead of letter grades, the course uses a hash-based key system. When a student submits code for a module assignment, the server runs hidden tests; if all tests pass, the server generates and returns a unique hash-based key. Students must collect all **4 keys** (one per module) and upload them to the course website's certificate page, where the server validates the key hashes before generating the final certificate.

This system combines the security of hidden tests (preventing gaming) with the transparency of clear success criteria. The binary feedback loop (pass/not yet) shifts the focus from accumulating points to demonstrating competency through iteration. Students are encouraged to revise and resubmit until they achieve mastery, rather than accepting a partial-credit grade and moving on with incomplete understanding.

### The Importance of Feedback

Third, the course design emphasizes the critical role of **feedback**, particularly in the mentor-led path. As Hounsell (2021) notes, feedback in postgraduate-level study must be "generative" and "actionable" to support students in developing disciplinary habits of mind. The user journey is designed with specific touchpoints for this: kickoff meetings, code reviews, and feedback loops where students revise code based on mentor input before final submission. This dialogic approach transforms assessment from a summative judgment into a formative conversation that advances learning.

The combination of automated tests (for immediate validation) and human feedback (for conceptual guidance) creates a hybrid assessment model. The automated system scales efficiently for the self-paced path, while the mentor-led path preserves the irreplaceable value of expert guidance in developing professional coding practices and deep mathematical intuition.

## Limitations

Despite its intentional design, the course has limitations.

First, the reliance on a mentor-led model for the optimal experience creates significant **scalability issues**. As Pucher and Lehner (2011) note, the success of project-based learning is highly dependent on the specific experience of the teacher, and finding qualified mentors who deeply understand attention mechanisms at both the mathematical and implementation levels is a significant bottleneck. The course design assumes access to mentors with specialized expertise—a resource that may not be readily available in many educational contexts.

Second, the "ungrading" system for the self-paced path relies on **automated tests**. While efficient, these tests verify code correctness but cannot assess the elegance or maintainability of the solution, nor can they correct deep conceptual misunderstandings if a student arrives at the right answer through incorrect reasoning. A student might, for example, implement matrix multiplication with nested loops that produce correct output but demonstrate no understanding of vectorization or computational efficiency. The automated system would pass such code, missing an opportunity for formative feedback.

Third, the **technical prerequisites**—specifically the need to manage a local Python environment, use Git for version control, and navigate Jupyter notebooks—may present a barrier to entry for learners who could benefit from the conceptual content but lack the specific software engineering background to manage the course repository. The course assumes a baseline of technical literacy that may exclude learners from non-traditional backgrounds who are attempting to transition into AI engineering.

Finally, while the course teaches the mathematical implementation of attention, it does **not address the broader socio-technical context** of deploying AI systems responsibly. Students learn how attention works but not necessarily when it should be used, what biases it might amplify, or how to evaluate its societal impact. This limitation reflects a design choice to focus narrowly on mathematical competency, but it risks producing technically skilled practitioners who lack critical perspectives on the systems they build.

## References

- Bone, M., González Ehlinger, E., & Stephany, F. (2025). Skills or degree? The rise of skill-based hiring for AI and green jobs. *Technological Forecasting & Social Change*, 214, 124042. https://doi.org/10.1016/j.techfore.2025.124042

- Hounsell, D. (2021). Feedback in Postgraduate Online Learning: Perspectives and Practices. In T. Fawns et al. (Eds.), *Online Postgraduate Education in a Postdigital World*. Springer Nature. https://doi.org/10.1007/978-3-030-77673-2_3

- Interaction Design Foundation (n.d.). Personas – A Simple Introduction. https://www.interaction-design.org/literature/article/personas-why-and-how-you-should-use-them

- Koedinger, K. R., Corbett, A. T., & Perfetti, C. (2012). The Knowledge-Learning-Instruction Framework: Bridging the Science-Practice Chasm to Enhance Robust Student Learning. *Cognitive Science*, 36, 757-798. https://doi.org/10.1111/j.1551-6709.2012.01245.x

- Komljenovic, J. (2021). The rise of education rentiers: digital platforms, digital data and rents. *Learning, Media and Technology*, 46(3), 320-332. https://doi.org/10.1080/17439884.2021.1891422

- Pucher, R., & Lehner, M. (2011). Project Based Learning in Computer Science - A Review of More than 500 Projects. *Procedia - Social and Behavioral Sciences*, 29, 1561-1566. https://doi.org/10.1016/j.sbspro.2011.11.398

- Stommel, J. (2024). Ungrading: An Introduction. *Pedagogy: Critical Approaches to Teaching Literature, Language, Composition, and Culture*, 24(3), 327-340. https://doi.org/10.1215/15314200-11246255

- Wiggins, G., & McTighe, J. (2011). *The Understanding by Design Guide to Creating High-Quality Units*. ASCD.

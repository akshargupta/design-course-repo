# User Journey Diagram

## Two Learning Paths

```mermaid
flowchart TD
    START([Student Discovers Course]) --> REVIEW[Review Course Overview<br/>Prerequisites & Syllabus]
    REVIEW --> DECISION{Meets<br/>Prerequisites?}
    DECISION -->|No| LEARN_PREP[Study Prerequisites<br/>Python, Basic Math]
    LEARN_PREP --> DECISION
    DECISION -->|Yes| MODALITY{Choose<br/>Learning Mode}

    MODALITY -->|Self-Paced| CLONE_SOLO[Clone Repository<br/>Setup Environment]
    MODALITY -->|With Mentor| FIND_MENTOR[Find Mentor]

    FIND_MENTOR --> INTRO[Introductory Meeting<br/>Set Expectations]
    INTRO --> CLONE_MENTOR[Clone Repository<br/>Setup Environment]

    CLONE_SOLO --> SOLO_PATH[Self-Paced Journey]
    CLONE_MENTOR --> MENTOR_PATH[Mentor-Led Journey]

    style START fill:#e1f5ff
    style MODALITY fill:#ffe1e1
    style SOLO_PATH fill:#e1ffe1
    style MENTOR_PATH fill:#fff4e1
```

## Path 1: Self-Paced Journey

```mermaid
flowchart TD
    START_SOLO([Self-Paced Mode]) --> SETUP[Setup Environment<br/>Clone Repository]
    SETUP --> MODULE_START[Open Module Notebook]

    MODULE_START --> READ[Read Lesson<br/>Watch Presentations]
    READ --> LOCAL[Run Local Tests]
    LOCAL --> CODE[Write Assignment]
    CODE --> SUBMIT[Submit to API]
    SUBMIT --> TEST{Tests Pass?}
    TEST -->|Fail| DEBUG[Debug Independently<br/>Re-read Materials]
    DEBUG --> CODE
    TEST -->|Pass| KEY[Receive Key]
    KEY --> SAVE[Save Key]

    SAVE --> MORE{More<br/>Modules?}
    MORE -->|Yes<br/>Modules 1-3| MODULE_START
    MORE -->|Module 4<br/>Complete| CERT_SOLO[Get Certificate]
    CERT_SOLO --> END_SOLO([Course Complete])

    style START_SOLO fill:#e1ffe1
    style END_SOLO fill:#e1ffe1
    style KEY fill:#fff4e1
    style MORE fill:#ffe1e1
```

**Note**: This cycle repeats 4 times (once for each module)

## Path 2: Mentor-Led Journey

```mermaid
flowchart TD
    START_MENTOR([Mentor-Led Mode]) --> KICKOFF[Kickoff Meeting<br/>Mentor + Student]
    KICKOFF --> PLAN[Set Learning Schedule<br/>Meeting Cadence]

    PLAN --> MODULE_START[Start Module]

    subgraph "Module Cycle (Repeats 4x)"
        MODULE_START --> PRE[Pre-work:<br/>Read Lesson, Watch Presentations]
        PRE --> MEET[Mentor Meeting<br/>Discuss Concepts]
        MEET --> WORK[Work on Assignment<br/>Apply Feedback]
        WORK --> REVIEW[Code Review<br/>with Mentor]
        REVIEW --> REVISE{Mentor<br/>Approves?}
        REVISE -->|No| FEEDBACK[Receive Feedback<br/>Revise Code]
        FEEDBACK --> WORK
        REVISE -->|Yes| SUBMIT[Submit to API]
        SUBMIT --> TEST{Tests Pass?}
        TEST -->|Fail| DEBUG_M[Debug with<br/>Mentor Support]
        DEBUG_M --> WORK
        TEST -->|Pass| KEY[Receive Key]
        KEY --> SAVE[Save Key]
    end

    SAVE --> MORE{More<br/>Modules?}
    MORE -->|Yes<br/>Modules 1-3| MODULE_START
    MORE -->|Module 4<br/>Complete| FINAL_MEET[Final Meeting<br/>Celebrate Success]

    FINAL_MEET --> CERT_MENTOR[Get Certificate]
    CERT_MENTOR --> END_MENTOR([Course Complete])

    style START_MENTOR fill:#fff4e1
    style END_MENTOR fill:#fff4e1
    style KEY fill:#ffe1e1
    style MORE fill:#ffe1e1
```

**Note**: The module cycle repeats 4 times (once for each module)

## Comparison: Self-Paced vs Mentor-Led

```mermaid
graph LR
    subgraph "Self-Paced Journey"
        SP1[Read Materials] --> SP2[Code Assignment]
        SP2 --> SP3[Debug Independently]
        SP3 --> SP4[Submit to API]
        SP4 --> SP5[Receive Key]
    end

    subgraph "Mentor-Led Journey"
        ML1[Pre-work Reading] --> ML2[Mentor Discussion]
        ML2 --> ML3[Code Assignment]
        ML3 --> ML4[Code Review with Mentor]
        ML4 --> ML5[Revise Based on Feedback]
        ML5 --> ML6[Submit to API]
        ML6 --> ML7[Receive Key]
    end

    style SP1 fill:#e1ffe1
    style SP5 fill:#e1ffe1
    style ML1 fill:#fff4e1
    style ML7 fill:#fff4e1
```

## Key Differences

| Aspect | Self-Paced | Mentor-Led |
|--------|-----------|------------|
| **Support** | Materials only (notebooks, presentations) | Mentor guidance + materials |
| **Feedback Loop** | API test results only | Code reviews + mentor feedback before submission |
| **Debugging** | Independent problem-solving | Collaborative debugging sessions |
| **Schedule** | Flexible, student's pace | Structured meetings (weekly/bi-weekly) |
| **Accountability** | Self-driven | Mentor check-ins |
| **Learning Depth** | Can skip to "make it work" | Mentor ensures deep understanding |
| **Time Commitment** | 8-10 hrs/week solo | 8-10 hrs/week + 1-2 hrs mentor meetings |

## Mentor Touchpoints

### Kickoff Meeting
- Set expectations and goals
- Establish meeting schedule
- Review course structure
- Assess student's current knowledge

### Module Meetings (4 total)
- **Before assignment**: Discuss concepts, answer questions
- **During assignment**: Progress check-ins, unblock issues
- **Code review**: Review solution before API submission
- **After submission**: Celebrate success, prep for next module

### Final Meeting
- Review complete journey
- Discuss career applications
- Provide recommendation/endorsement
- Celebrate certificate achievement

## Emotional Journey Comparison

### Self-Paced
```
Excitement → Confusion → Frustration → Breakthrough → Pride
     ↓           ↓            ↓              ↓           ↓
  Module 1   Module 2    Module 3      Module 4   Certificate
```

### Mentor-Led
```
Excitement → Supported Learning → Guided Progress → Mastery → Pride
     ↓              ↓                    ↓             ↓         ↓
  Kickoff      Modules 1-3          Module 4      Review    Certificate
```

**Key Difference**: Mentor-led reduces frustration valleys through continuous support, but self-paced offers more flexibility and autonomy.

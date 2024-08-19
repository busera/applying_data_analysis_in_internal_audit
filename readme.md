# Applying Data Analysis in Internal Audit

This repository contains resources and examples for applying data analysis techniques in internal auditing. It aims to bridge the gap between data analysis theory and practical application in the field of internal audit including code examples, data sets and visualizations.

## Methodology
1. [Phase 1 - Scope & Plan](./methodology/phase1.md)
2. [Phase 2 - Data Collection & Curation](./methodology/phase2.md)
3. [Phase 3 -Analyze](./methodology/phase3.md)
4. [Phase 4 - Interpretation & Communication](./methodology/phase4.md)

## Workflow

```mermaid

flowchart TB
    A[Start]
    F[End]

    subgraph workflow [" "]
        direction TB
        subgraph Phase1["Phase 1: Scope & Plan"]
            direction TB
            B1[1.0 Initial Objective Setting]
            B2[2.0 Define Data Analysis Scope and Questions]
            B3[3.0 Identify Data Requirements]
            B4[4.0 Stakeholder Engagement]
            B5[5.0 Data Request and Acquisition]
            B1 --> B2 --> B3 --> B4 --> B5
        end

        subgraph Phase2["Phase 2: Data Collection & Curation"]
            direction TB
            C1[6.0 Data Validation and Cleansing]
            C2[7.0 Data Management]
            C1 --> C2
        end

        subgraph Phase3["Phase 3: Analyze"]
            direction TB
            D1[8.0 Conduct Initial EDA]
            D2[9.0 Develop and Execute Test Scripts and Queries]
            D3[10.0 Perform Targeted/Focused Analysis]
            D4[11.0 Interpret & Analyze Results]
            D5[12.0 Documentation and Iteration]
            D1 --> D2 --> D3 --> D4 --> D5
        end

        subgraph Phase4["Phase 4: Interpretation & Communication"]
            direction TB
            E1[13.0 Synthesize and Evaluate Findings]
            E2[14.0 Prepare and Communicate Results]
            E3[15.0 Document Technical Details]
            E1 --> E2 --> E3
        end
    end

    A --> B1
    B5 --> C1
    C2 --> D1
    D5 --> E1
    E3 --> F

    %% Additional paths
    D1 -.-> |Refine questions| B2
    D1 -.-> |Revisit data cleansing| C1

    classDef error stroke:#f00,stroke-width:2px;
    class B2,C1 error;
```

## Available Guides
- [Methodology](./methodology/00_methodology.md)
- [2.0 Formulate initial questions and hypotheses](./methodology/2.0_define_da_questions/00_define_da_questions.md)

## About This Project

This project explores the application of data analysis techniques in internal auditing, adapting key concepts from academic research methodologies to the practical world of internal audit. It focuses on two distinct concepts:

- Confirmatory vs. Exploratory Questions
- Causal vs. Non-Causal Questions

This repository will include examples with generated or anonymized real-life data, Python code for analysis and visualization.


## Contact

For questions or feedback, please open an issue in this repository.

---

tags: #data_analysis

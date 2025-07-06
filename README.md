# Condition Sequence Coverage Criterion and Automatic Test Case Generation for Testing-Based Formal Verification

###  Project Overview

The tool **TBFV4J-CSC** presented in this project is implemented based on the methodology proposed in the paper *"Condition Sequence Coverage Criterion and Automatic Test Case Generation for Testing-Based Formal Verification."* It is an enhanced and upgraded version of the original TBFV4J tool, introducing a novel test coverage criterion—**Condition Sequence Coverage (CSC)**—to replace the original random test case generation strategy. This advancement significantly improves the thoroughness and precision of path exploration during verification, enabling more effective detection of semantic defects in Java programs.

------

###  Project Directory Structure

This project consists of the following three main folders: 

#### 1. `Experiment Result`

This folder contains the evaluation results comparing the performance of **TBFV4J-CSC** and **TBFV4J-Ran**. It includes data collected from **14 representative Java program samples**, with a total of **92 sets of experiments**. These results correspond directly to Table 1 and Table 2 in the paper.

#### 2. `TBFV4J-CSC-DataSet`

This folder provides a dedicated dataset designed to support the validation of the CSC criterion and the automatic test case generation algorithm. Each program sample includes:

- A well-defined Functional Scenario Form (FSF);
- A set of mutated program versions with semantic defects.

This dataset serves as the foundation for experimental validation and algorithm analysis.

#### 3. `TBFV4J-CSC-Code`

This folder contains the **full source code** of the TBFV4J-CSC tool. We**open research, reproducibility, and extensibility**, and welcome researchers to reuse, test, or extend the code.

Each folder includes its own `README.md` with more detailed explanations. We recommend reading them for usage instructions and technical details.

------

###  About TBFV4J-Ran

**TBFV4J-Ran** is an automated tool that integrates **specification-based testing** with **formal verification** for validating Java programs. It adopts a grey-box testing approach, combining path exploration and constraint solving, which avoids the need for manually deriving loop invariants.

GitHub repository:
🔗  https://github.com/aabcliu/TBFV4J

The tool has been officially accepted for demonstration at **ISSTA 2025**:
 🔗 https://dl.acm.org/doi/10.1145/3713081.3731740

------

###  Differences Between TBFV4J-CSC and TBFV4J-Ran

Although **TBFV4J-CSC** is built upon the**TBFV4J-Ran**, it features extensive enhancements and architectural redesigns, particularly in the following two core modules:

#### 🔹 Java Code Parser Redesign

- **TBFV4J-Ran**: Relies on regula
- **TBFV4J-CSC**: Uses `JavaParser` to construct an abstract syntax tree (AST) from the Java code (`CompilationUnit`) and overrides the `ModifierVisitor` to accurately visit and modify syntax nodes (e.g., `IfStmt`, `AssignExpr`, `ReturnStmt`). This significantly improves parsing precision and automation.

#### 🔹 Test Execution and Generation Strategy Upgrade

- **TBFV4J-Ran**: Uses a **randomized strategy** for test case generation, which lacks directionality and may miss important execution paths.
- **TBFV4J-CSC**: Introduces the **Condition Sequence Coverage (CSC)** criterion, guiding the t

> According to our analysis, **approximately 70% of the TBFV4J-CSC codebase has been rewritten or significantly refactored**, including major changes in both the test generation algorithm and the Java parsing logic.

For detailed installation and usage instructions, please refer to the `README.md` file located in the [`TBFV4J-CSC-Code`](https://chat3.sorryios.ai/c/TBFV4J-CSC-Code) folder.

------

We welcome you to use, contribute to, or provide feedback on this project to advance the development of practical and intelligent formal verification tools.
 For questions or bug reports, please open an [Issue](https://github.com/your-project/issues).


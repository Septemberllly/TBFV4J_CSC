# TBFV4J-CSC-Code

This folder contains the **complete source code** of the **TBFV4J-CSC** tool, which is implemented based on the methodology proposed in the paper *"Condition Sequence Coverage Criterion and Automatic Test Case Generation for Testing-Based Formal Verification."*

------

## Project Features Overview

TBFV4J-CSC provides the following core functionalities:

- **Java Program Parsing**: Constructs abstract syntax trees using `JavaParser`, enabling structured, statement-level code analysis.
- **Condition Sequence Extraction and Coverage Checking**: Extracts atomic conditions from execution paths and constructs condition sequences.
- **Automated Test Case Generation**: Generates representative test cases by combining functional scenarios (FSF) with the CSC criterion.
- **Formal Path Verification**: Applies Hoare logic for path reasoning and verifies program correctness using the Z3 SMT solver.
- **Bug Detection and Counterexample Reporting**: Automatically reports counterexamples when the program violates the specification.

------

## 🚀 Getting Started

### 1. Clone the Repository

```bash
gh repo clone Septemberllly/TBFV4J_CSC
cd Septemberllly/TBFV4J_CSC
```

### 2. Build the Project (Using Maven)

Make sure Java (JDK 11 or higher) and Maven are installed on your machine. Then run:

```bash
mvn clean install
```

### Maven Dependencies

```xml
<dependencies>
    <dependency>
        <groupId>com.github.javaparser</groupId>
        <artifactId>javaparser-core</artifactId>
        <version>3.23.1</version>
    </dependency>
    <dependency>
        <groupId>com.microsoft.z3</groupId>
        <artifactId>z3</artifactId>
        <version>4.13.3</version>
    </dependency>
    <dependency>
        <groupId>org.codehaus.groovy</groupId>
        <artifactId>groovy-all</artifactId>
        <version>2.4.16</version>
    </dependency>
    <dependency>
        <groupId>com.github.jsqlparser</groupId>
        <artifactId>jsqlparser</artifactId>
        <version>3.1</version>
    </dependency>
</dependencies>
```

### 3. Import into IDE

You can import the project into any of the following IDEs:

- IntelliJ IDEA
- Eclipse
- Visual Studio Code

> It is recommended to use **IntelliJ IDEA** and enable automatic Maven dependency import.

------

##  How to Use

1. **Prepare Input Files**:
   - Java source code (we recommend using sample programs provided in the dataset).
   - Corresponding functional specification in **Functional Scenario Form (FSF)**.
2. **Run the Tool**:
   - Execute the `CodePrinterAdder` class to generate instrumented Java code.
   - Run the `dynamic_testing` class to automatically generate test cases and verify Java code dynamically.
3. **View the Output**:
   - If path verification succeeds, the tool outputs the verified path and the corresponding test case.
   - If verification fails, it outputs the failing path along with a counterexample, which can help with debugging and correction.

------

##  Dependencies

- [JavaParser](https://javaparser.org/): Used to parse and manipulate Java abstract syntax trees.
- [Z3 SMT Solver](https://github.com/Z3Prover/z3): Used to decide the satisfiability of logical formulas.
- Maven: For dependency management and build automation.

------

## Contribution

We welcome contributions to enhance the tool! If you'd like to add new features or fix bugs:

1. Fork this repository.
2. Commit your changes and submit a pull request.

You’re also encouraged to open [issues](https://github.com/your_project/issues) to report bugs or suggest improvements.

------

##  Contact

For questions, feedback, or collaboration, please contact us via the project homepage or email.
 Thank you for your interest and support in **TBFV4J-CSC**!

------


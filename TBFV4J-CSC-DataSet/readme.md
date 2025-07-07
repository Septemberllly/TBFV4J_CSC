# TBFV4J-CSC-DataSet

To comprehensively evaluate the practical effectiveness of the proposed tool **TBFV4J-CSC**, we constructed a dedicated dataset named **TBFV4J-CSC-DataSet**. This dataset contains a collection of representative Java programs that cover diverse functionalities and testing scenarios. It is designed to validate the functional integrity and test effectiveness of the tool, and to support experimental studies involving the CSC criterion and automatic test case generation algorithms.

---

##  Dataset Structure

The `TBFV4J-CSC-DataSet` folder contains **14 testing programs**, each consisting of the following components:

- A well-defined Functional Scenario Form (FSF);
- A correctly implemented Java program (located in the `1.0` subfolder);
- Several manually created program variants (mutants) with semantic faults injected by researchers.

---

## Mutation Operator Design

We defined and applied four categories of mutation operators in this dataset:

- **Logical Operators**
- **Comparative Operators**
- **Arithmetic Operators**
- **Conditional Statement Structural Mutations**

These mutation strategies aim to cover common patterns of semantic defects and are highly representative for test generation and fault detection evaluation.

**Table I: The Defined Mutation Operators**

| **Mutation Type**         | **Original Operator**                         | **Mutated Operators**                |
| ------------------------- | --------------------------------------------- | ------------------------------------ |
| **Logical**               | &&                                            | \|\|                                 |
|                           | \|\|                                          | &&                                   |
|                           | a                                             | !a                                   |
| **Comparative**           | <=                                            | <                                    |
|                           | >=                                            | >                                    |
|                           | <                                             | <=                                   |
|                           | >                                             | >=                                   |
|                           | ==                                            | !=                                   |
|                           | !=                                            | ==                                   |
| **Arithmetic**            | +                                             | -                                    |
|                           | -                                             | +                                    |
| **Conditional Statement** | Condition Insertion/Removal    eg:if(n%i==0)  | eg:if(n%i==0  && i!=500000)          |
|                           | Statement Insertion/Removal    eg:statement1; | eg:if (condition) {statement1};      |
|                           | Nested Condition Injection    eg:if (x > 0)   | eg:if (x > 0) { if (x != 10) {...} } |

---

##  Why Not Use Existing Mutation Tools?

We did not adopt existing mutation generation tools such as **PIT** or **MuJava**, for the following reasons:

1. These tools lack precise control over the mutation locations and the semantic nature of injected faults;
2. Automatically generated mutants often include a large number of **equivalent mutants**, i.e., program variants whose behavior is indistinguishable from the original and cannot be detected by any test case.

Therefore, we opted for a **manual design and injection of semantic faults** by researchers to ensure that each mutant is meaningful. This approach allows us to evaluate whether TBFV4J-CSC can:

- Generate guided and effective test cases;
- Accurately detect semantic faults;
- Outperform TBFV4J-Ran in exploring representative program execution paths.

---

##  Functionality Description

The dataset includes a `Functionality.txt` file, which provides a brief description of each program's intended functionality and design purpose. Reviewing this file can help users quickly understand the behavioral goals of each sample program, thereby improving testing efficiency and debugging effectiveness.

---

We welcome researchers to reference, reproduce, or extend this dataset. If you have any questions or suggestions during use, please feel free to submit an issue or get in touch with us.

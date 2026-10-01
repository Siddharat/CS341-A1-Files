# CS341 Assignment 1 — Software Quality and Testing

Group 5's CS341 Assignment 1 submission covers unit test design, defect tracking, and code coverage for two small Java applications. The tests use JUnit 5; each application is a separate Maven project with JaCoCo coverage reporting.

## What's in the repository

- **Section A — Employee rating:** Tests the provided `Employee` class across rating thresholds, bonus eligibility, input validation, and summary formatting. The production class was left unchanged.
- **Section B — Car park overstay charge:** Tests parking charges and clamping rules for cars and trucks, visitor and resident permits, valid hour ranges, and invalid inputs. The implementation contains the fixes identified during testing.
- **Assignment evidence:** The [report](<CS341 A1 Files/CS341_A1_Report_Group5.pdf>), [unit test plan](<CS341 A1 Files/CS341_A1_UTP_Group5.xlsx>), and [defect tracker](<CS341 A1 Files/CS341_A1_DefectTracker_Group5.xlsx>) are in `CS341 A1 Files/`.

The Java projects are under [`CS341 A1 Files/CS341_A1_Java_Group5/CS341_A1_Java_Group5/`](<CS341 A1 Files/CS341_A1_Java_Group5/CS341_A1_Java_Group5/>):

```text
CS341 A1 Files/
├── CS341_A1_Report_Group5.pdf
├── CS341_A1_UTP_Group5.xlsx
├── CS341_A1_DefectTracker_Group5.xlsx
└── CS341_A1_Java_Group5/CS341_A1_Java_Group5/
    ├── section-a-employee-rating/
    │   ├── pom.xml
    │   └── src/{main,test}/java/fj/usp/cs341/sectiona/
    └── section-b-overstay-charge/
        ├── pom.xml
        └── src/{main,test}/java/fj/usp/cs341/sectionb/
```

## Run the tests

Install **JDK 17 or newer** and **Apache Maven**. From the repository root, run:

```sh
mvn -f "CS341 A1 Files/CS341_A1_Java_Group5/CS341_A1_Java_Group5/section-a-employee-rating/pom.xml" clean verify
mvn -f "CS341 A1 Files/CS341_A1_Java_Group5/CS341_A1_Java_Group5/section-b-overstay-charge/pom.xml" clean verify
```

Each command runs its JUnit tests and generates a JaCoCo report at that project's `target/site/jacoco/index.html`. The repository also includes saved [Section A](<CS341 A1 Files/CS341_A1_Java_Group5/CS341_A1_Java_Group5/section-a-employee-rating/jacoco-report/index.html>) and [Section B](<CS341 A1 Files/CS341_A1_Java_Group5/CS341_A1_Java_Group5/section-b-overstay-charge/jacoco-report/index.html>) coverage reports. Their recorded results show **100% instruction and branch coverage** for both production classes.

## Testing approach

The test cases use equivalence partitioning and boundary value analysis. Section A checks scores around 0, 50, 70, 85, and 100, along with invalid names and scores. Section B checks charge bands at 4/5, 12/13, and 48/49 hours, as well as vehicle and permit validation. See the [unit test plan](<CS341 A1 Files/CS341_A1_UTP_Group5.xlsx>) for expected results and the [defect tracker](<CS341 A1 Files/CS341_A1_DefectTracker_Group5.xlsx>) for the bugs found during testing.

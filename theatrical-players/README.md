# **Theatrical Players Refactoring Kata**

The Theatrical Players Refactoring Kata is a practical exercise inspired by Martin Fowler's *Refactoring* book. It challenges you to improve the design of a small system while maintaining its existing functionality. This kata focuses on separating calculation logic from formatting logic, making the code cleaner and easier to extend.

---

## **Objective**

The goal of this kata is to:
- Refactor the code to separate responsibilities (calculation vs. formatting).
- Produce both plain-text and HTML customer statements.
- Practice refactoring techniques such as method extraction and replacing temporary variables with queries.
- Ensure that all functionality is preserved by using approval tests.

---

## **Scenario**

The code calculates customer statements for a troupe of theatrical players performing Shakespearean plays. Customers receive statements detailing:
1. Plays they attended.
2. Audience size for each play.
3. Volume credits earned (used for discounts).

The system must support generating these statements in both **plain text** and **HTML** formats.

You’ll find that the current implementation has mixed responsibilities, making it hard to extend. Your task is to refactor it into a cleaner design.

---

## **Getting Started**

### **Prerequisites**
- **Java Development Kit (JDK):** Ensure JDK 21 is installed.
- **Build Tool:** Gradle or Maven.
- **IDE:** IntelliJ IDEA or your preferred Java IDE.

---

### **Setup Instructions**
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd theatrical-players
   ```
2. Open the `theatrical-players` folder in your IDE.

3. Run the provided tests to verify the current functionality:
   ```bash
   mvn test
   ```
   or
   ```bash
   ./gradlew test
   ```

4. Review the starting code and test data provided:
    - **JSON Files**:
        - `plays.json`: Contains details about the plays (e.g., name, type).
        - `performances.json`: Contains performance details (e.g., audience size).
    - **Tests**: Approval tests verify the generated statements.

---

## **The Refactoring Process**

### **Step 1: Understand the Current Design**
- Review the code for:
    - **Long Methods**: Identify methods with mixed responsibilities.
    - **Temporary Variables**: Look for variables with long scopes and replace them with queries where appropriate.
    - **Tight Coupling**: Note where calculation and formatting logic are intertwined.

- Run the tests to ensure they cover the functionality.

---

### **Step 2: Add Missing Tests (if applicable)**
- Ensure you have approval tests that verify:
    - Correct statements for valid play types.
    - Error handling for invalid play types (e.g., unknown play types).
    - Both plain-text and HTML outputs.

---

### **Step 3: Extract Methods**
- Refactor the `statement` method:
    - Extract logic for calculating totals into separate methods.
    - Extract logic for formatting into separate methods (e.g., `textStatement`, `htmlStatement`).

---

### **Step 4: Introduce Classes**
- Create new classes to handle distinct responsibilities:
    - `StatementCalculator`: Handles calculation logic.
    - `StatementFormatter`: Handles formatting logic.
    - `Play`: Represents play data (e.g., name, type).
    - `Performance`: Represents performance data (e.g., audience size).

---

### **Step 5: Replace Temporary Variables with Queries**
- Identify temporary variables with long scopes and replace them with methods that compute the values when needed.

Example:
```java
// Replace this temporary variable
double volumeCredits = 0;
// With a method
double getVolumeCredits(Performance performance) { ... }
```

---

### **Step 6: Verify Output Formats**
- Ensure the refactored code can generate:
    - Plain-text statements.
    - HTML statements.

Run the tests frequently to verify the correctness of both formats.

---

### **Step 7: Clean Up**
- Remove any unused variables or methods.
- Ensure all classes and methods have clear, meaningful names.

---

## **Reflection Questions**

1. **Code Understanding:**
    - What design smells did you notice in the original implementation?
    - How did separating calculation and formatting logic improve the design?

2. **Refactoring Process:**
    - Were there any points where you introduced errors? How did you fix them?
    - How did replacing temporary variables with queries impact the design?

3. **Output Formats:**
    - Is the system now flexible enough to support additional formats (e.g., XML, JSON)?
    - How would you explain the value of your refactoring work to a client or manager?

---

## **Running Tests**

Run the test suite to verify your changes:
```bash
mvn test
```
or
```bash
./gradlew test
```

Ensure all tests pass before committing your changes.

---

## **Additional Resources**

- [Theatrical Players Kata Description](https://martinfowler.com/books/refactoring.html) (from *Refactoring* by Martin Fowler)
- [Approval Testing for Legacy Code](https://approvaltests.com/)
- [Emily B’s Refactoring Demo](https://www.youtube.com/watch?v=<insert-link>)

---

## **Credits**
This kata is inspired by Martin Fowler’s *Refactoring* book and Emily B’s video walkthroughs. Special thanks to both for their contributions to the software development community.

---

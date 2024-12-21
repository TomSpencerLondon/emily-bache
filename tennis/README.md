# **Tennis Refactoring Kata**

The Tennis Refactoring Kata is an engaging exercise designed to help you practice improving code quality in an existing system. It challenges you to refactor a poorly written tennis scoring system while maintaining its functionality and behavior.

---

## **Objective**

The goal is to refactor the `TennisGame` code to:
- Simplify the design.
- Improve readability and maintainability.
- Ensure that all tests continue to pass throughout the process.

This exercise simulates a real-world scenario where you inherit code from another developer and are tasked with tidying it up before handing it off to a client or colleague.

---

## **Scenario**

Imagine you are working for a consultancy, and one of your colleagues has partially completed a tennis scoring system for a client. The functionality is working, but the code quality is poor. Your boss has asked you to spend some time cleaning up the code so the client can be billed for the remaining hours.

You have a comprehensive test suite that ensures the functionality is preserved while you refactor the code.

---

## **Getting Started**

### **Prerequisites**
- **Java Development Kit (JDK):** Ensure you have JDK 21 installed.
- **Build Tool:** Maven or Gradle, depending on your setup.
- **IDE:** IntelliJ IDEA or your preferred Java IDE.

---

### **Setup Instructions**
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd tennis
   ```
2. Open the `tennis` folder in your IDE.

3. Run the provided tests to verify the current functionality:
   ```bash
   mvn test
   ```
   or
   ```bash
   ./gradlew test
   ```

---

## **The Refactoring Process**

### **Step 1: Review the Code**
1. Open the `TennisGame` classes in your IDE.
2. Identify design smells such as:
    - **Long methods**: Methods performing multiple responsibilities.
    - **Hardcoded values**: E.g., player names like `"player1"` and `"player2"`.
    - **Poor naming**: Ambiguous or unclear variable and method names.

---

### **Step 2: Start with Small, Safe Refactorings**
- **Extract Methods:**
    - Break down long methods into smaller, focused methods with descriptive names.
    - Example: Extract score calculation logic into a separate method.

- **Rename Variables:**
    - Replace vague or misleading names with clear, meaningful names.
    - Example: Rename variables like `p1` and `p2` to `player1Score` and `player2Score`.

- **Fix Hardcoded Values:**
    - Replace hardcoded values (e.g., `"player1"` and `"player2"`) with parameters or constants.
    - Update the tests to validate this change.

---

### **Step 3: Address Larger Design Issues**
- **Apply Object-Oriented Principles:**
    - Encapsulate behaviors specific to players or scores into separate classes or methods.
    - Consider introducing a `Player` class to hold player-related information (e.g., name and score).

- **Simplify Conditional Logic:**
    - Refactor complex conditionals for determining the score (e.g., `"Deuce"`, `"Advantage"`, `"Win for X"`) into methods or strategies.
    - Example: Use enums or constants to represent scores like `Love`, `Fifteen`, `Thirty`, `Forty`.

---

### **Step 4: Refactor Incrementally**
- Run tests frequently to ensure no functionality is broken.
- Use your IDE’s refactoring tools (e.g., Extract Method, Rename) to automate changes safely.
- Commit after each small, safe change to track progress and maintain a history of working states.

---

### **Step 5: Improve Tests**
- Add new tests to verify edge cases (e.g., ties, "Deuce", and "Advantage").
- Use descriptive test names to document what each test is verifying.

---

## **Reflection Questions**

After completing the kata, reflect on the following:
1. **Tests:**
    - How did having comprehensive tests affect your confidence while refactoring?
    - Were there any gaps in the test coverage? How did you address them?

2. **Refactoring Process:**
    - Did you encounter any unexpected challenges while refactoring?
    - Were there opportunities to take smaller steps during refactoring?

3. **Design Improvements:**
    - How did the final design compare to the original?
    - What would you say to the developer who wrote the original code?

4. **Client Value:**
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

## **Questions to Discuss**
1. Did you make any refactoring mistakes that were caught by the tests?
2. What would you say to the client about the improvements made?
3. How did the tests help guide your refactoring process?

---

## **Additional Resources**
- [Tennis Kata Description](https://sammancoaching.org/kata_descriptions/tennis.html)
- [Refactoring: What You Need to Know](https://youtu.be/K7xSsNpeM8I) - Demo by Emily B
- [Martin Fowler’s Refactoring Techniques](https://refactoring.com)

---

## **Credits**
This kata is inspired by Emily B’s refactoring exercises and is part of her broader collection of coding katas. Special thanks to Emily for making these exercises widely accessible.

---

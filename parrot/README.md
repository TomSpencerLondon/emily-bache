# **Parrot Refactoring Kata**

The Parrot Refactoring Kata is a practical exercise designed to help you practice and refine your refactoring and software design skills. It focuses on replacing type codes with polymorphism, a classic refactoring technique, and demonstrates how to incrementally improve the codebase while maintaining existing functionality.

---

## **Objective**

The goal of this kata is to refactor the `Parrot` class, which currently contains a type code and a large switch statement. By refactoring this code, you will:
- Replace type codes with polymorphic behavior.
- Introduce subclasses for better organization.
- Implement factory methods to simplify object creation.
- Practice safe, incremental refactoring techniques.

---

## **Getting Started**

### Prerequisites
- **Java Development Kit (JDK):** Ensure you have JDK 21 installed.
- **Build Tool:** Maven or Gradle, depending on your setup.
- **IDE:** IntelliJ IDEA or your preferred Java IDE.

---

### **Setup Instructions**
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd parrot
   ```
2. Open the `parrot` folder in your IDE.

3. Run the provided tests to verify the current functionality:
   ```bash
   mvn test
   ```
   or
   ```bash
   ./gradlew test
   ```

4. Review the starting code in `Parrot.java` and `ParrotTest.java` to understand its current structure.

---

## **The Refactoring Process**

### **Step 1: Analyze the Code**
1. Identify the main code smell: **Type code with repeated switch statements**.
2. Understand how each parrot type behaves and note the switch statement in `Parrot.java`.

### **Step 2: Refactor the Constructor**
- Replace the constructor with a **factory method** to prepare for introducing subclasses.
- Example:
  ```java
  public static Parrot createParrot(ParrotType type, int numberOfCoconuts, double voltage, boolean isNailed) {
      switch (type) {
          case EUROPEAN: return new EuropeanParrot();
          case AFRICAN: return new AfricanParrot(numberOfCoconuts);
          case NORWEGIAN_BLUE: return new NorwegianBlueParrot(voltage, isNailed);
          default: throw new IllegalArgumentException("Invalid parrot type");
      }
  }
  ```

### **Step 3: Introduce Subclasses**
- Create subclasses for each parrot type:
    - `EuropeanParrot`
    - `AfricanParrot`
    - `NorwegianBlueParrot`
- Move specific behaviors from the `Parrot` class into the relevant subclass.

### **Step 4: Push Down Methods**
- Use your IDE’s **"Push Members Down"** refactoring to move type-specific methods (e.g., `getSpeed`) into the respective subclasses.

### **Step 5: Simplify the Superclass**
- Remove the switch statements and type code from the `Parrot` superclass.
- Ensure that `Parrot` becomes a simple abstract class or an interface with shared behavior.

### **Step 6: Refactor Tests**
- Update `ParrotTest` to use the factory method and verify that all behaviors remain intact.

---

## **Running Tests**
After each refactoring step, ensure the tests pass:
```bash
mvn test
```
or
```bash
./gradlew test
```

---

## **Key Refactoring Techniques**
- **Replace Type Code with Polymorphism:** Eliminate the switch statements and type codes by creating subclasses for each behavior.
- **Introduce Factory Method:** Simplify object creation and improve flexibility for adding new parrot types.
- **Push Members Down:** Move behavior-specific methods into subclasses to adhere to the **Single Responsibility Principle**.
- **Safe Refactorings:** Use small, incremental changes to maintain functionality.

---

## **Reflection Questions**
1. How did replacing type codes with polymorphism improve the design?
2. Did the refactoring process reveal any unexpected edge cases or bugs?
3. How could you make the code even more flexible for future parrot types?
4. What did you learn about the importance of testing during refactoring?

---

## **Additional Resources**
- **Video Walkthrough by Emily B:** [Parrot Refactoring Kata Demo](https://www.youtube.com/watch?v=<insert-link>)
- **Refactoring Techniques**: Learn more about these techniques in Martin Fowler’s book, *Refactoring: Improving the Design of Existing Code*.
- **Emily B’s Patreon**: [Support Emily’s work on Patreon](https://www.patreon.com/EmilyBache).

---

## **Credits**
This kata is inspired by Emily B’s work on refactoring katas and her video walkthroughs. Special thanks to Emily for making these exercises accessible and practical.

---
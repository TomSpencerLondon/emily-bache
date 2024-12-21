Here’s a clear and detailed README for the **Gilded Rose Kata**:

---

# **Gilded Rose Refactoring Kata**

The Gilded Rose Refactoring Kata is a popular exercise designed to challenge your ability to work with legacy code. It provides a real-world scenario where you need to refactor a messy, untested codebase while maintaining its existing functionality.

---

## **Objective**

The goal of this kata is to:
- Understand and work with a complex legacy codebase.
- Refactor the code to improve readability and maintainability.
- Ensure all functionality is preserved by running the provided tests.

---

## **Scenario**

You are tasked with maintaining and improving the Gilded Rose inventory system. The system manages a variety of items with unique update rules. The code currently works but is difficult to understand and modify.

Your job is to refactor the code to make it easier to maintain while ensuring the behavior of the system remains unchanged.

---

## **Key Rules for the Gilded Rose Inventory**

1. All items have a `sellIn` value (days until the item must be sold) and a `quality` value.
2. At the end of each day:
    - The `sellIn` value decreases by 1.
    - The `quality` value decreases by 1 unless special rules apply.
3. Special rules for specific items:
    - **"Aged Brie"**:
        - Increases in quality as it gets older.
    - **"Backstage passes"**:
        - Quality increases as the `sellIn` value approaches zero.
        - Quality drops to 0 after the concert (`sellIn` < 0).
    - **"Sulfuras"**:
        - Never decreases in quality or `sellIn`.
    - **"Conjured" items**:
        - Degrade in quality twice as fast as normal items.

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
   cd gilded-rose-kata
   ```
2. Open the `gilded-rose-kata` folder in your IDE.

3. Run the provided tests to verify the current functionality:
   ```bash
   ./gradlew test
   ```
   or
   ```bash
   mvn test
   ```

4. Review the starting code in `GildedRose.java` and `Item.java`.

---

## **The Refactoring Process**

### **Step 1: Understand the Code**
1. Review the existing logic in `GildedRose.java` and identify areas for improvement:
    - Long, nested conditionals.
    - Lack of modularization.
    - Hardcoded rules.

2. Run the tests frequently to confirm the behavior of the system.

---

### **Step 2: Add Unit Tests (if missing)**
- If no unit tests are provided, write tests to verify the behavior of:
    - Normal items.
    - Aged Brie.
    - Backstage passes.
    - Sulfuras.
    - Conjured items.

- Example Test:
  ```java
  @Test
  void testAgedBrieIncreasesInQuality() {
      Item[] items = new Item[]{new Item("Aged Brie", 10, 20)};
      GildedRose app = new GildedRose(items);
      app.updateQuality();
      assertEquals(21, app.items[0].quality);
  }
  ```

---

### **Step 3: Refactor Incrementally**
- **Extract Methods:**
    - Break down large methods into smaller, focused methods.
    - Example: Extract logic for each item type into separate methods.

- **Introduce Classes:**
    - Consider creating separate classes for each item type (e.g., `AgedBrie`, `BackstagePass`, `Sulfuras`).
    - Use polymorphism to replace conditional logic with object-oriented behavior.

- **Clean Up Code:**
    - Remove redundant comments.
    - Use meaningful variable and method names.

---

### **Step 4: Verify Changes**
1. Run the tests after every small refactoring step.
2. Ensure all tests pass to confirm the behavior remains unchanged.

---

### **Step 5: Optimize for Future Maintenance**
- Add comments or documentation for any complex areas of the code.
- Ensure the system is flexible enough to support new item types without extensive modifications.

---

## **Running the TextTest Fixture**

The Gilded Rose Kata includes a TextTest fixture for additional testing. Use the following commands to run it:

1. **Run the TextTest Fixture:**
   ```bash
   ./gradlew -q text
   ```

2. **Specify Number of Days:**
   For example, to simulate 10 days:
   ```bash
   ./gradlew -q text --args 10
   ```

3. **Test Using Approval Tests:**
   Set up [TextTest](../texttests/README.md) to run approval tests for the system.

---

## **Reflection Questions**

1. **Code Understanding:**
    - What design smells did you identify in the original code?
    - How did the tests help you understand the code?

2. **Refactoring Process:**
    - What small refactoring steps did you take to avoid breaking the code?
    - How did introducing polymorphism improve the design?

3. **Future Maintenance:**
    - Is the code now easier to extend for new item types?
    - How would you explain your improvements to a colleague or client?

---

## **Additional Resources**
- [Emily B’s Video on Gilded Rose Kata](https://www.youtube.com/watch?v=<insert-link>)
- [Martin Fowler’s Refactoring Techniques](https://refactoring.com)

---

## **Credits**
This kata is inspired by the original Gilded Rose Kata and Emily B’s refactoring exercises. Special thanks to Emily for her educational videos and contributions to the software development community.

---

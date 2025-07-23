
## Assignment \#2: OOP Principles & Algorithm Efficiency

**Objective:** This assignment assesses your understanding and application of core Object-Oriented Programming (OOP) principles (Encapsulation, Inheritance, Polymorphism, Abstraction) and fundamental concepts of Algorithm Analysis using Big-O Notation.

**Instructions:**

  * For coding tasks, create new Java classes in separate files as needed. Include a `main` method to demonstrate your solution.
  * For conceptual questions, provide clear and concise explanations.
  * Submit all source code files and a single document (PDF or Markdown) containing your answers to conceptual questions and explanations.

-----

### Task 1: Encapsulating a `Student` (OOP - Encapsulation)

**Goal:** Design a `Student` class that properly protects its data.

1.  **Create a `Student` class:**

      * It should have **private** fields: `name` (String) and `studentId` (String).
      * Implement a **constructor** to initialize both fields.
      * Provide **public getter methods** for `name` and `studentId`.
      * **Do not** provide any setter methods for these fields.

2.  **Demonstrate:** In a `main` method, create a `Student` object. Try to directly access or modify its private fields (e.g., `student.name = "New Name";`) and observe the compile-time error. Then, use the getter methods to print the student's details.

-----

### Task 2: Basic `Vehicle` Hierarchy (OOP - Inheritance)

**Goal:** Create a simple inheritance structure.

1.  **Create a `Vehicle` class:**

      * Field: `brand` (String).
      * Constructor.
      * Method: `startEngine()` (prints "Engine started.").

2.  **Create a `Car` class:**

      * **Extends `Vehicle`**.
      * Additional field: `model` (String).
      * Constructor: Initialize `brand` (using `super()`) and `model`.
      * Override `startEngine()`: Print "Car engine started with a turn of the key."

3.  **Demonstrate:** In a `main` method, create instances of both `Vehicle` and `Car`. Call `startEngine()` on both and observe the output.

-----

### Task 3: Printable Objects (OOP - Polymorphism & Abstraction)

**Goal:** Use an interface to define common behavior for different objects.

1.  **Create an `IPrintable` interface:**

      * Define one abstract method: `void printInfo()`.

2.  **Create two classes:**

      * **`Book` class:**
          * Implements `IPrintable`.
          * Field: `title` (String).
          * Constructor.
          * Implement `printInfo()`: Prints "Book Title: [title]".
      * **`Movie` class:**
          * Implements `IPrintable`.
          * Field: `director` (String).
          * Constructor.
          * Implement `printInfo()`: Prints "Movie Director: [director]".

3.  **Demonstrate:** In a `main` method, create an `ArrayList` of `IPrintable` objects. Add instances of `Book` and `Movie`. Iterate through the list and call `printInfo()` on each object.

-----

### Task 4: Identifying Big-O for Code Snippets (Big-O Notation)

**Goal:** Determine the Big-O time complexity for simple code structures.

  * For each code snippet below, state its Big-O time complexity in terms of `n`.

    1.  ```java
        int result = 5 * 10;
        System.out.println(result);
        ```
    2.  ```java
        for (int i = 0; i < n; i++) {
            System.out.println("Processing item " + i);
        }
        ```
    3.  ```java
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                System.out.println("Pair: " + i + ", " + j);
            }
        }
        ```
    4.  ```java
        // Assume 'arr' is a sorted array of size 'n'
        int target = 10;
        int low = 0;
        int high = n - 1;
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (arr[mid] == target) break;
            if (arr[mid] < target) low = mid + 1;
            else high = mid - 1;
        }
        ```

-----

### Task 5: Algorithm Efficiency Analysis (Big-O Application)

**Goal:** Analyze and compare the Big-O time complexity of different approaches to a simple array processing task.

  * Consider a **non-sorted** array of `n` integers.

    1.  **Algorithm A:** Find the *maximum* value in the array by iterating through each element once.
        ```java
        // Example structure for Algorithm A
        int max = arr[0];
        for (int i = 1; i < n; i++) {
            if (arr[i] > max) {
                max = arr[i];
            }
        }
        ```
    2.  **Algorithm B:** Calculate the *sum of all unique pairs* of elements in the array (e.g., `arr[0]+arr[1]`, `arr[0]+arr[2]`, `arr[1]+arr[2]`, but not `arr[1]+arr[0]` or `arr[0]+arr[0]`).
        ```java
        // Example structure for Algorithm B
        long sumOfUniquePairs = 0;
        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j < n; j++) { // Notice j starts from i + 1
                sumOfUniquePairs += arr[i] + arr[j];
            }
        }
        ```

  * **Questions:**

      * What is the Big-O time complexity of **Algorithm A**?
      * What is the Big-O time complexity of **Algorithm B**?
      * For a very large `n`, which algorithm would you consider more efficient, and why?

-----

### Task 6: Optimizing a Simple Operation (Big-O Optimization)

**Goal:** Identify inefficient code and propose an optimized solution based on Big-O principles.

  * Consider the following method designed to count how many pairs of elements in an array `arr` (of size `n`) are identical.

    ```java
    public static int countIdenticalPairs(int[] arr) {
        int count = 0;
        for (int i = 0; i < arr.length; i++) {
            for (int j = 0; j < arr.length; j++) {
                if (i != j && arr[i] == arr[j]) { // Checks all pairs, including (A,B) and (B,A) separately
                    count++;
                }
            }
        }
        return count / 2; // Divide by 2 because each pair (A,B) is counted twice
    }
    ```

  * **Questions:**

    1.  What is the **Big-O time complexity** of the `countIdenticalPairs` method as currently written?
    2.  Propose a **more efficient version** of this method. You don't need to write the full code, but describe your approach in detail. (Hint: Consider how you could use a data structure to keep track of seen elements or their counts.)
    3.  What would be the **Big-O time complexity** of your proposed optimized approach?

-----

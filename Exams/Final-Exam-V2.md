***

# Final Exam: Programming Algorithms & Patterns V2

***

### **Question 1 (5 points)**

* What is a method reference in Java?  
* Give an example of using a method reference to print every element of a List<Integer>.

***

### **Question 2 (5 points)**

* What is the difference between the map and filter operations in Java streams?  
* Provide an example where you double every element in an `ArrayList<Integer>` and collect the result.

***

### **Question 3 (10 points)**

* What is a recursive algorithm?

* Write a recursive method (in Java or pseudocode) that sums all the integers in an array.

* Clearly identify the base case and recursive case in your solution.

* Briefly explain one advantage and one drawback of using recursion in this example.

***

### **Question 4: SOLID Principles – Open/Closed Principle (10 points)**

* State the Open/Closed Principle (OCP) and describe, in your own words (no code required),
  how you would apply this principle if asked to add new discount types to an online store application.

***

### **Question 5: Implementing a Stack Using Linked List (10 points)**

* Suppose you need to implement a stack with push and pop operations using your own singly-linked list.
* Which end of the list would you use for these operations, and why?  
* Write pseudocode or Java snippets for push and pop.

***

### **Question 6: Interface Segregation Principle & Reusability (10 points)**

* Explain the Interface Segregation Principle (ISP).  
* Give a real-world scenario where a “fat” interface would be problematic, and how breaking it up improves code quality or reusability.

***

### **Question 7 (10 points)**

* A map in Java (e.g., Map<Integer, String>) holds student IDs as keys and student names as values.

* Describe how you would use an Iterator to print every student ID and name pair stored in a map.
*  Write a Java code snippet that demonstrates this process.

***

### **Question 8 (10 points)**

* Given this list:
    ```java
    List<Double> temps = Arrays.asList(98.6, 99.5, 97.8, 102.1, 99.9);
    ```
* Write a stream operation (with lambda, map, and filter as appropriate) that finds and prints all temperatures above 99.0, converting them to Celsius.

***

### **Question 9 (10 points)**

* Given this list:
    ```java
    List<String> animals = Arrays.asList("tiger", "giraffe", "goat", "sheep", "lion");
    ```
* Write a stream operation that capitalizes every animal name starting with 'g' and prints each one.

***

### **Question 10 (5 points)**

* How would you use a comparator (with lambda) to sort a list of `Employee` objects by their name alphabetically?

***

### **Question 11: Iteration and Collection API (5 points)**

* Java’s Set interface does not guarantee ordering.  
* Write a for-each loop that prints every value in a `Set<String>`.  
* Why is a for-each loop often preferred over manual index-based traversal?

***

### **Question 12 (10 points)**

* You are building a calculation service app that supports multiple algorithms, such as “sum all numbers,” “multiply all numbers,” and “find the median.”
* Describe how you would design this system to make it easy to add new algorithms in the future without modifying existing code.
* In your answer, explain how using interfaces and composition can help achieve this flexibility.
* Optionally, provide a brief interface definition and describe how concrete algorithm classes would implement it.
***

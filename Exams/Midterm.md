# Midterm Exam: Programming Algorithms & Patterns

### Question 1: OOP Principles (10 points)
* What is the key difference between method overriding and method overloading in Java?
* Consider a Shape class with a single method calculateArea(). Describe how you would create a Circle class that inherits from Shape and overrides the calculateArea() method to provide a specific implementation.

### Question 2: Big-O Notation (10 points)
Determine the Big-O time complexity for the following code snippet in terms of n. Justify your answer in one sentence.
```java
// Assume 'arr' is an array of size 'n'
for (int i = 0; i < n; i++) {
    for (int j = 0; j < 10; j++) {
        System.out.println("Processing: " + arr[i]);
    }
}
```
### Question 3: Recursion (10 points)
* Provide a recursive implementation in pseudo-code or a detailed description for a function calculatePower(base, exponent)
  that calculates base to the power of exponent (assume exponent is a non-negative integer).
* Be sure to identify the Base Case and the Recursive Step.

### Question 4: MyLinkedList Implementation (10 points)
* You are implementing your own MyLinkedList class as a singly linked list. 
* Describe the conceptual steps involved in implementing the addLast(T element) method.
* Your answer should focus on how you handle the edge case of an empty list and how you update the necessary pointers to append a new node to the end of the list.

### Question 5: Stack Implementation (10 points)
* You have successfully implemented your own MyLinkedList class.
* How would you use your MyLinkedList as the underlying data structure for a MyStack?
* Which MyLinkedList methods would you use to implement the push() and pop() operations of your stack, and why?

### Question 6: Algorithm Analysis (10 points)
* A program needs to perform frequent random access (get(index)) to its elements, but rarely adds or removes elements from the middle.
* Based on this access pattern, would an ArrayList or a LinkedList be a better choice?

### Question 7: Data Structures Application (10 points)
* You are designing a simple "Undo" feature for a text editor. 
* Every time a user makes a change, you need to store the previous version of the text.
* The most common operations are adding a new version and retrieving the most recent version (the one to "undo").
* Which linear data structure (Stack or Queue) would be most appropriate for this task?
* Briefly explain your choice by referencing its core principle (LIFO or FIFO).
* Justify your answer by referencing the Big-O time complexity of the relevant operation for both data structures.



## **Lab11: Lambda Expressions**

### **Instructions:**  
Implement each task concisely using lambda expressions. Demonstrate each with minimal complete code snippets or a main method.

### **Task 1: Simple Lambda for Runnable and Invocation**

Write a lambda expression implementing Runnable that prints "Hello from Runnable!" when run. Then, create a new Thread using this Runnable, start the thread, and ensure the message is printed.

Requirements:

- Use a lambda expression to instantiate Runnable.

- Start the thread to execute the lambda.

- Print a confirmation message inside the lambda.


### **Task 2: Comparator with Lambda**

Given a list of `String`. Sort it by their length using a lambda `Comparator`.

```java
List words = Arrays.asList("apple", "pear", "banana", "fig");

```

### **Task 3: Consumer with Lambda**

Use a `Consumer` lambda to print each element in a string list prefixed by `"Item: "`.

```java

List list = Arrays.asList("A", "B", "C");

```

### **Task 4: Function with Lambda**

Write a `Function` lambda that returns the length of a string. Use it to map a list of strings to their lengths.

```java
Function toLength = String::length;
List list = Arrays.asList("hello", "world");

```

### **(Optional) Task 5: Lambda with Multiple Statements**

Write a lambda for `Runnable` with multiple statements: print start, sleep 1 second, then print done.



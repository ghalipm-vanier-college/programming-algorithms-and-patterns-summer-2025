
## Lecture: Lambda Expressions and Stream Processing in Java

### 1. Lambda Expressions: The Basics

**Definition:**  
A lambda expression is an *anonymous function*—a block of code you can pass around and execute, 
introduced in Java 8 for concise, functional-style programming.

### Java Streams should be used when:
```java
List<Integer> numbers = Arrays.asList(1, 2, 3, 4);
```
* Filtering: selecting elements from a collection based on a specific condition.
```java
List<Integer> evenNumbers = numbers.stream().filter(number -> number%2==0).toList();
```
* Mapping: Transforming each element in a collection into a different element.
  ```java
  List<Integer> squaredNumbers = numbers.stream().map(n -> n * n).toList();
  ```
* Reducing: Aggregating elements of a collection into a single result (e.g., sum, count, min, max).
```java
    int sum = numbers.stream().reduce(0, Integer::sum);
```

* Collecting: Gathering the results of stream operations into a new collection or data structure.

 ```java

    List<String> words = Arrays.asList("hello", "world", "java", "hello");
    Set<String> uniqueWords = words.stream().collect(Collectors.toSet());
```
* Sorting: Ordering elements within a stream.
```java
    List<String> unsortedNames = Arrays.asList("Charlie", "Alice", "Bob");
    List<String> sortedNames = unsortedNames.stream()
                                             .sorted()
                                             .collect(Collectors.toList());
```
* Grouping and Partitioning: Organizing elements based on specific criteria.
  ```java
      List<Person> people = Arrays.asList(
        new Person("Alice", 30),
        new Person("Bob", 25),
        new Person("Charlie", 30)
  );
    Map<Integer, List<Person>> peopleByAge
        = people.stream().collect(Collectors.groupingBy(Person.age));
   Map<Integer, List<Person>> peopleByName
        = people.stream().collect(Collectors.groupingBy(Person.name));
  ```
  
**Syntax:**  
```java
(parameters) -> expression
// or
(parameters) -> { statements }
```
- The `->` is called the "arrow operator".

**Examples:**
- No parameters:  `() -> 42`
- One parameter:  `(x) -> x * 2`
- Multiple parameters:  `(a, b) -> a + b`

**Why Use Lambdas?**
- Eliminates need for trivial anonymous classes.
- Lets you pass code as data (e.g., to methods).
- Enables concise collection processing.

**Functional Interfaces:**  
- Lambdas work only with *functional interfaces* (interfaces with a single abstract method).
- Examples: `Runnable`, `Comparator`, `Consumer`, `Function`

Here are the most representative examples for the Java functional interfaces: **Runnable**, **Comparator**, **Consumer**, and **Function**. Each example is concise and demonstrates typical usage.

### 1. Runnable Example

```java
public class RunnableExample {
    public static void main(String[] args) {
        // Runnable using a lambda expression to print a message
        Runnable task = () -> System.out.println("Runnable is running in thread: " + Thread.currentThread().getName());

        // Create and start a thread with the runnable
        Thread thread = new Thread(task);
        thread.start();
    }
}
```
**Explanation:**  
- `Runnable` defines a task to be run asynchronously.
- The `run()` method is implemented via a lambda.
- Thread executes the task printing the current thread name.

### 2. Comparator Example

```java
import java.util.*;

public class ComparatorExample {
    public static void main(String[] args) {
        List fruits = Arrays.asList("Banana", "Apple", "Cherry", "Date");

        // Comparator to sort strings by length, ascending
        Comparator byLength = (s1, s2) -> Integer.compare(s1.length(), s2.length());

        // Sort the list using the comparator
        fruits.sort(byLength);

        System.out.println(fruits); // Output: [Date, Apple, Banana, Cherry]
    }
}
```
**Explanation:**  
- `Comparator` compares two objects to impose an ordering.
- Here, strings are sorted by their length rather than lex order.

### 3. Consumer Example

```java
import java.util.*;
import java.util.function.Consumer;

public class ConsumerExample {
    public static void main(String[] args) {
        List names = Arrays.asList("Alice", "Bob", "Charlie");

        // Consumer to print each name with a greeting
        Consumer greeter = name -> System.out.println("Hello, " + name + "!");

        // Apply the consumer to each element using forEach
        names.forEach(greeter);
    }
}
```
**Explanation:**  
- `Consumer` represents an operation that takes an input and returns nothing.
- Here, it prints a greeting for each name.

### 4. Function Example

```java
import java.util.*;
import java.util.function.Function;
import java.util.stream.Collectors;

public class FunctionExample {
    public static void main(String[] args) {
        List words = Arrays.asList("apple", "banana", "cherry");

        // Function to convert a string to its length
        Function lengthFunction = String::length;

        // Map words to their lengths using the function
        List lengths = words.stream()
                                     .map(lengthFunction)
                                     .collect(Collectors.toList());

        System.out.println(lengths); // Output: [5, 6, 6]
    }
}
```
**Explanation:**  
- `Function` represents a function taking a `T` and returning an `R`.
- Here, it maps strings to their lengths.


### 2. Stream Processing Overview

**What are Streams?**  
A *Stream* represents a sequence of elements supporting sequential and parallel operations. 
They enable *declarative* ("what, not how") data processing—often replacing loops.

**Key Stream Operations:**
- **Creation:**  `Collection.stream()`
- **Intermediate:**  `filter`, `map`, `sorted`
- **Terminal:**  `forEach`, `collect`, `reduce`

**Typical Stream Pipeline:**
```java
list.stream()
    .filter(s -> s.length() > 2)
    .map(String::toUpperCase)
    .sorted()
    .forEach(System.out::println);
```

### 3. Essential, Interview-Ready Patterns

**A. Sorting with Lambdas**
```java
List names = Arrays.asList("Tom", "Jerry", "Anna");
names.sort((a, b) -> a.compareToIgnoreCase(b));
```

**B. Mapping and Filtering**
```java
List nums = Arrays.asList(1, 2, 3, 4);
List evens = nums.stream()
    .filter(n -> n % 2 == 0)
    .collect(Collectors.toList());
```

**C. Collect and Joining**
```java
String result = list.stream()
    .map(String::toUpperCase)
    .collect(Collectors.joining(", "));
```

The difference between **`filter`** and **`map`** operations in Java Streams:

### Filter Example: Keep only even numbers

```java
import java.util.*;
import java.util.stream.Collectors;

public class FilterExample {
    public static void main(String[] args) {
        List numbers = Arrays.asList(1, 4, 7, 8, 10, 13);

        // Filter: keep only even numbers
        List evens = numbers.stream()
                                     .filter(n -> n % 2 == 0)
                                     .collect(Collectors.toList());

        System.out.println("Filtered evens: " + evens);  // Output: [4, 8, 10]
    }
}
```

- **`filter`** keeps elements that satisfy the predicate (`n % 2 == 0`),
- what is filtered is part of the original collection.

### Map Example: Convert each number to its square

```java
import java.util.*;
import java.util.stream.Collectors;

public class MapExample {
    public static void main(String[] args) {
        List numbers = Arrays.asList(1, 4, 7, 8, 10, 13);

        // Map: square each number
        List squares = numbers.stream()
                                       .map(n -> n * n)
                                       .collect(Collectors.toList());

        System.out.println("Mapped squares: " + squares);  // Output: [1, 16, 49, 64, 100, 169]
    }
}
```

- **`map`** `transforms` each element from the source to a new value (`n * n` here).

### Summary

| Operation | What it does                          | Example using `numbers = `            | Result                 |
|-----------|-------------------------------------|------------------------------------------------------|------------------------|
| **filter**| Selects some elements by a predicate| `filter(n -> n % 2 == 0)`                            | ``           |
| **map**   | Transforms elements into new ones   | `map(n -> n * n)`                                    | `[1, 16, 49,two are often used in sequence to select and then transform data efficiently.


**D. Count, Min, Max in One Line**
```java
long count = list.stream().filter(s -> s.startsWith("A")).count();
String minStr = list.stream().min(Comparator.naturalOrder()).orElse("");
```

### 4. Practical Exercises (for active learning)

- Write a lambda to print each string in a list.
- Use a stream to sum even numbers.
- Filter, then sort, a list of custom objects using lambdas and streams.

### 5. Summary Table

| Feature             | Lambda Example                           | Stream Usage Example                  |
|---------------------|------------------------------------------|---------------------------------------|
| Print list          | `l.forEach(x -> System.out.println(x));` | `l.stream().forEach(System.out::println);` |
| Filter              | –                                        | `l.stream().filter(x -> x > 3)`       |
| Map/transform       | –                                        | `l.stream().map(String::length)`      |
| Sort                | `l.sort((a,b)->a-b);`                    | `l.stream().sorted()`                 |

### Key Takeaways

- **Lambda expressions**: Short, "throwaway" code blocks for functional interfaces.
- **Stream API**: Declarative, efficient, and expressive way to handle collections.
- **Best Practice**: Use lambdas for code brevity and clarity, streams for powerful collection processing.



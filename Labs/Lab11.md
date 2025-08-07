
## **Lab11: Lambda Expressions**

### **Instructions:**  
Implement each task concisely using lambda expressions. Demonstrate each with minimal complete code snippets or a main method.

### **Task 1: Runnable with Lambda**

Write a lambda expression implementing `Runnable` that prints the current thread ID and a message. Run it in a new thread.

```java
Runnable task = () -> System.out.println("Running in thread " + Thread.currentThread().getId());
new Thread(task).start();
```

### **Task 2: Comparator with Lambda**

Create a list of `String` and sort it by their length using a lambda `Comparator`.

```java
List words = Arrays.asList("apple", "pear", "banana", "fig");
words.sort((s1, s2) -> Integer.compare(s1.length(), s2.length()));
System.out.println(words);
```

### **Task 3: Consumer with Lambda**

Use a `Consumer` lambda to print each element in a string list prefixed by `"Item: "`.

```java
Consumer printer = s -> System.out.println("Item: " + s);
List list = Arrays.asList("A", "B", "C");
list.forEach(printer);
```

### **Task 4: Function with Lambda**

Write a `Function` lambda that returns the length of a string. Use it to map a list of strings to their lengths.

```java
Function toLength = String::length;
List list = Arrays.asList("hello", "world");
List lengths = list.stream().map(toLength).collect(Collectors.toList());
System.out.println(lengths);
```

### **(Optional) Task 5: Lambda with Multiple Statements**

Write a lambda for `Runnable` with multiple statements: print start, sleep 1 second, then print done.

```java
Runnable r = () -> {
    System.out.println("Start");
    try { Thread.sleep(1000); } catch (InterruptedException e) {}
    System.out.println("Done");
};
new Thread(r).start();
```


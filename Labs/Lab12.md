## **Lab12: Stream Processing**

### **Instructions:**  
Write concise, clean code snippets applying stream operations. Demonstrate outputs using printing.

### **Task 1: Filter Even Numbers**

Given a list of integers, use streams to collect only even numbers into a new list.

```java
List nums = Arrays.asList(1,2,3,4,5,6);
List evens = nums.stream().filter(n -> n % 2 == 0).collect(Collectors.toList());
System.out.println(evens);
```

### **Task 2: Map Strings to Uppercase**

Given a list of strings, transform all strings to uppercase using `map()`.

```java
List words = Arrays.asList("apple", "banana", "cherry");
List upper = words.stream().map(String::toUpperCase).collect(Collectors.toList());
System.out.println(upper);
```

### **Task 3: Sort Custom Objects**

Create a `Person` class with `name` and `age`. Given a list of `Person`, use streams to sort by age ascending.

```java
List people = Arrays.asList(new Person("Alice", 30), new Person("Bob", 25));
List sorted = people.stream()
                            .sorted(Comparator.comparingInt(p -> p.age))
                            .collect(Collectors.toList());
sorted.forEach(p -> System.out.println(p.name + ": " + p.age));
```

### **Task 4: Count Elements Matching a Predicate**

Count how many strings in a list start with the letter `'A'`.

```java
List names = Arrays.asList("Amy", "Bob", "Anna", "Alfred");
long count = names.stream().filter(s -> s.startsWith("A")).count();
System.out.println("Count starting with A: " + count);
```

### **Task 5: Collect Into a Map Grouped by Length**

Given a list of strings, group them by their length into a `Map>`.

```java
List words = Arrays.asList("a", "bb", "ccc", "dd", "eee");
Map> grouped = words.stream()
    .collect(Collectors.groupingBy(String::length));
System.out.println(grouped);
```

### Additional Notes:

- Your implementation should aim to be concise (only relevant imports, minimal variable declarations).
- Use static imports for `Collectors` methods if allowed by your style.
- Provide a small `main()` or test snippet to demonstrate each task’s correctness.
- Ensure you understand method references (`::`) and lambda shorthand.
  

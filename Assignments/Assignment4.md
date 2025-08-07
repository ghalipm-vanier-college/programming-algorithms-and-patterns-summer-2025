## Assignment : Generic Classes & Java Collections Framework (Revised)

**Instructions:** Implement each task with concise, readable code. 
Where necessary, briefly comment on any non-obvious logic. 
Demonstrate usage with a simple `main` method or test snippet for each task.

### **Task 1: Generic Method – Swap Elements in an Array**

**Problem:**  
Write a generic static method:
```java
public static  void swap(T[] array, int i, int j)
```
that swaps the elements at positions `i` and `j` in the given array.  
**Demo:** Swap elements in an array of `String` and in an array of `Integer`, then print the arrays.

### **Task 2: Find the Most Frequent Element in a List**

**Problem:**  
Given a `List`, write a generic static method that returns the element that appears most 
frequently (mode). If there are ties, return any one of them.  
**Demo:** Show usage with `List<String>` and `List<Integer>`. Use Java collections only.

### **Task 3: Remove Duplicates with HashSet**

**Problem:**  
Given a list of integers with possible duplicates, write a method to return a new list with only unique elements, keeping their original input order.  
**Demo:** Input: [2, 5, 4, 7, 2, 3, 4] --> Output: [2, 5, 4, 7, 3].

### **Task 4: Min/Max in a Generic List**

**Problem:**  
Implement a generic static method:
```java
public static <T extends Comparable<T>> T min(List<T> list)
```
that returns the smallest element.  
**Demo:** Find the minimum of a `List<Double>` and a `List<String>`.

### **Task 5: Advanced HashMap Operations**

**Problem:**  
Given a list of strings, write a Java method that returns a Map<String, Integer> 
mapping each string to its frequency (the number of times it appears in the list). 
Then, write a method to print all entries of the map sorted in ascending order by value (frequency); 
if multiple strings have the same frequency, sort those alphabetically.
**Demo:** Input: ["apple", "pear", "apple", "banana", "pear", "pear"] --> 
Output: 
banana: 1
apple: 2
pear: 3


### **Task 6: Sort a List of Custom Objects Using Comparator**

**Problem:**  
Define a simple `Person` class (fields: name `String`, age `int`). Write code to:
- Add several `Person` objects to a `List`
- Sort the list first by age (ascending), then by name (alphabetically if ages are equal), using a custom `Comparator`.
- Print the list before and after sorting.

**Submission Tips**
- Use Java generics and collections for all tasks.
- Keep your solutions concise.
- Each problem should provide a `main` or a demonstration snippet showing the method/class in action.
- Use brief comments where logic is non-trivial.
  

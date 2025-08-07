Certainly! Here is **Assignment #5: Lambda Expressions & Stream Processing** featuring 6 clean, focused tasks that cover similar core concepts as Labs 11 and 12 but with different problems to encourage deeper understanding and variation.

# **Assignment #5: Lambda Expressions & Stream Processing**

**Instructions:**  
Implement each task concisely using Java lambda expressions and Stream API. Provide a short demonstration snippet showing the correctness of your solutions.

### **Task 1: Runnable Lambda with Delay**

Create a `Runnable` lambda that prints `"Task started"`, waits 500 milliseconds (Hint: `Thread.sleep()`), then prints `"Task finished"`. Run this in a new thread and wait for it to complete.

**Deliverables:**

- Lambda implementing `Runnable` with multiple statements.
- Code to start and join the thread.
- Expected Output:
  ```
  Task started
  Task finished
  ```

### **Task 2: Sort Words by Number of Vowels**

Given a list of strings, sort them ascendingly by the count of vowels (`a, e, i, o, u`) in each string using a lambda `Comparator`.

**Example:**

Input: `["apple", "pear", "banana", "fig"]`  
Sorted by vowel count: `["fig", "pear", "apple", "banana"]`

### **Task 3: Consumer to Collect Lengths**

Write a `Consumer` lambda that adds the length of each consumed string to an external `List`. Demonstrate by consuming a list of strings and then printing the collected lengths.

### **Task 4: Stream - Filter and Map Unique Odd Numbers**

Given a list of integers with duplicates, use stream operations to:

- Filter odd numbers,
- Remove duplicates,
- Square each odd number,
- Collect into a list.

**Example:**  
Input: `[2, 3, 4, 2, 6, 4, 7, 3, 5]` --> Output: `[9, 49, 25]`

### **Task 5: Stream Reduce to Concatenate**

Use Stream API and a lambda to concatenate all strings from a list into a single string, 
separated by commas, using the `reduce` method.

**Example:**  
Input: `["Java", "Python", "C++"]`  
Output: `"Java,Python,C++"`

### **Task 6: Grouping Employees by Department and Count**

Define an `Employee` class with `String name` and `String department`. 
Given a list of employees, use Stream API to create a `Map` that maps 
each department to the count of employees in it.

**Example Input:**  
- `{name=Alice, department=HR}`  
- `{name=Bob, department=Finance}`  
- `{name=Charlie, department=HR}`

**Output:**  
`{HR=2, Finance=1}`

## Submission Tips

- Include minimal, functional demo code showing results.
- Keep code concise and clear, focusing on lambda and stream usage.
- Add brief comments if logic isn't straightforward.


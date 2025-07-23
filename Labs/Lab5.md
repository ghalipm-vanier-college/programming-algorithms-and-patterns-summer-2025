
# Big-O Notation Tasks

**Task 1: Identifying Basic Big-O **

* **Description:** For each of the following scenarios, identify the most appropriate Big-O notation that describes its time complexity.
* **Scenarios:**
    1.  Looking up a specific word in a dictionary where you directly jump to the page based on the first letter.
    2.  Printing every single element in a list of `n` items.
    3.  Calculating the result of `2 + 3`.
    4.  Finding a number in a sorted list by repeatedly dividing the search space in half.
* **Expected Answer Format:** Provide the Big-O notation for each scenario (e.g., "1. O(n)").

---

**Task 2: Dominant Term Identification **

* **Description:** Given an algorithm's total operation count expressed as a function of input size `n`, determine its Big-O notation by identifying and simplifying the dominant term.
* **Functions:**
    1.  $5n + 100$
    2.  $n^2 + 3n + 50$
    3.  $10 \log n + 2n$
    4.  $2^n + n^2$
* **Expected Answer Format:** For each function, state its Big-O (e.g., "1. O(n)").

---

**Task 3: Real-World Scenario to Big-O Mapping **

* **Description:** Match each real-world task description with the Big-O notation that best represents its efficiency, considering `n` as the input size. Explain your reasoning briefly.
* **Tasks & Big-O Options:**
    * **Tasks:**
        1.  Calling the first person in a phone book of `n` contacts.
        2.  Searching for a specific book title in an unsorted library of `n` books.
        3.  Finding the shortest route that visits all `n` cities exactly once (Traveling Salesperson Problem, brute-force approach).
        4.  Doubling the storage capacity of an existing dynamic array (like `ArrayList`) when it runs out of space, which requires copying all `n` current elements.
    * **Big-O Options:** O(1), O(n), O(n!), O(n) (worst-case for specific operation)
* **Expected Answer Format:** "Task X: Big-O (Reasoning: ...)"

---

**Task 4: Comparing `ArrayList` vs. `LinkedList` Operations **

* **Description:** Using the provided "Summary: ArrayList vs. LinkedList Performance" table, identify which data structure (or both) is generally more efficient for the following operations in terms of Big-O time complexity.
* **Operations:**
    1.  Accessing an element at a specific index (e.g., `get(5)`).
    2.  Adding an element to the beginning of the list.
    3.  Adding an element to the end of the list.
* **Expected Answer Format:** "1. [Data Structure Name]"

---

**Task 5: Choosing the Right Data Structure **

* **Description:** For each application scenario, recommend whether an `ArrayList` or `LinkedList` would be the more efficient choice. Justify your answer based on their Big-O performance characteristics.
* **Scenarios:**
    1.  **Scenario A:** A music player maintaining a playlist where users frequently jump to a specific song by its number in the list and occasionally add new songs to the end.
    2.  **Scenario B:** An undo/redo functionality in a text editor where operations are constantly added to the end and removed from either the beginning or end of a history stack.
* **Expected Answer Format:**
    * "Scenario A: [Data Structure Name] because [Justification referencing Big-O]."
    * "Scenario B: [Data Structure Name] because [Justification referencing Big-O]."

---

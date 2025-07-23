
## Lab Assignment: Building Custom Data Structures

**Objective:** To gain a fundamental understanding of how dynamic arrays (`ArrayList`) and linked lists (`LinkedList`) are implemented internally, reinforcing concepts of arrays, object references (pointers), and Big-O efficiency.

**Instructions:**
1.  For each task, create a new Java class (e.g., `MyArrayList.java`, `MyLinkedList.java`).
2.  Within each class, implement the specified methods according to the descriptions.
3.  Include a `main` method in a separate test class (e.g., `LabTest.java`) for each task to demonstrate the functionality of your implemented methods. Print outputs to show success.
4.  Pay attention to the Big-O complexity goals mentioned in the provided content.

---

### Task 1: `MyArrayList` - Core Operations (Easy)

**Goal:** Implement the fundamental components of an array-backed list.

1.  **Create a generic class `MyArrayList<T>`:**
    * Declare the essential internal state: `Object[] elements;` and `int size;`.
    * Implement a **constructor** that initializes `elements` with a default capacity (e.g., 10) and `size` to 0.
2.  **Implement `add(T element)`:**
    * This method should add an element to the end of the list.
    * Ensure it handles the **`resize()`** logic: if the internal array is full, create a new array (e.g., double the size), copy existing elements, and update the `elements` reference.
3.  **Implement `int size()`:**
    * Return the current number of elements in the list.
4.  **Demonstrate:** In your `LabTest` class, create a `MyArrayList<String>`. Add at least 15-20 strings (to trigger resize), then print the size and some elements to show they were added.

---

### Task 2: `MyLinkedList` - Head/Tail Operations (Easy)

**Goal:** Understand node creation and pointer manipulation for list ends.

1.  **Create a generic class `MyLinkedList<T>`:**
    * Define the `private static class Node<T>` inner class as provided in the content (with `data`, `next`, `prev`).
    * Declare the essential internal state: `Node<T> head;`, `Node<T> tail;`, and `int size;`.
    * Implement a **constructor** to initialize `head`, `tail` to `null` and `size` to 0.
2.  **Implement `addFirst(T element)`:**
    * Adds an element to the beginning of the list. Handle empty list and non-empty list cases by updating `head` and relevant node pointers.
3.  **Implement `T removeFirst()`:**
    * Removes and returns the element from the beginning of the list. Handle empty list and single-element list cases. Update `head` and relevant node pointers.
4.  **Implement `int size()`:**
    * Return the current number of elements in the list.
5.  **Demonstrate:** In `LabTest`, create a `MyLinkedList<Integer>`. Add a few elements using `addFirst()`, then `removeFirst()` a few times. Print the list's size after each operation.

---

### Task 3: `MyArrayList` - Access & Removal by Index (Medium)

**Goal:** Practice precise element access and array shifting.

1.  **Continue with your `MyArrayList<T>` from Task 1.**
2.  **Implement `T get(int index)`:**
    * Return the element at the specified `index`.
    * Include **bounds checking**: throw an `IndexOutOfBoundsException` if `index` is invalid.
3.  **Implement `T remove(int index)`:**
    * Remove and return the element at the specified `index`.
    * Include **bounds checking**.
    * Perform the necessary **element shifting** to fill the gap created by the removal.
    * Set the last element's reference to `null` after removal (good practice).
4.  **Demonstrate:** In `LabTest`, create a `MyArrayList<String>`. Add at least 5-7 elements. Use `get()` to retrieve elements at various valid indices. Then, `remove()` elements from the middle and beginning, printing the list's state (e.g., by repeatedly calling `get()` and `size()`) after each removal to confirm correctness.

---

### Task 4: `MyLinkedList` - Indexed Access & Insertion (Medium)

**Goal:** Master list traversal and pointer manipulation for middle operations.

1.  **Continue with your `MyLinkedList<T>` from Task 2.**
2.  **Implement `T get(int index)`:**
    * Return the element at the specified `index`.
    * Include **bounds checking**.
    * This requires **traversing** the list from the `head` (or `tail` for efficiency) to reach the desired node.
3.  **Implement `void add(int index, T element)`:**
    * Inserts an `element` at the specified `index`.
    * Include **bounds checking**.
    * Handle edge cases for `index 0` (equivalent to `addFirst`) and `index size` (equivalent to `addLast`).
    * For other indices, **traverse** to the correct position, then update the `next` and `prev` pointers of the new node and its neighbors.
4.  **Demonstrate:** In `LabTest`, create a `MyLinkedList<Character>`.
    * Add some characters using `addFirst()` and `addLast()`.
    * Use `get()` to access elements at different indices, printing them.
    * Use `add(index, element)` to insert elements in the middle of the list.
    * After each insertion, verify the list's contents by repeatedly calling `get()` or by printing elements (you might need a simple `toString()` for debugging if you wish).

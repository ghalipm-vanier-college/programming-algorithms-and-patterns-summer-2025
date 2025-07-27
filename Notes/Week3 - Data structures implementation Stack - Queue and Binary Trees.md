
#  Stacks, Queues, Binary Trees & Recursion

## I. Basic Data Structures: `Stack` and `Queue`

We've covered `Arrays`, `ArrayList`, and `LinkedList`. Now, let's explore two more fundamental linear data structures: Stacks and Queues. They are conceptual tools that define specific access patterns.

### A. Stack

  * **Definition:** A linear data structure that follows the **LIFO (Last-In, First-Out)** principle.
      * Think of a stack of plates: You add new plates to the top, and you remove plates from the top. The last plate added is the first one removed.
  * **Core Operations:**
      * `push(element)`: Adds an element to the top of the stack.
      * `pop()`: Removes and returns the top element from the stack.
      * `peek()`: Returns the top element without removing it.
      * `isEmpty()`: Checks if the stack is empty.
      * `size()`: Returns the number of elements in the stack.
  * **Big-O Performance (for typical implementations):**
      * `push`, `pop`, `peek`, `isEmpty`, `size`: **O(1)**
  * **Common Use Cases:**
      * Function call stack (managing method calls).
      * Undo/Redo functionality in applications.
      * Browser history (back button).
      * Expression evaluation (e.g., postfix notation).

### B. Queue

  * **Definition:** A linear data structure that follows the **FIFO (First-In, First-Out)** principle.
      * Think of a line at a grocery store: The first person in line is the first person to be served.
  * **Core Operations:**
      * `enqueue(element)`: Adds an element to the rear (or tail) of the queue.
      * `dequeue()`: Removes and returns the front (or head) element from the queue.
      * `peek()`: Returns the front element without removing it.
      * `isEmpty()`: Checks if the queue is empty.
      * `size()`: Returns the number of elements in the queue.
  * **Big-O Performance (for typical implementations):**
      * `enqueue`, `dequeue`, `peek`, `isEmpty`, `size`: **O(1)**
  * **Common Use Cases:**
      * Printer job scheduling.
      * CPU task scheduling.
      * Handling requests in web servers.
      * Breadth-First Search (BFS) algorithm.

### C. Stack vs. Queue Summary

| Feature        | Stack                  | Queue                 |
| :------------- | :--------------------- | :-------------------- |
| Principle      | LIFO (Last-In, First-Out) | FIFO (First-In, First-Out) |
| Add Operation  | `push` (to top)        | `enqueue` (to rear)   |
| Remove Operation | `pop` (from top)       | `dequeue` (from front) |
| Access         | Only top element        | Only front element    |
| Typical Speed  | O(1) for all main ops  | O(1) for all main ops |

-----

## II. Data Structures Implementation: Stack, Queue, and Binary Trees

Just like we discussed implementing `MyArrayList` and `MyLinkedList`, we can build our own versions of Stacks, Queues, and even more complex structures like Binary Trees. This reveals their internal working mechanisms.

### A. Implementing `MyStack<T>`

  * **Core Idea:** A stack can be implemented using either an array or a linked list.

      * **Array-backed Stack:** Uses a dynamic array (like `MyArrayList`) where `push` adds to the end, and `pop`/`peek` operate on the last element. A `top` index or `size` variable tracks the top. Resizing is needed.
      * **Linked List-backed Stack:** Uses a singly linked list. `push` adds to the head, and `pop`/`peek` remove/read from the head. No resizing, just pointer updates.

  * **Internal State (Example: Array-backed):**

      * `Object[] elements;`
      * `int top;` (index of the top element, or `size`)

  * **Key Methods & Big-O Goals:**

      * `MyStack()`: Constructor.
      * `push(T element)`: Add to array/linked list end/head. **O(1)** (amortized for array).
      * `pop()`: Remove from array/linked list end/head. **O(1)**.
      * `peek()`: Read from array/linked list end/head. **O(1)**.
      * `isEmpty()`: Check `top` or `head`. **O(1)**.

### B. Implementing `MyQueue<T>`

  * **Core Idea:** A queue can also be implemented using an array (often circular to optimize space) or a linked list.

      * **Array-backed Queue:** More complex to implement efficiently (requires managing `front` and `rear` pointers, and often circular array logic to avoid constant shifting).
      * **Linked List-backed Queue:** Generally simpler to achieve O(1) for both `enqueue` and `dequeue`. `enqueue` adds to the `tail`, `dequeue` removes from the `head`.

  * **Internal State (Example: Linked List-backed):**

      * `Node<T> head;`
      * `Node<T> tail;`

  * **Key Methods & Big-O Goals:**

      * `MyQueue()`: Constructor.
      * `enqueue(T element)`: Add to tail. **O(1)**.
      * `dequeue()`: Remove from head. **O(1)**.
      * `peek()`: Read from head. **O(1)**.
      * `isEmpty()`: Check `head`. **O(1)**.

### C. Introduction to Binary Trees

  * **Definition:** A **non-linear**, hierarchical data structure where each node has at most two children, referred to as the "left child" and the "right child."
  * **Key Terminology:**
      * **Root:** The topmost node of the tree.
      * **Node:** Each element in the tree.
      * **Child:** A node directly below another node.
      * **Parent:** A node directly above another node.
      * **Leaf Node:** A node with no children.
      * **Edge:** The link between a parent and child node.
  * **Core Concept (Implementation):** Trees are built from linked `Node` objects, similar to `LinkedList`, but with two child references instead of `next`/`prev`.
  * **Inner `Node` Class Example:**
    ```java
    private static class Node<T> {
        T data;
        Node<T> left;  // Reference to left child
        Node<T> right; // Reference to right child

        Node(T data) {
            this.data = data;
            this.left = null;
            this.right = null;
        }
    }
    ```
  * **Basic Operations (Conceptual):**
      * **Insertion:** Adding new nodes while maintaining tree properties (e.g., for a Binary Search Tree, smaller values go left, larger go right).
      * **Traversal:** Visiting each node in a specific order. Common types:
          * **In-order:** Left -\> Root -\> Right (Often results in sorted output for BSTs).
          * **Pre-order:** Root -\> Left -\> Right (Useful for copying trees).
          * **Post-order:** Left -\> Right -\> Root (Useful for deleting trees).
  * **Big-O Performance (for typical operations like search, insertion, deletion):**
      * **Balanced Tree:** **O(log N)** (e.g., in a perfectly balanced tree, you halve the search space at each level).
      * **Skewed Tree (Worst Case):** **O(N)** (behaves like a linked list if all nodes are on one side).
  * **Why Trees Matter:** Efficient searching, sorting, and storing hierarchical data. Foundation for more advanced data structures (e.g., Heaps, B-Trees).

-----

## III. Review of Recursion

Recursion is a powerful programming technique often used with hierarchical data structures like trees.

### A. Definition

  * A function (or method) is **recursive** if it calls itself directly or indirectly to solve a problem.

### B. Essential Components of a Recursive Function

Every well-formed recursive function must have:

1.  **Base Case:** A condition that stops the recursion. Without it, the function would call itself infinitely, leading to a "Stack Overflow Error." This is the simplest instance of the problem that can be solved directly.
2.  **Recursive Step:** The part where the function calls itself with a *modified input*, moving towards the base case. The problem is broken down into smaller, similar subproblems.

### C. How Recursion Works (The Call Stack)

  * Each time a recursive function calls itself, a new *stack frame* is pushed onto the **call stack**.
  * This stack frame stores the local variables and the return address for that specific function call.
  * When a base case is reached, the function starts returning, and stack frames are popped off the call stack in LIFO order.

### D. When to Use Recursion

  * When a problem naturally breaks down into smaller, identical subproblems.
  * Processing hierarchical data (trees, graphs).
  * Certain mathematical definitions (e.g., factorial, Fibonacci).
  * When the recursive solution is simpler and more readable than an iterative one (though iterative is often more performant due to less overhead).

### E. Examples

1.  **Factorial Calculation:**

      * `factorial(n) = n * factorial(n-1)` for `n > 1`
      * `factorial(1) = 1` (Base Case)

    <!-- end list -->

    ```java
    public static int factorial(int n) {
        if (n == 1) { // Base Case
            return 1;
        }
        return n * factorial(n - 1); // Recursive Step
    }
    ```

2.  **Tree Traversal (In-order):**

      * Visiting nodes of a Binary Tree in sorted order (for a Binary Search Tree).

    <!-- end list -->

    ```java
    public void inOrderTraversal(Node node) {
        if (node == null) { // Base Case
            return;
        }
        inOrderTraversal(node.left);  // Recursive call for left subtree
        System.out.print(node.data + " "); // Process current node
        inOrderTraversal(node.right); // Recursive call for right subtree
    }
    ```

    (Note: This requires a `Node` class as described in the Binary Trees section.)

-----

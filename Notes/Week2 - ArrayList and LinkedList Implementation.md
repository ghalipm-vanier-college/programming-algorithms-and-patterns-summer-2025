Now, we are not just using pre-made tools; we are building them from the ground up. 
This will solidify our understanding of how `ArrayList` and `LinkedList` actually work internally and 
why they have their specific Big-O characteristics.

-----

# Data Structures Implementation: Building Custom `MyArrayList` & `MyLinkedList`

The core idea here is to recreate the fundamental behavior of Java's standard library `ArrayList` and `LinkedList` 
using only basic building blocks (arrays, objects, and references).

-----

### 1\. Implementing `MyArrayList<T>` (The Dynamic Array)

Your `MyArrayList` will mimic the behavior of `java.util.ArrayList`, which is backed by a resizeable array.

  * **Core Idea:** Store elements in a basic Java array. When this array gets full, create a new, larger array and copy all elements over.

  * **Essential Internal State:**

      * `Object[] elements;` (or `T[] elements;` with careful casting due to Java's generics and arrays). This is your underlying storage.
      * `int size;` This keeps track of how many elements are currently in your list (not the capacity of the array).

  * **Key Methods to Implement & Their Big-O Goals:**

    1.  **Constructor(s):**

          * Initialize `elements` with a default starting capacity (e.g., 10).
          * Set `size` to 0.

    2.  **`add(T element)` (Add to end):**

          * **Check Capacity:** If `size == elements.length`, you need to resize.
          * **Resize (Helper Method):** Create a *new* array, typically 1.5x or 2x the current capacity. Copy all existing `elements` to this new array. Assign the new array to `this.elements`. (This step is O(N)).
          * **Add Element:** Place the `element` at `elements[size]`.
          * **Increment Size:** `size++`.
          * **Big-O Goal:** Amortized **O(1)** (due to occasional O(N) resizing being spread out), Worst-case **O(N)** (when resizing occurs).

    3.  **`get(int index)`:**

          * **Bounds Check:** Ensure `index` is within `0` and `size - 1`. If not, throw `IndexOutOfBoundsException`.
          * **Return Element:** Return `(T) elements[index]`.
          * **Big-O Goal:** **O(1)**

    4.  **`remove(int index)`:**

          * **Bounds Check:** Ensure `index` is valid.
          * **Shift Elements:** Move all elements *after* `index` one position to the left to fill the gap.
              * Example: `System.arraycopy(elements, index + 1, elements, index, size - index - 1);`
          * **Decrement Size:** `size--`.
          * **Clear Last Element (Optional but Good Practice):** Set `elements[size]` to `null` to allow garbage collection.
          * **Big-O Goal:** **O(N)** (due to shifting).

    5.  **`size()`:**

          * Return the current value of `size`.
          * **Big-O Goal:** **O(1)**

  * **Key Challenge:** Managing the underlying array's size and copying elements efficiently.

-----

### 2\. Implementing `MyLinkedList<T>` (The Node-Based List)

Your `MyLinkedList` will mimic the behavior of `java.util.LinkedList`, which uses nodes linked together by references. You'll typically implement a **doubly linked list** for efficient adds/removes at both ends.

  * **Core Idea:** Elements are stored in individual "nodes," where each node contains the data and references (pointers) to the next and (for doubly linked) the previous node.

  * **Essential Internal State:**

      * **Inner `Node` Class:** You'll define a private static inner class like:
        ```java
        private static class Node<T> {
            T data;
            Node<T> next;
            Node<T> prev; // For doubly linked list

            Node(T data) {
                this.data = data;
                this.next = null;
                this.prev = null;
            }
        }
        ```
      * `Node<T> head;` (reference to the first node)
      * `Node<T> tail;` (reference to the last node)
      * `int size;` (keeps track of the number of elements)

  * **Key Methods to Implement & Their Big-O Goals:**

    1.  **Constructor(s):**

          * Initialize `head`, `tail` to `null`.
          * Set `size` to 0.

    2.  **`addFirst(T element)`:**

          * Create a new `Node` for the `element`.
          * Handle the case where the list is empty (new node becomes both `head` and `tail`).
          * Otherwise, update the new node's `next` to point to the current `head`, and the current `head`'s `prev` to point to the new node.
          * Update `head` to be the new node.
          * Increment `size`.
          * **Big-O Goal:** **O(1)**

    3.  **`addLast(T element)`:**

          * Similar logic to `addFirst`, but update `tail` and its pointers.
          * **Big-O Goal:** **O(1)**

    4.  **`get(int index)`:**

          * **Bounds Check:** Ensure `index` is valid.
          * **Traverse:** Start from `head` (or `tail` if `index` is closer to the end for efficiency) and iterate `next` (or `prev`) until you reach the `index`.
          * Return the `data` from the found node.
          * **Big-O Goal:** **O(N)** (due to traversal).

    5.  **`removeFirst()`:**

          * **Handle Empty/Single Element:** Check if `head` is null or if `size` is 1.
          * Update `head` to `head.next`.
          * If the new `head` is not null, set its `prev` to `null`.
          * Decrement `size`.
          * **Big-O Goal:** **O(1)**

    6.  **`removeLast()`:**

          * Similar logic to `removeFirst`, but update `tail`.
          * For doubly linked lists, `tail.prev` makes this O(1).
          * **Big-O Goal:** **O(1)**

    7.  **`add(int index, T element)` / `remove(int index)` (in middle):**

          * These operations involve two steps:
              * **Find Node:** Use a traversal similar to `get(index)` to find the node *before* the insertion/removal point. This is O(N).
              * **Update Pointers:** Once found, manipulate the `next` and `prev` pointers of the surrounding nodes to insert or bypass the node. This part is O(1).
          * **Big-O Goal:** **O(N)** (dominated by the traversal).

    8.  **`size()`:**

          * Return the current value of `size`.
          * **Big-O Goal:** **O(1)**

  * **Key Challenge:** Meticulously updating all relevant `next` and `prev` references to maintain the integrity of the list, especially for edge cases (empty list, adding to/removing from a list with one element). Drawing diagrams helps immensely\!

-----

**General Tips for Implementation:**

  * **Start Simple:** Begin by implementing just the constructor and `add(T element)` (to the end) and `size()`. Get those working and tested.
  * **Test Thoroughly:** Write JUnit or TestNG tests for every method you implement. Cover normal cases, empty list cases, single-element lists, and boundary conditions (e.g., adding/removing at `index 0`, `index size-1`).
  * **Draw Diagrams:** Especially for `MyLinkedList`, sketch out the nodes and pointer changes before you write code. It prevents many headaches.
  * **Generics & Arrays:** Remember that you can't create a `new T[capacity]` directly in Java. You'll typically create `new Object[capacity]` and then cast elements when you `get()` them (`(T) elements[index]`). Suppress warnings thoughtfully.
  * **Think Big-O:** As you implement each method, constantly ask yourself: "How many operations does this take relative to `n` (the number of elements)?" This guides your implementation towards the correct efficiency.

This implementation task is a fantastic way to truly grasp the efficiency differences between array-backed and node-based list structures. Good luck\!

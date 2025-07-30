Designed for use with the custom `MyQueue` class, or any basic queue implementation 
using standard `enqueue`, `dequeue`, `peek`, `isEmpty`, and `size` methods. 

## Lab: Problem Solving with MyQueue

### 1. Enqueue & Dequeue Demo
- Create a `MyQueue`.
- Enqueue the numbers 7, 14, and 21 (in that order).
- Dequeue and print all values from the queue until it is empty.
- What is the printed output?
- Briefly explain your result in terms of the queue’s FIFO (First-In-First-Out) principle.

### 2.  Process People in a Line
- Suppose five people arrive one after another (Alice, Bob, Carol, Dave, Eve).
- Enqueue their names as strings.
- Serve them using `dequeue` and print each name as they are served.
- What is the order in which they are served?

### 3.  Check the Next in Line
- After enqueuing several items (for example: 1, 2, 3), use the `peek()` method to print the item at the front of the queue **without removing it**.
- Confirm that after `peek()`, the value is still in the queue (try dequeueing afterwards to verify).

### 4.  Simulate Print Queue Processing
- Write a method to simulate a printer queue:
    - Enqueue a series of print jobs (strings like "Doc1", "Doc2", ...).
    - Process jobs by dequeueing and printing the job name until the queue is empty.
- Print both the order jobs enter and the order they’re processed.
- Discuss how queues naturally model fair “first-come, first-served” systems.

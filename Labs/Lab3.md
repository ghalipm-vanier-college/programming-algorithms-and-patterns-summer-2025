# Lab 3: Diving into LinkedList 
________________________________________
## Objective: 
To grasp the concept of linked structures, their efficiency in insertions/deletions at ends, 
differences from ArrayList, and their use as a Queue(FIFO)/Deque(LIFO).
## Instructions:
### 1.	LinkedList Creation and Population:
o	Create a LinkedList of String objects named shoppingList.
o	Add at least five different items to the shoppingList (e.g., "Eggs", "Milk", "Bread", "Cheese", "Apples").
o	Create a LinkedList of Double objects named temperatures.
o	Add at least five different temperature readings (e.g., 25.5, 30.1, 18.0, 27.3, 32.5) to the temperatures LinkedList.
2.	Adding and Removing at Ends (Efficient Operations):
o	Add "Yogurt" to the beginning of the shoppingList using addFirst().
o	Add "Orange Juice" to the end of the shoppingList using addLast().
o	Remove the first item from the shoppingList using removeFirst().
o	Remove the last item from the shoppingList using removeLast().
o	Add 22.0 to the beginning of temperatures.
o	Remove the last temperature from temperatures.
o	New Task: Add 100,000 random Double values (between 0.0 and 100.0) to a new LinkedList<Double> named largeLinkedList. Measure and print the time it takes for this operation. (Hint: Use System.nanoTime() and addLast()).
3.	Accessing Elements (Less Efficient Operations):
o	Print the item at index 2 in the shoppingList using get(index). (Observe that this is still possible, but conceptually less efficient than in an ArrayList for large lists).
o	Print the first and last elements of the temperatures LinkedList using getFirst() and getLast().
o	New Task: Try to retrieve the element at index 50,000 from largeLinkedList using get(50000). Measure and print the time it takes. Compare this time to the time it took to add elements or to ArrayList's get() operation.
4.	Checking Size and Iterating:
o	Print the current size of both shoppingList and temperatures.
o	Use an enhanced for loop to print all elements of the shoppingList.
o	Use a standard for loop to print all elements of the temperatures LinkedList.
5.	LinkedList as a Queue/Deque:
o	New Task: Demonstrate LinkedList as a Queue (First-In, First-Out).
	Create a LinkedList<String> called taskQueue.
	Add "Task A", "Task B", "Task C" using offer().
	Simulate processing tasks by repeatedly using poll() and printing the removed task until the queue is empty.
o	New Task: Demonstrate LinkedList as a Stack (Last-In, First-Out).
	Create a LinkedList<Integer> called numberStack.
	Add 10, 20, 30 using push().
	Simulate popping elements by repeatedly using pop() and printing the removed number until the stack is empty.
6.	Conceptual Questions on LinkedList Performance:
o	Question 1: Explain why removing an element from the middle of a LinkedList can be more efficient than removing an element from the middle of an ArrayList, assuming you already have a reference to the node to be removed. (If you don't have a direct reference, discuss the implications).
o	Question 2: When would you absolutely prefer using a LinkedList over an ArrayList? Provide at least two distinct scenarios where LinkedList shines.
o	Question 3: Describe the internal structure of a LinkedList and how it differs from the internal structure of an ArrayList. Use an analogy if it helps your explanation.


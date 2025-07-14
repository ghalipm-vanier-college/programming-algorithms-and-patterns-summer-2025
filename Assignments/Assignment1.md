# Assignment: Data Structures Review
________________________________________
## Total Marks: 100
## Instructions: 
* Answer all questions thoroughly. Provide code snippets for all programming tasks and clear, concise explanations for all conceptual questions.

#### Question 1: Array Fundamentals (10 Marks)
* Given the integer array: int[] data = {15, 22, 10, 30, 5, 28};
* a. (3 Marks) Write Java code to find and print the minimum value in the data array.
* b. (4 Marks) Create a new array called filteredData and populate it with all numbers from the data array that are greater than 20. Print the filteredData array.
* c. (3 Marks) Explain in your own words: What does it mean for an array to be a fixed-size data structure?
________________________________________
#### Question 2: Array Homogeneity & Flexibility (10 Marks)
* a. (5 Marks) Can a Java array store both String and Integer objects in the same array (e.g., ["Hello", 123])? Explain your answer with respect to Java's type system for arrays.
* b. (5 Marks) If you need to store a collection of elements where the size frequently changes (e.g., adding or removing elements often), would a traditional Java array be the most suitable choice? Why or why not?
________________________________________
#### Question 3: ArrayList Basics & Operations (10 Marks)
* Consider an ArrayList<String> named cities.
* a. (3 Marks) Write Java code to create this ArrayList and add "London", "Paris", "Tokyo", "New York" to it.
* b. (4 Marks) Add "Rome" at the beginning of the cities list and "Berlin" at index 3. Then remove "Tokyo" from the list. Print the cities list after these operations.
* c. (3 Marks) What is the primary advantage of using ArrayList over a primitive array when you don't know the exact number of elements beforehand?
________________________________________
#### Question 4: ArrayList Performance (10 Marks)
* Imagine you have an ArrayList<Integer> containing 1 million elements.
* a. (5 Marks) If you need to access an element at a specific index (e.g., get(500000)), would this operation be fast or slow? Explain why, referring to the internal structure of ArrayList.
* b. (5 Marks) If you frequently need to insert elements at the very beginning of this 1 million-element ArrayList, would this be an efficient operation? Explain the underlying process that makes it efficient or inefficient.
________________________________________
#### Question 5: LinkedList Fundamentals (10 Marks)
* a. (4 Marks) Create a LinkedList of Double objects named prices. Add the values 9.99, 12.50, 5.00, and 20.75 to it. Then, add 7.25 to the front and remove the last element. Print the prices list.
* b. (3 Marks) Describe a scenario where LinkedList would be a more suitable choice than ArrayList for adding/removing elements.
* c. (3 Marks) What is the main difference in how LinkedList stores its elements compared to ArrayList?
________________________________________
#### Question 6: LinkedList Efficiency (10 Marks)
* Consider a LinkedList<String> containing 1 million elements.
* a. (5 Marks) If you need to add a new element to the very end of this LinkedList, would this operation be fast or slow? Explain why, referencing LinkedList's internal structure.
* b. (5 Marks) If you need to retrieve an element at a specific index (e.g., get(750000)), would this operation be fast or slow? Explain the process LinkedList must undertake to perform this operation.
________________________________________
#### Question 7: Using LinkedList as a Queue (10 Marks)
* a. (5 Marks) Create a LinkedList<String> to simulate a queue of print jobs. Add "Document A", "Document B", and "Document C" to the queue using appropriate Queue methods.
* b. (5 Marks) Write code to process (remove) and print each print job from the queue until it is empty. Show the state of the queue (or elements printed) after each processing step.
________________________________________
#### Question 8: Choosing the Right Data Structure (10 Marks)
* For each of the following scenarios, recommend whether an Array, ArrayList, or LinkedList would be the most appropriate data structure in Java and explain why your choice is optimal.
* a. (3 Marks) Storing a fixed number of sensor readings (e.g., 100 readings) where you frequently need to access data by its index.
* b. (3 Marks) Managing a playlist of songs where songs are frequently added to the beginning or end, and you rarely jump to a specific song by its number.
* c. (4 Marks) Maintaining a list of registered users for a website, where new users are added constantly, and existing users might be removed, but you also need to occasionally search for a user by their username (not by index).
________________________________________
#### Question 9: Comparing Internal Mechanisms (10 Marks)
* a. (5 Marks) Explain the concept of "resizing" in an ArrayList. When does it happen, and what is the performance implication of this process?
* b. (5 Marks) How does a LinkedList avoid the need for resizing like an ArrayList? Describe how elements are "linked" together.
________________________________________
#### Question 10: Practical Application & Time Measurement (10 Marks)
* a. (5 Marks) Write Java code that demonstrates the time difference for adding 50,000 elements to the beginning of both an ArrayList<Integer> and a LinkedList<Integer>.
  Print the time taken for each operation in milliseconds.
* Initialize both collections.
* Use System.nanoTime() to measure the start and end times for each addition loop.
* Convert the time difference to milliseconds for printing.
* b. (5 Marks) Based on your results from part (a), explain why LinkedList is significantly faster for this specific operation compared to ArrayList.
________________________________________
#### Marking Criteria
*  Correctness (60%):
*  Code compiles and runs without errors.
*  Output matches expected results.
*  Algorithms/logic are sound and address the problem correctly.
•	Completeness (20%):
* 	All parts of each question are attempted and addressed.
* 	Explanations are provided where required.
•	Clarity & Understanding (20%):
* 	Code is well-formatted and easy to read.
* 	Explanations are clear, concise, and demonstrate a strong understanding of the concepts.
*  Proper use of terminology.




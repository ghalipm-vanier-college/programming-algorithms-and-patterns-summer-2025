________________________________________
# Lab 2: Exploring ArrayList
________________________________________
## Objective: To deepen understanding of dynamic arrays, their common operations, the use of generics, and their performance characteristics.
### Instructions:
#### 1.	ArrayList Creation and Population:
*	Create an ArrayList of String objects named fruits.
*	Add at least five different fruit names to the fruits ArrayList (e.g., "Apple", "Banana", "Cherry", "Date", "Elderberry").
*	Create an ArrayList of Integer objects named studentAges.
*	Add at least five different ages to the studentAges ArrayList (e.g., 18, 19, 20, 21, 22).

#### 2.	Accessing and Modifying Elements:
*	Print the element at index 2 in the fruits ArrayList.
*	Change the fruit at index 0 to "Mango" and print the updated fruits ArrayList.
*	Retrieve and print the age of the student at index 3 from studentAges.

#### 3.	Adding and Removing Elements Dynamically:
*	Add "Grape" to the end of the fruits ArrayList.
*	Add "Banana" at index 1 in the fruits ArrayList. (Notice how this shifts subsequent elements).
*	Remove the fruit at index 3 from the fruits ArrayList. (Notice the shifting again).
*	Remove the first occurrence of the Integer value 20 (if it exists) from studentAges.
*	Add 100,000 random integers (between 0 and 1000) to a new ArrayList<Integer> named largeList. Measure and print the time it takes for this operation. (Hint: Use System.nanoTime() before and after the loop).


#### 4.	Checking Size and Emptiness:
*	Print the current size of both fruits and studentAges.
*	Check if the fruits ArrayList is empty and print the result.

#### 5.	Iterating Through ArrayLists:
*	Use a standard for loop to print all elements of the fruits ArrayList.
*	Use an enhanced for loop to print all elements of the studentAges ArrayList.
*	Iterate through largeList and find the sum of all elements. Measure and print the time it takes for this operation.

#### 6.	Advanced ArrayList Operations:
*	Create another ArrayList<String> called tropicalFruits and add "Pineapple", "Papaya", "Coconut". Use addAll() to add all elements from tropicalFruits to the fruits ArrayList. Print fruits.
*	Use the indexOf() method to find the index of "Banana" in the fruits ArrayList. Print the index.
*	Use the clear() method to remove all elements from studentAges. Print studentAges and its size to confirm it's empty.

#### 7.	Conceptual Questions on ArrayList Performance:
*	Question 1: Explain in your own words why adding an element to the middle of an ArrayList can be less efficient than adding an element to the end of an ArrayList.
*	Question 2: When would you prefer using an ArrayList over a traditional Java array? Provide at least two scenarios.

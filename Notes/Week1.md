
## Basic Data Structures: `Arrays and  Array List` 

## Arrays 
Arrays in Java can store elements of any type: 
`primitive types` and `objects`. 
Static size once created. Efficient for static data.

* In Java, arrays themselves are `objects`, even when they hold primitive data types
* While arrays can hold various types, a single array instance can only hold homogenous elements
* Arrays vs. Collections: While `arrays` can hold `primitive types and objects`, 
Java `Collections (like ArrayList, LinkedList, etc.)` 
are designed to work with `objects` only and cannot 
directly store primitive types.

### Primitive Data Types:
* boolean
* byte
* short
* int
* long
* float
* double
* char

### Reference Data Types:
* Any class or interface type (e.g., String, Integer, custom classes like MyClass).
* Arrays of objects (e.g., String[ ], Object[ ]).
* Multidimensional arrays (e.g., int[ ][ ]).

### Examples
* Primitive array: int[ ] numbers = new int[7];
* Reference array: String[ ] weekDays = new String[ ]{"Mon", "Tues", "Wed", "Thurs", "Fri", "Sat", "Sun"};
* Multidimensional array: int[ ][ ] matrix = new int[2][2];

## ArrayList (in Java)
* dynamic-size, can store objects only, not primitives directly, unless wrapped;  
* supports methods like add(), remove(), and get(); 
part of java.util. 
* ideal for dynamic data but slightly slower than Array.
* is an object that implements the List,
  internally backed by Array.
* can only hold homogenous elements.

## Object Data Types:
* Any class or interface

## Examples
### Object ArrayList ( Pre-Generics or Raw Type ): 
* An Object ArrayList refers to an ArrayList declared without a specific type parameter, like 
 `ArrayList fruits = new ArrayList<>(Arrays.asList("Apple", 12));` no type parameter.
### Generic ArrayList ( an ArrayList declared with a type parameter ):
* `ArrayList<Integer> numbers = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5));`
### Dynamic addition: 
fruits.add("Mango"); // Resizes automatically.
### In Summary
* Size of ArrayList can be changed dynamically using methods like add(), remove(), and clear().
* ArrayList is efficient for scenarios requiring frequent modifications but slightly slower than arrays due to overhead.

## LinkedList (in Java)
* Dynamic-size, can store objects only, not primitives directly, unless wrapped.

* Supports methods like addFirst(), addLast(), removeFirst(), removeLast(), get(), etc.

* Part of java.util.

* Ideal for frequent insertions and deletions at the beginning or end, but slower for random access (getting elements by index).

* Is an object that implements the List and Deque interfaces, internally backed by a doubly linked list structure.

* Can only hold homogenous elements.

### In summary:

* LinkedList: Great for operations where you're always dealing with the first or last element because it's just a quick pointer change. Think of adding/removing items from the top/bottom of a stack or queue.

* ArrayList: Great when you frequently need to access/read elements by their position (index) because it provides direct access.

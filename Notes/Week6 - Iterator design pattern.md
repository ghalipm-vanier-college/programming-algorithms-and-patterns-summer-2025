# Iterator Design Pattern

  The `Iterator design pattern` is a behavioral design pattern in Java that provides a way 
  to access the elements of a collection object sequentially without exposing its underlying 
  representation. It `decouples the traversal logic from the collection itself`, promoting flexibility 
  and maintainability. 

## Iterator Interface:
Defines the methods for traversing the collection. In Java, this is typically the 
java.util.Iterator interface, which includes:
* hasNext(): Returns true if there are more elements to iterate over, false otherwise.
* next(): Returns the next element in the sequence.
* remove(): (Optional) Removes the last element returned by next() from the underlying collection.

## Benefits:
* Decoupling:
  Separates the traversal logic from the collection, allowing them to evolve independently.
* Encapsulation:
  Hides the internal representation of the collection from the client.

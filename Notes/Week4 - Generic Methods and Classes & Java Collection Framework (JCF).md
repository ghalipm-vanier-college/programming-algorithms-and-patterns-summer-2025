# Generic Methods and Classes & Java Collection Framework (JCF)
  ## 1. Generic Methods and Classes in Java
        * Generics enable you to write classes and methods that work with any data type, 
          making the code more reusable and type-safe.
        
        * Why use Generics?
        * Code Reusability: One class/method works with multiple data types.
        
        * Type Safety: Errors caught at compile time.
        
        * No Casting: Easier and safer code without explicit casts.

 ### Generic Class Example
 * **Generic class with type parameter T**
```java
class Box<T> {
    private T value;

    public void set(T value) { this.value = value; }
    public T get() { return value; }
}

public class Main {
    public static void main(String[] args) {

        Box<String> stringBox = new Box<>();
        stringBox.set("Hello");
        System.out.println(stringBox.get());  // Output: Hello

        Box<Integer> intBox = new Box<>();
        intBox.set(10);
        System.out.println(intBox.get());     // Output: 10
    }
}
```
### Generic Method Example
```java
public class Utils {
    // Generic method to print elements of any type
    public static <T> void printArray(T[] array) {
        System.out.println(Arrays.toString(array));
    }    

    // Generic method to find max of an array
    public static <T extends Comparable<T>> T  findMax(T[] array) {
        T max=(array.length==0)?null:array[0];
        for (T num: array){
            max=(max.compareTo(num)<0)?num:max;
        }
        return max;
    }

    //Generic addition of two elements with proper operators: 
    public static <T> T add(T elem1, T elem2, BinaryOperator<T> adder) {
        return adder.apply(elem1, elem2);
    }

}

```
## 2. Introduction to Java Collection Framework (JCF)
      * Java Collections provide data structures to store and manipulate groups of objects.
      
      * **Key Interfaces**:
      * Collection: The root interface for collections (List, Set, Queue)
      
      * List: Ordered, allows duplicates (e.g., ArrayList, LinkedList)
      
      * Set: No duplicates, unordered or sorted (e.g., HashSet, TreeSet)
      
      * Map: Key-value pairs (not a Collection)
      
      * Common Concrete Classes:

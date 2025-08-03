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
}

```
## 2. Introduction to Java Collection Framework (JCF)
      * Java Collections provide data structures to store and manipulate groups of objects.
      
      * **Key Interfaces**:
      * Collection: The root interface for collections (List, Set, Queue)
      
      * List: Ordered, allows duplicates (e.g., ArrayList, LinkedList)
      
      * Set: No duplicates, unordered or sorted (e.g., HashSet, TreeSet)
      
      * Map: Key-value pairs (not a Collection)

  <img width="852" height="612" alt="image" src="https://github.com/user-attachments/assets/f32c8864-c4a2-4905-8eea-d81d28eb7b49" />
      
  ### Common Concrete Classes:
  <img width="954" height="429" alt="image" src="https://github.com/user-attachments/assets/5c27b78d-bc22-4cae-a5be-de3359296a46" />

## 3. Sets in Java: HashSet vs TreeSet

<img width="1132" height="458" alt="image" src="https://github.com/user-attachments/assets/ddc89384-9ec1-4a90-8fc1-4a98db39be8d" />

## Summary

<img width="988" height="267" alt="image" src="https://github.com/user-attachments/assets/d93979a8-a2f1-45fa-bddd-63b8d6c33ad6" />




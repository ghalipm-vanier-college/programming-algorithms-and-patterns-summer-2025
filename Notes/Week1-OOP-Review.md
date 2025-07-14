# OOP Review
## 1. Encapsulation:
   * Definition: `Bundling data` (fields) and methods that operate on the data `into a single unit` (class), restricting direct access to some components.
   * Key Feature: Uses access modifiers (e.g., `private, public`) to hide internal details and expose only necessary interfaces.
   * By making fields private, we prevent external code from directly modifying them, forcing interaction through public methods (getters and setters). This concept is often referred to as data hiding.

### Why it Matters:

#### Data Integrity:
 * Prevents unauthorized or incorrect modification of an object's internal state.

 #### Maintainability: 
 * Changes to internal implementation don't affect external code, as long as the public interface remains consistent.

#### Reduced Complexity: 
* Simplifies the usage of an object by exposing only what's necessary.

#### Example: 
* A SalesPerson class with private salary, can be accessed via public getSalary() method. Here the details such as
  baseSalary, salesGeneratedBonus/commissionRate are hided in the SalesPerson class,
  only salary can be viewed by public getSalary() method. 
     
## 2. Inheritance:
   * Definition: Allows a class (subclass/child) to inherit properties and methods from another class (superclass/parent).
   * Key Feature: Supports code reuse and establishes an "is-a" relationship (e.g., Dog is-a Animal).
   * Example: class Dog extends Animal, inherits move() from Animal.
     
## 3. Polymorphism:
   * Definition: Enables a single interface or method to represent different underlying forms (behaviors).
   * Key Feature: Achieved through method overriding in inheritance (runtime) or overloading in the same class (compile-time), 
   often with interfaces or abstract classes.
### Key Features and Mechanisms
#### Method Overriding (Runtime Polymorphism):
* This occurs when a subclass provides its own specific implementation
for a method that is already defined in its superclass. When the method is called on an object,
the actual method executed depends on the runtime type of the object. This is often referred to as
`dynamic polymorphism or late binding`.
   * Example: WebDriver driver = new ChromeDriver(); (interface-based runtime polymorphism).
     
#### Method Overloading (Compile-Time Polymorphism): 
* This occurs when multiple methods within the same class
have the same name but different parameters (i.e., different number of parameters, different types of parameters, or both).
The compiler determines which method to call based on the arguments provided at compile time.
This is also known as `static polymorphism or early binding`.
 * Example: findMax(int[] nums), findMax(double[] nums), have the same name findMax(),
   but different params and return type: int, double.

####   Interfaces and Abstract Classes: 
* These play a crucial role in achieving polymorphism, particularly runtime polymorphism.
* Interfaces define a contract (a set of methods that a class must implement) but provide no implementation.
  Classes that implement an interface must provide their own implementation for all interface methods,
  allowing for different behaviors under a common interface.
* Abstract classes can have both concrete methods and abstract methods (methods declared but not implemented).
   Subclasses must implement the abstract methods, again leading to varied behaviors for a common type.

* In essence, polymorphism promotes code reusability and flexibility, allowing for more maintainable
  and extensible software designs.

## 4. Abstraction (tells what to do, does not tell how to do):
* Definition: Abstraction hides complex implementation details and exposes only essential features to the user.
  This simplifies the user's interaction with the system, as they only need to understand `what an object does, not how it does it`.
  
### Key Feature: 
* It primarily uses abstract classes or interfaces to define a blueprint or a contract.
  These blueprints declare methods without providing their full implementation, effectively deferring
  the implementation to concrete (non-abstract) subclasses.

#### Abstract Classes: 
* Can have both abstract methods (declared but not implemented) and concrete methods (implemented). 
They can also have member variables. A class can inherit from only one abstract class.
Abstract classes are often used when there's a "is-a" relationship, but the parent class itself isn't meant to be instantiated.

####  Interfaces: 
* Contain only method signatures (and constant fields in some languages) but no method implementations.
 A class can implement multiple interfaces, which is a way to achieve multiple inheritance of type.
 Interfaces define a contract that implementing classes must adhere to.

* Example:  a Vehicle interface with a startEngine() method .
* The Vehicle interface defines the abstract concept that any vehicle can start its engine.
  It doesn't specify how it starts the engine.

* A Car class implementing Vehicle would provide its specific startEngine()
  implementation (e.g., turning a key, pressing a button).

* A Motorcycle class implementing Vehicle would provide its specific startEngine()
  implementation (e.g., kicking a kickstarter, pressing a different button).

* This separation of "what" from "how" makes systems easier to design, understand, and maintain,
 as changes in implementation details don't necessarily affect the way users interact with the abstracted entity.

  * Example: An Vehicle interface with startEngine() method, implemented differently by Car and Motorcycle.

# Lab4 - Practice Tasks: OOP Review (Revised)
## Objective: To apply the core principles of OOP (Encapsulation, Inheritance, Polymorphism, Abstraction) by designing and implementing class hierarchies.

### Instructions:

* For each task, create new Java classes in separate files as needed.

* Include a main method in at least one class for each task to demonstrate your solution.

* Add comments to your code explaining your design choices related to OOP principles.

#### Task 1: Managing Employee Data (Encapsulation)
* Goal: Design an Employee class that properly encapsulates its data, ensuring data integrity for sensitive information like salary.

* Create an Employee class:

It should have the following private fields:

name (String)

salary (double)

* Implement a constructor to initialize name and salary.

* Crucially: The salary must be positive. If a non-positive value is passed during creation, set salary to 0.0 and print a warning message to the console.

* Provide public getter methods for both name (getName()) and salary (getSalary()).

* Important: Do not provide a setter method for any of salary or name to ensure it can only be set at object creation.

* Demonstrate Encapsulation:

In your main method, create two Employee objects:

One with a valid name and positive salary.

One with a valid name and a non-positive salary (e.g., -500.0). Observe the warning message.

Try to directly access and modify the private salary field (e.g., employee.salary = 100000.0;) and observe the compile-time error.

Use the public getter methods (getName(), getSalary()) to retrieve and print the details of both Employee objects.

#### Task 2: Employee Hierarchy (Inheritance) - No changes to this task from previous version.
* Goal: Design a simple employee hierarchy to demonstrate inheritance.

* Create a Employee class:

Fields: name (String), employeeId (String), baseSalary (double).

Constructor to initialize these fields.

Public methods: getDetails() (prints name, ID, and base salary), calculatePay() (returns baseSalary).

Create a Manager class:

This class should inherit from Employee.

Additional field: bonus (double).

Constructor: Initialize inherited fields using super() and its own bonus.

Override the calculatePay() method: It should return baseSalary + bonus.

Override the getDetails() method to also include the bonus amount.

Create a SalesPerson class:

This class should inherit from Employee.

Additional field: salesCommissionRate (double, e.g., 0.05 for 5%).

Additional field: totalSales (double).

Constructor: Initialize inherited fields using super() and its own salesCommissionRate and totalSales.

Override the calculatePay() method: It should return baseSalary + (totalSales * salesCommissionRate).

Override the getDetails() method to also include totalSales and salesCommissionRate.

Demonstrate Inheritance:

In your main method, create instances of Employee, Manager, and SalesPerson.

Call getDetails() and calculatePay() for each instance. Observe how the overridden methods in Manager and SalesPerson provide specialized behavior while still leveraging the base Employee structure.

#### Task 3: Geometric Calculations (Polymorphism - Overriding & Interfaces)
* Goal: Implement polymorphism using separate interfaces for area and perimeter, applied to different geometric shapes.

Create Two Interfaces:

IShapeArea Interface:

Define one abstract method: double calculateArea().

IShapePerimeter Interface:

Define one abstract method: double calculatePerimeter().

Create Concrete Shape Classes:

Ellipse class:

Implements both IShapeArea and IShapePerimeter.

Private fields: majorAxis (double), minorAxis (double).

Constructor to initialize these fields.

Implement calculateArea() (π * majorAxis * minorAxis) and calculatePerimeter() (approx. π * (1.5 * (majorAxis + minorAxis) - sqrt(majorAxis * minorAxis))). 

For simplicity, you can use a simpler approximation for perimeter like π * (majorAxis + minorAxis).

Parallelogram class:

Implements both IShapeArea and IShapePerimeter.

Private fields: base (double), height (double), side (double).

Constructor to initialize these fields.

Implement calculateArea() (base * height) and calculatePerimeter() (2 * (base + side)).

Demonstrate Runtime Polymorphism:

In your main method, create an ArrayList of IShapeArea objects and another ArrayList of IShapePerimeter objects.

Add instances of Ellipse and Parallelogram to both lists (as they implement both interfaces).

Loop 1: Iterate through the IShapeArea list. For each object, call calculateArea() and print the result.

Loop 2: Iterate through the IShapePerimeter list. For each object, call calculatePerimeter() and print the result.

Explain: How does this setup demonstrate runtime polymorphism, allowing you to treat different shapes uniformly based on the interfaces they implement?

#### Task 4: Simple Math Utility (Polymorphism - Overloading)
* Goal: Implement method overloading within a single utility class to perform similar operations on different data types.

Create a MathUtils class:

All methods in this class should be static (no need to create MathUtils objects).

Implement overloaded add methods:

static int add(int a, int b): Returns the sum of two integers.

static double add(double a, double b): Returns the sum of two doubles.

Implement overloaded findMax methods:

static int findMax(int[] numbers): Returns the maximum integer from an array.

static double findMax(double[] numbers): Returns the maximum double from an array.

Demonstrate Compile-time Polymorphism:

In your main method, call each of the overloaded add and findMax methods with different argument types (e.g., MathUtils.add(5, 10); and MathUtils.add(5.5, 10.2);).

Create example integer and double arrays and call the findMax methods.

Print the results of each call.

Explain: How does the Java compiler determine which specific add or findMax method to call when you invoke them?

####  Task 5: Library User Roles (Abstraction & Polymorphism)
* Goal: Design a system to represent different types of library users (Librarian, Student) using abstraction, and demonstrate their polymorphic behavior.

Create an abstract class LibraryUser:

Protected fields: userId (String), name (String).

Constructor: Initialize userId and name.

Public concrete method: getUserDetails() (prints the user's ID and name).

Abstract method: abstract void performDuty(); (This method should describe what a library user does, but not how each specific type does it).

Create Concrete Library User Classes:

Student class:

Extends LibraryUser.

Private field: studentId (String).

Constructor: Initialize inherited fields using super() and its own studentId.

Implement performDuty(): Print a message like "Student [name] is focused on studying and borrowing books."

Librarian class:

Extends LibraryUser.

Private field: employeeId (String).

Constructor: Initialize inherited fields using super() and its own employeeId.

Implement performDuty(): Print a message like "Librarian [name] is assisting patrons and managing the collection."

Demonstrate Abstraction and Polymorphism:

In your main method, create an ArrayList of LibraryUser objects.

Add instances of Student and Librarian to this list.

Iterate through the list. For each LibraryUser object:

Call getUserDetails().

Call performDuty().

Explain: How does the LibraryUser abstract class provide a common "blueprint" for different user types, and how does calling performDuty() on LibraryUser references demonstrate polymorphism?
####  Task 6: Vehicle Energy Management (Advanced Abstraction & Interfaces)
* Goal: Explore abstraction and interfaces for managing vehicle operations and energy.

Create an abstract class AbstractVehicle:

Protected fields: make (String), model (String).

Constructor: Initialize make and model.

Public concrete method: getDetails() (prints make and model).

Abstract methods:

abstract void start();

abstract void stop();

Create an IEnergizing Interface:

Define one abstract method: void getEnergy(); (This method represents the action of getting fuel/charge).

Create Concrete Vehicle Classes:

GasCar class:

Extends AbstractVehicle and implements IEnergizing.

Constructor: Initialize inherited fields.

Implement start(): Print "Gas Car engine starts."

Implement stop(): Print "Gas Car engine stops."

Implement getEnergy(): Print "Filling gas tank with gasoline."

ElectricBike class:

Extends AbstractVehicle and implements IEnergizing.

Constructor: Initialize inherited fields.

Implement start(): Print "Electric Bike motor whirs to life."

Implement stop(): Print "Electric Bike motor powers down."

Implement getEnergy(): Print "Charging battery at a charging station."

Demonstrate Abstraction and Polymorphism:

In your main method, create an ArrayList of AbstractVehicle objects and an ArrayList of IEnergizing objects.

Add instances of GasCar and ElectricBike to both lists where appropriate.

Loop 1 (Vehicles): Iterate through the AbstractVehicle list. For each vehicle, call getDetails(), start(), and stop().

Loop 2 (Energizing): Iterate through the IEnergizing list. For each item, call getEnergy().

Discuss: How does this design allow you to treat GasCar and ElectricBike uniformly for starting/stopping (via AbstractVehicle) and for getting energy (via IEnergizing), even though their underlying implementations are different?

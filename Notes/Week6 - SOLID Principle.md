# SOLID Principles

* SOLID is a set of five object-oriented design principles that guide developers
  in writing clean, maintainable, and scalable code. The acronym SOLID stands for:
  * Single Responsibility Principle,
  * Open/Closed Principle,
  * Liskov Substitution Principle,
  * Interface Segregation Principle, and
  * Dependency Inversion Principle.
###	Single Responsibility Principle (SRP): Refactor for Single Responsibility

* A class should have only one reason to change.
```java
// NOT SRP: class doing too much
class Notifier {
    void sendEmail() { /* sending email logic */ }
    void sendSMS() { /* sending sms logic */ }
}

// SRP-compliant: responsibilities split
class EmailSender { void sendEmail() { /* ... */ } }
class SMSSender { void sendSMS() { /* ... */ } }
```  
  This means a class should be responsible for a single, well-defined task. Split the responsibilities into separate classes [one responsibility into one class].

###	Open/Closed Principle (OCP):
* Software entities (classes, modules, etc.) should be open for extension but closed for modification.

  This means you should be able to add new functionality without altering the existing code. 
```java
abstract class Shape { abstract double calculateArea(); }
class Circle extends Shape { /* ... */ }
class Square extends Shape { /* ... */ }

// OCP: Adding new shape doesn’t require changing Shape code.
```
###	Liskov Substitution Principle (LSP): ## 
* Subtypes should be substitutable for their base types.
* Only appropriate classes can use certain features. [Bad: Vehicle refeul(). Good: Gas car refeul(), Electric car recharge()]
 
  This means that a derived class should be able to replace its parent class without causing any problems. 
```java
//Not LSP!
class Car { void refeul() { /* ... */ } }
class ElectricCar extends Car { /* ElectricCar can’t refeul – violates LSP! */ }

Good LSP: Use interfaces: interface ElectricVehicle { void recharge(); }
```

###	Interface Segregation Principle (ISP):
* Clients should not be forced to depend on methods they do not use.

  This means that interfaces should be broken down into smaller, more specific interfaces to avoid unnecessary dependencies. 
```java
interface Machine { void print(); void scan(); void fax(); }
// ISP violation: not all printers fax! Split interfaces:

interface Printer { void print(); }
interface Scanner { void scan(); }
```
###	Dependency Inversion Principle (DIP): [change tight coupling to loose coupling ]

* High-level modules should not depend on low-level modules. Both should depend on abstractions. Abstractions should not depend on details. Details should depend on abstractions.

  This means that dependencies should be resolved through abstraction, rather than concrete implementations.

### Without DIP (“bad”): ##
```java
class EmailSender {
    void send(String msg) { System.out.println("Email: " + msg); }
}

class OrderService {
    private final EmailSender sender = new EmailSender();
    void confirmOrder() {
        sender.send("Your order is confirmed.");
    }
}
```
* Problem: OrderService is tightly coupled to EmailSender. What if you want to add SMS, or change notification?

 ### With DIP (“good”): ##
 ```java
// Abstraction (depends on interfaces)
interface Notifier {
    void send(String message);
}

// Low-level implementations
class EmailSender implements Notifier {
    public void send(String msg) { System.out.println("Email: " + msg); }
}
class SmsSender implements Notifier {
    public void send(String msg) { System.out.println("SMS: " + msg); }
}

// High-level module depends on abstraction, not concrete class
class OrderService {
    private final Notifier notifier;
    public OrderService(Notifier notifier) { this.notifier = notifier; }

    void confirmOrder() {
        notifier.send("Your order is confirmed.");
    }
}

// Demo (main)
public class Demo {
    public static void main(String[] args) {
        Notifier email = new EmailSender();
        Notifier sms = new SmsSender();

        OrderService emailOrder = new OrderService(email);
        OrderService smsOrder = new OrderService(sms);

        emailOrder.confirmOrder(); // Email: Your order is confirmed.
        smsOrder.confirmOrder();   // SMS: Your order is confirmed.
    }
}
```
# Pros:
* OrderService cares only about the contract (Notifier), not the implementation.

* Can add new notification types (Slack, WhatsApp, Mock) with no changes to OrderService.

* Promotes loose coupling, extensibility, and easier maintenance.
  
By following `SOLID` principles, developers can create `more flexible, maintainable, and scalable object-oriented software`. 

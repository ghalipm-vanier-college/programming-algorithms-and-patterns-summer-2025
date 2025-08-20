# SOLID Principles

* SOLID is a set of five object-oriented design principles that guide developers
  in writing clean, maintainable, and scalable code. The acronym SOLID stands for:
  * Single Responsibility Principle,
  * Open/Closed Principle,
  * Liskov Substitution Principle,
  * Interface Segregation Principle, and
  * Dependency Inversion Principle.
###	Single Responsibility Principle (SRP):
* A class should have only one reason to change.

  This means a class should be responsible for a single, well-defined task. 

###	Open/Closed Principle (OCP):
* Software entities (classes, modules, etc.) should be open for extension but closed for modification.

  This means you should be able to add new functionality without altering the existing code. 

###	Liskov Substitution Principle (LSP):
* Subtypes should be substitutable for their base types without altering the correctness of the program.
 
  This means that a derived class should be able to replace its parent class without causing any problems. 

###	Interface Segregation Principle (ISP):
* Clients should not be forced to depend on methods they do not use.

  This means that interfaces should be broken down into smaller, more specific interfaces 
 to avoid unnecessary dependencies. 

###	Dependency Inversion Principle (DIP): [change tight coupling to loose coupling ]
* High-level modules should not depend on low-level modules. Both should depend on abstractions. Abstractions should not depend on details. Details should depend on abstractions.

  This means that dependencies should be resolved through abstraction, rather than concrete implementations. 

By following `SOLID` principles, developers can create `more flexible, maintainable, and scalable object-oriented software`. 

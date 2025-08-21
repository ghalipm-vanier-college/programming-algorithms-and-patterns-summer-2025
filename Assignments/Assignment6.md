
# Assignment 6

***

### Question 1: Single Responsibility Principle (SRP)  
**Context:** Build a payment processing module.  
- Create separate classes to handle payment authorization, payment processing, and receipt printing.  
- Each class should have one responsibility without overlapping.  
- Example: AuthorizationHandler authorizes cards, PaymentProcessor processes payment, ReceiptPrinter prints receipts.

***

### Question 2: Open/Closed Principle (OCP)  
**Context:** Payment types extension.  
- Design an abstract base class `Payment` with method `pay(amount)`.  
- Implement concrete subclasses: `CreditCardPayment` and `DebitCardPayment`.  
- Add a new payment type `PaypalPayment` without changing existing classes but by extension only.  
- Demonstrate polymorphic payment processing.

***

### Question 3: Liskov Substitution Principle (LSP)  
**Context:** Payment method behavior.  
- Base class `PaymentMethod` with `pay(amount)`.  
- Subclass `CreditCard` overrides `pay` with credit-specific logic.  
- Subclass `DebitCard` that may throw exception if funds insufficient, ensure it fully satisfies `PaymentMethod` expectations (no surprises).  
- Design so all subclasses can be substituted without breaking client code.

***

### Question 4: Interface Segregation Principle (ISP)  
**Context:** Card functionalities.  
- Separate interfaces:  
  - `ICard` with `getCardDetails()` and `validate()`.  
  - `IRechargeable` with `recharge(amount)` (e.g., for prepaid debit cards).  
  - `ICredit` with `increaseCreditLimit(amount)` (only for credit cards).  
- Implement `DebitCard` and `CreditCard` classes implementing only the interfaces relevant to them.

***

### Question 5: Dependency Inversion Principle (DIP)  
**Context:** Payment gateway integration.  
- Define a `PaymentGateway` interface with `processPayment(amount)`.  
- Implement `StripeGateway` and `PaypalGateway`.  
- `PaymentProcessor` depends on `PaymentGateway` interface, not on concrete gateway classes.  
- Demonstrate how to use different gateways without changing `PaymentProcessor`.

***

### Question 6: Spring MVC Web Application – Display Book Catalog

**Context:**  
Implement a simple Spring MVC web application to display a catalog of books.

**Requirements:**  
- Create a `Book` model class with the following fields:  
  - `String name`  
  - `String author`  
  - `String isbn`  
  - `int year`  
  - `double price`  
- In the Controller, create a list of 6 hardcoded `Book` instances.  
- Implement a method to handle HTTP GET request (`/books`) that passes the list of books to a Thymeleaf view.  
- In the Thymeleaf template, display the list of books in tabular format showing all details.  
- No database is required; use hardcoded book data.

**Deliverables:**  
- `Book.java` model class code  
- Spring MVC Controller code with the list of 6 books  
- Thymeleaf HTML template for displaying the book catalog  

**Objective:**  
Understand and implement the MVC pattern by clearly separating the Model (Book), Controller (data provisioning), and View (Thymeleaf template rendering).

## Remark:  
- Keep your code modular, focused, and well-commented.  
- Use interfaces and abstract classes appropriately.  
- Print meaningful output demonstrating the principle or pattern in action.  

***

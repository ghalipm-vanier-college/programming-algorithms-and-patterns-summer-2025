Spring Boot simplifies the MVC pattern for web applications. The framework handles much of the boilerplate, allowing you to focus on the three core components. Here's a concise example of a web application that lists products.

# Project Structure
### A standard Spring Boot MVC project looks like this:

<img width="711" height="371" alt="image" src="https://github.com/user-attachments/assets/5a727bbb-9d18-4460-a5c2-62240db95400" />

## 1. The Model: `Product.java`
The `Model` is a simple Java class (a POJO - Plain Old Java Object) that represents the data. 
It has no knowledge of the web layer.

```java
@NoArgsConstructor
@AllArgsConstructor
@Getter
@Setter
public class Product {
    private long id;
    private String name;
    private String producer;
}
```

## 2. The Controller: `ProductController.java`
The Controller handles incoming HTTP requests, interacts with the model, and selects the appropriate view to render. The @Controller annotation identifies this class as the controller.

```java
package com.vanier.demo.controller;

import com.vanier.demo.model.Product;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

import java.util.Arrays;
import java.util.List;

/**
 * @author ghalipm on 8/18/2025
 * @project vaniercollege
 */
@Controller
public class ProductController {

    @GetMapping("/products")
    public String listProducts(Model model) {
        // 1. Controller interacts with a "service" or "repository" to get data
        // (In this simple example, we're creating dummy data)
        List<Product> products = Arrays.asList(
                new Product(1, "Laptop", "Dell"),
                new Product(2, "Mouse", "LogIt"),
                new Product(3, "Keyboard", "Fame")
        );

        // 2. Controller populates the Model with data to be displayed
        model.addAttribute("products", products);

        // 3. Controller returns the name of the View template
        return "products";
    }
}

```

## 3. The View: products.html
The View is an HTML template that renders the data provided by the controller. This example uses Thymeleaf, a popular template engine in Spring Boot. It uses th:each to iterate over the products list passed from the controller and th:text to display the data.
```
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Product List</title>
    
  <style>
        /* A more robust and clean approach */
        table {
            /* Set the border color for the table as a whole */
            border: 2px solid #00F;

            /* Collapse the borders to avoid double lines */
            border-collapse: collapse;

            /* Add some spacing for better readability */
            margin-top: 20px;
            width: 100%;
        }

        th, td {
            /* Set the border color for cells, which overrides the main table border */
            border: 2px solid #ccc;
            padding: 8px; /* Add some padding inside the cells */
            text-align: left; /* Align text to the left */
        }
    </style>
    
</head>
<body>
    <h1>Available Products</h1>
    <table>
        <thead>
            <tr>
                <th>ID</th>
                <th>Name</th>
               <th>Producer</th>
            </tr>
        </thead>
        <tbody>
            <tr th:each="product : ${products}">
                <td th:text="${product.id}"></td>
                <td th:text="${product.name}"></td>
               <td th:text="${product.producer}"></td>
            </tr>
        </tbody>
    </table>
</body>
</html>
```

## 4. The Application: `DemoApplication.java`
This is the main class that starts the Spring Boot application.

```java
@SpringBootApplication
public class DemoApplication {

	public static void main(String[] args) {
		SpringApplication.run(DemoApplication.class, args);
	}

}

## To Run:

Add the `spring-boot-starter-web` and `spring-boot-starter-thymeleaf` dependencies to your `pom.xml` (Maven) or build.gradle (Gradle) file.

Run the `DemoApplication.java` file.

Navigate to `http://localhost:8080/products` in your web browser. You'll see a web page listing the three products.
```

Spring Boot simplifies the MVC pattern for web applications. The framework handles much of the boilerplate, allowing you to focus on the three core components. Here's a concise example of a web application that lists products.

# Project Structure
### A standard Spring Boot MVC project looks like this:

<img width="711" height="371" alt="image" src="https://github.com/user-attachments/assets/5a727bbb-9d18-4460-a5c2-62240db95400" />

## 1. The Model: `Product.java`
The Model is a simple Java class (a POJO - Plain Old Java Object) that represents the data. 
It has no knowledge of the web layer.


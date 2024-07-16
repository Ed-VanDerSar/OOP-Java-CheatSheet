# OOP-Java-CheatSheet
Java Cheat Sheet


## Table of Contents 
1. [Key Concepts](#1-key-concepts)
2. [Inheritance](#2-inheritance)
3. [Polymorphism](#3-polymorphism)
4. [Encapsulation](#5-encapsulation)
5. [Abstraction](#6-abstraction)

## 1. Key Concepts

1. __Class:__ A template used to create objects
```java
   public class ClassName {
       // Atributos (variables)
       // Methods (behaviour)
   }
```
2. __Object:__ Is the instance of a class 
```java
   ClassName obj = new ClassName();
```
### Example 
```java
 // Class definition
public class Car {
    // Fields
    int year;
    String model;

    // Constructor
    public Car(int year, String model) {
        this.year = year;
        this.model = model;
    }

    // Method
    public void display() {
        System.out.println("Model: " + model + ", Year: " + year);
    }
}

// Main class
public class Main {
    public static void main(String[] args) {
        // Creating an object
        Car myCar = new Car(2020, "Toyota");
        myCar.display(); // Method call
    }
}
```


## 2. Inheritance 

**Definition:** Inheritance is one of the four fundamental principles of Object-Oriented Programming (OOP). It is the mechanism by which one class (subclass) can inherit the attributes and methods of another class (superclass). Inheritance promotes code reuse and establishes a hierarchical relationship between classes, allowing subclasses to extend or modify the behavior of their superclasses.

**Example:** Consider a base class Animal that has a method makeSound(). You might have subclasses like Dog and Cat that inherit from Animal, each implementing its own version of the makeSound() method. This allows defining specific behaviors for each type of animal without duplicating common code.

**Benefits:**

Facilitates code reuse.
Promotes hierarchical organization and structure of classes.
Allows code extensibility.
Simplifies code maintenance and modification.


**How to Achieve Inheritance:**

Using the extends keyword in Java to let one class inherit from another.
Overriding superclass methods in the subclass when necessary.




## 3. Polymorphism

Polymorphism is a core concept in Object-Oriented Programming (OOP) that allows methods to perform different tasks based on the object that it is acting upon. It provides a way to use a single interface to represent different underlying forms (data types).

### Key Points of Polymorphism

1. **Compile-time (Static) Polymorphism**: Achieved through method overloading.
2. **Run-time (Dynamic) Polymorphism**: Achieved through method overriding.

### Benefits of Polymorphism

- **Flexibility**: Write more general and reusable code.
- **Maintainability**: Easier to maintain and update code.

### Types of Polymorphism

#### 1. Compile-time (Static) Polymorphism

This type of polymorphism is achieved by method overloading. It allows a class to have more than one method with the same name, as long as their parameter lists are different.

##### Example of Method Overloading

```java
public class MathOperations {
    // Method to add two integers
    public int add(int a, int b) {
        return a + b;
    }

    // Method to add three integers
    public int add(int a, int b, int c) {
        return a + b + c;
    }

    // Method to add two double values
    public double add(double a, double b) {
        return a + b;
    }
}
```

public class Main {
    public static void main(String[] args) {
        MathOperations math = new MathOperations();

        System.out.println(math.add(5, 3));           // Output: 8
        System.out.println(math.add(5, 3, 2));        // Output: 10
        System.out.println(math.add(5.5, 3.3));       // Output: 8.8
    }
}
```


## 4. Encapsulation


## 5. Abstraction

**Definition:** Abstraction is one of the four fundamental principles of OOP. It is the process of hiding the complex implementation details and showing only the essential features of an object. Abstraction allows programmers to reduce complexity and increase efficiency by focusing on what an object does rather than how it does it.

**Example:** Consider a car. When you drive a car, you only need to know how to use the steering wheel, pedals, and gear shift. You don't need to understand the complex mechanisms of the engine or the electrical systems. Similarly, in OOP, abstraction allows you to use objects without needing to know all the intricate details of their implementation.

**Benefits:**
- Simplifies code by reducing complexity.
- Enhances code readability and maintainability.
- Facilitates code reuse and modularity.

**How to Achieve Abstraction:** 
- Using abstract classes and interfaces.
- Use the interface keyword to create an interface
- Use the implements keyword to implement a interface in a class 
- Use the abstract keyword before the class keyword when defining an abstract class.
- For each method where you don't implement the details, use the abstract keyword before the return type of the method.
- Defining methods without implementing their details, leaving the specifics to the derived classes.
- When you extend an abstract class to a normal class, you need to override all the abstract methods.

### Example with abstract classes 

**Code Example in Java:**
```java
abstract class Car {
    abstract void startEngine();
    abstract void stopEngine();
}

class Sedan extends Car {
    @Override
    void startEngine() {
        System.out.println("Sedan engine started.");
    }
    
    @Override
    void stopEngine() {
        System.out.println("Sedan engine stopped.");
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Sedan();
        myCar.startEngine();
        myCar.stopEngine();
    }
}
```
### Example with interfaces 
```
// Define an interface
interface Payment {
    void processPayment(double amount);
}

// Implement the interface in a class
class CreditCardPayment implements Payment {
    @Override
    public void processPayment(double amount) {
        System.out.println("Processing credit card payment of $" + amount);
    }
}

// Implement the interface in another class
class PayPalPayment implements Payment {
    @Override
    public void processPayment(double amount) {
        System.out.println("Processing PayPal payment of $" + amount);
    }
}

public class Main {
    public static void main(String[] args) {
        Payment creditCardPayment = new CreditCardPayment();
        Payment payPalPayment = new PayPalPayment();
        
        creditCardPayment.processPayment(100.00);
        payPalPayment.processPayment(200.00);
    }
}
```






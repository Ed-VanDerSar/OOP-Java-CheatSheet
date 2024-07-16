# OOP-Java-CheatSheet
Java Cheat Sheet


## Table of Contents 
1. [Key Concepts]{#1}
2. Inheritance
3. Polymorphism
4. Overriding and Overloading 
5. Encapsulation
6. Abstraction

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


## Inheritance 

## Abstraction

**Definition:** Abstraction is one of the four fundamental principles of OOP. It is the process of hiding the complex implementation details and showing only the essential features of an object. Abstraction allows programmers to reduce complexity and increase efficiency by focusing on what an object does rather than how it does it.

**Example:** Consider a car. When you drive a car, you only need to know how to use the steering wheel, pedals, and gear shift. You don't need to understand the complex mechanisms of the engine or the electrical systems. Similarly, in OOP, abstraction allows you to use objects without needing to know all the intricate details of their implementation.

**Benefits:**
- Simplifies code by reducing complexity.
- Enhances code readability and maintainability.
- Facilitates code reuse and modularity.

**How to Achieve Abstraction:** 
- Using abstract classes and interfaces.
- Defining methods without implementing their details, leaving the specifics to the derived classes.

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


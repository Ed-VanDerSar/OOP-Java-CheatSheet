# OOP-Java-CheatSheet
Java Cheat Sheet


## Table of Contents 
1. [Key Concepts](#1-key-concepts)
2. [Inheritance](#2-inheritance)
3. [Polymorphism](#3-polymorphism)
4. [Overriding and Overloading](#4_overriding_and_overloading)
5. [Encapsulation](#5-encapsulation)
6. [Abstraction](#6-abstraction)

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

ExampleGet your own Java Server
class Vehicle {
  protected String brand = "Ford";        // Vehicle attribute
  public void honk() {                    // Vehicle method
    System.out.println("Tuut, tuut!");
  }
}

class Car extends Vehicle {
  private String modelName = "Mustang";    // Car attribute
  public static void main(String[] args) {

    // Create a myCar object
    Car myCar = new Car();

    // Call the honk() method (from the Vehicle class) on the myCar object
    myCar.honk();

    // Display the value of the brand attribute (from the Vehicle class) and the value of the modelName from the Car class
    System.out.println(myCar.brand + " " + myCar.modelName);


## 3. Polymorphism


## 4. Overriding and Overloading 


## 5. Encapsulation


## 6. Abstraction

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





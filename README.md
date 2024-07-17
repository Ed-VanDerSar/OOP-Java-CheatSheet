# $\color{Apricot}{Java-OOP-CheatSheet}$
 Java Object-Oriented Programming (OOP) Cheatsheet :coffee:
<br>

> Welcome to the comprehensive Java Object-Oriented Programming (OOP) Cheatsheet, designed to provide you with a quick reference to the essential concepts, principles, and syntax of OOP in Java.
> 
>  :e-mail: Authors: [Diego Aldana](https://github.com/PucBro),  [Yodak Aldana](https://github.com/Yodak91) and 
[Edwin Anzures](https://github.com/Ed-VanDerSar)
>  



<br>

## Table of Contents 
1. [Key Concepts](#1-key-concepts-bookmark)
2. [Inheritance](#2-inheritance-bookmark)
3. [Polymorphism](#3-polymorphism-bookmark)
4. [Encapsulation](#4-encapsulation-bookmark)
5. [Abstraction](#5-abstraction-bookmark)

## 1. Key Concepts :bookmark:

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


## 2. Inheritance :bookmark:

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
```java
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
  }
}
```



## 3. Polymorphism :bookmark:

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


public class Main {
    public static void main(String[] args) {
        MathOperations math = new MathOperations();

        System.out.println(math.add(5, 3));           // Output: 8
        System.out.println(math.add(5, 3, 2));        // Output: 10
        System.out.println(math.add(5.5, 3.3));       // Output: 8.8
    }
}
```


## 4. Encapsulation :bookmark:

Encapsulation is a fundamental concept of Object-Oriented Programming (OOP) in Java. It is the mechanism of wrapping the data (variables) and the code (methods) acting on the data into a single unit, usually a class. This helps to keep the data safe from outside interference and misuse.

### Key Points of Encapsulation


* Data Hiding: Internal object details are hidden from the outside world. Only essential aspects are exposed through a public interface.
* Access Modifiers: Java provides four access modifiers: private, default, protected, and public to achieve encapsulation.
* Getter and Setter Methods: Used to access and update the values of private fields.

### Benefits of Encapsulation

* Control: The class controls what is stored and how it is accessed.
* Flexibility and Maintainability: The internal representation of an object can be changed without affecting the outside code.
* Improved Security: Restricts unauthorized access to certain components of an object.

### Example of an encapsulated class

```java
public class Person {
    // Private fields
    private String name;
    private int age;

    // Getter method for name
    public String getName() {
        return name;
    }

    // Setter method for name
    public void setName(String name) {
        this.name = name;
    }

    // Getter method for age
    public int getAge() {
        return age;
    }

    // Setter method for age
    public void setAge(int age) {
        if (age > 0) {
            this.age = age;
        } else {
            System.out.println("Please enter a valid age.");
        }
    }
}
```
### Access Modifiers in Java

| Modifier      | Class | Package | Subclass (same package) | Subclass (different package) | World |
|---------------|-------|---------|-------------------------|------------------------------|-------|
| **public**    | Yes   | Yes     | Yes                     | Yes                          | Yes   |
| **protected** | Yes   | Yes     | Yes                     | Yes                          | No    |
| **no modifier (default)** | Yes   | Yes     | Yes                     | No                           | No    |
| **private**   | Yes   | No      | No                      | No                           | No    |

### Description

- **public**: The member is accessible from any other class.
- **protected**: The member is accessible within its own package and by subclasses.
- **no modifier (default)**: The member is accessible only within its own package.
- **private**: The member is accessible only within its own class.

### Code Example
```java
public class AccessModifiers {
    public int publicVar = 1;
    protected int protectedVar = 2;
    int defaultVar = 3; // default access modifier
    private int privateVar = 4;

    public static void main(String[] args) {
        AccessModifiers am = new AccessModifiers();
        System.out.println("Public: " + am.publicVar);
        System.out.println("Protected: " + am.protectedVar);
        System.out.println("Default: " + am.defaultVar);
        System.out.println("Private: " + am.privateVar);
    }
}

### Example of the Main Class to Demonstrate Encapsulation

```java
public class Main {
    public static void main(String[] args) {
        // Creating an object of the Person class
        Person person = new Person();

        // Setting values using setter methods
        person.setName("John Doe");
        person.setAge(30);

        // Accessing values using getter methods
        System.out.println("Name: " + person.getName()); // Output: Name: John Doe
        System.out.println("Age: " + person.getAge());   // Output: Age: 30
    }
}
```
### Explanation

* The `Person` class has private fields `name` and `age`.
* Public getter and setter methods are provided to access and update these private fields.
* The `setAge` method includes a validation check to ensure the age is positive.
* In the `Main` class, an object of the `Person` class is created, and its fields are accessed and modified using the getter and setter methods.
  ## Modifiers in Java: abstract, final, static

| Modifier  | Applied to            | Description                                                                                      |
|-----------|-----------------------|--------------------------------------------------------------------------------------------------|
| **abstract** | Classes, Methods    | Must be implemented by subclasses if it's a class, and must be overridden if it's a method.       |
| **final**  | Classes, Methods, Fields | Prevents modification: class cannot be subclassed, method cannot be overridden, field value cannot be changed. |
| **static** | Methods, Fields, Nested Classes | Belongs to the class rather than instances of the class. Shared among all instances.             |

### Code Examples

#### abstract Example
```java
abstract class Animal {
    abstract void makeSound(); // Abstract method

    void sleep() {
        System.out.println("Zzz...");
    }
}

class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Bark");
    }

    public static void main(String[] args) {
        Dog myDog = new Dog();
        myDog.makeSound();
        myDog.sleep();
    }
}
```


  <br>

> [!IMPORTANT]
> Encapsulation ensures that the internal state of an object is protected and can only be modified through well-defined methods, enhancing the robustness and maintainability of the code.


## 5. Abstraction :bookmark:

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
###  Differences between Abstract Classes and Interfaces 

| Feature                       | Abstract Classes                                   | Interfaces                                         |
|-------------------------------|----------------------------------------------------|----------------------------------------------------|
| **Keyword**                   | `abstract`                                         | `interface`                                        |
| **Method Implementation**     | Can have both abstract and fully implemented methods | Can only have abstract methods (Java 7 and earlier), can have default and static methods (Java 8 and later) |
| **Fields**                    | Can have instance variables (fields)               | Can only have static final variables (constants)   |
| **Multiple Inheritance**      | A class can inherit only one abstract class        | A class can implement multiple interfaces          |
| **Constructors**              | Can have constructors                             | Cannot have constructors                           |
| **Access Modifiers**          | Can have all types of access modifiers (public, protected, private) | Methods are public and abstract by default, and fields are public, static, and final by default |
| **Inheritance**               | Used when classes share a common base class and want to share code (inherit behavior) | Used to define a contract that multiple classes can implement |
| **Use Case**                  | Best for when classes share a common state and behavior | Best for defining a contract that unrelated classes can implement |
| **Keyword while using it on a class** | `extends` | `implements` |
| **Keyword while using it on a interface** | This can not happen | `interface` |


<a name="top"></a>




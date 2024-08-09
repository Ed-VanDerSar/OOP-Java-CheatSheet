# $\color{Apricot}{Herencia en Java}$

## Introduction

Inheritance is a core concept in Java and object-oriented programming (OOP) that allows a new class to inherit properties and behavior from an existing class. This promotes code reuse, reduces redundancy, and helps in maintaining a hierarchical class structure.

## What is Inheritance?

Inheritance in Java is the mechanism where one class, known as the subclass (or child class), derives properties and behaviors (fields and methods) from another class, known as the superclass (or parent class). The subclass inherits everything from the superclass, but it can also have its own additional properties and methods, or override the inherited ones.

## Syntax

The inheritance relationship is established using the extends keyword:
```java
class Superclass {
    // Fields and methods of the superclass
}

class Subclass extends Superclass {
    // Additional fields and methods or overridden methods
}
```

## Example

Let’s consider a simple example:
```java
class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("The dog barks.");
    }
}
```
In this example, Dog is a subclass of Animal. The Dog class inherits the eat method from the Animal class and adds a new method bark.

## How It Works

With inheritance, the subclass has access to all non-private fields and methods of the superclass. You can create an instance of the subclass and call both its own methods and the inherited ones:
```java
Dog myDog = new Dog();
myDog.eat();  // Inherited method from Animal class
myDog.bark(); // Method from Dog class
```

## Overriding Methods

One powerful feature of inheritance is method overriding. This allows a subclass to provide a specific implementation for a method that is already defined in its superclass. This is done by defining a method in the subclass with the same signature as the method in the superclass:
```java
class Dog extends Animal {
    @Override
    void eat() {
        System.out.println("The dog eats bones.");
    }
}
```
Here, the eat method in the Dog class overrides the eat method in the Animal class. When myDog.eat() is called, it uses the overridden method in the Dog class.

## Access Control and Inheritance

Private members of the superclass are not accessible directly in the subclass.
Protected members are accessible within the same package or subclasses.
Public members are accessible everywhere.
Default (package-private) members are accessible within the same package but not outside it.
Benefits of Inheritance

Code Reusability: Inheritance allows you to reuse code from the superclass without having to rewrite it.
Extensibility: You can easily extend existing classes and add new functionality.
Polymorphism: Inheritance enables polymorphism, where a subclass can be treated as an instance of its superclass, allowing for dynamic method binding and more flexible code.
## Conclusion

Inheritance is a fundamental concept in Java that helps in building a clear and maintainable code structure. By using inheritance, you can create a hierarchy of classes that share common behavior, reducing code duplication and enhancing the modularity of your application.

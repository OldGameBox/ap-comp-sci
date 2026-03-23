## Classes and Objects
A **Class** is a blueprint or a template for creating objects. It defines what data the object will hold and what it can do. An **Object** is a specific instance of a class.
```java
// The Class (Blueprint)
public class Dog {
    String breed;
    int age;
}

// Creating an Object (Instance)
Dog myDog = new Dog();
```
- **Exception:** You cannot use a class until you instantiate it using the `new` keyword, unless the methods inside are static.
## Instance Variables and Methods
**Instance Variables** are the data or attributes of an object. They define the "state." **Instance Methods** are the actions or behaviors an object can perform.
```java
public class Car {
    // Instance Variables
    String color;
    int speed;

    // Instance Method
    public void accelerate() {
        speed += 10;
    }
}
```
- **Note:** Every object gets its own copy of instance variables. If you change `myCar.color`, it does not change `yourCar.color`.
## Access Modifiers
These keywords control who can see or use your code.
- **public:** The code is accessible by any other class.  
- **private:** The code is only accessible within the class it is defined in.
```java
public class BankAccount {
    private double balance; // Only this class can see the balance
    public String accountName; // Anyone can see the name
}
```
- **Exception:** Even if a variable is private, it can still be changed if the class provides a public method to do so.
## Getters and Setters
Because instance variables are usually `private` (to protect data), we use **Getters** to read the value and **Setters** to change the value.
```java
public class Student {
    private int grade;

    // Getter
    public int getGrade() {
        return grade;
    }

    // Setter
    public void setGrade(int newGrade) {
        if (newGrade >= 0 && newGrade <= 100) {
            grade = newGrade;
        }
    }
}
```
## Static Methods and Variables
The keyword `static` means the variable or method belongs to the **Class itself**, not a specific object.
```java
public class Player {
    public static int playerCount = 0; // Shared by all players

    public Player() {
        playerCount++; // Increases every time a new player is made
    }
}
```
- **Exception:** Static methods cannot use instance variables directly because static methods don't belong to a specific object.
## Inheritance
**Inheritance** allows one class (Subclass) to derive features from another class (Superclass) using the `extends` keyword.
```java
public class Animal {
    public void eat() {
        System.out.println("Eating...");
    }
}

public class Cat extends Animal {
    public void meow() {
        System.out.println("Meow!");
    }
}
```
- **Note:** A subclass inherits all public methods but cannot directly access private variables of the superclass.
## Overloading vs. Overriding
- **Overloading:** Two methods in the **same class** have the same name but different parameters.
- **Overriding:** A subclass provides a **new version** of a method that already exists in its superclass.
```java
public class Calculator {
    // Overloading (same name, different inputs)
    public int add(int a, int b) { return a + b; }
    public double add(double a, double b) { return a + b; }
}

public class Robot extends Animal {
    // Overriding (changing inherited behavior)
    @Override
    public void eat() {
        System.out.println("Charging battery instead of eating.");
    }
}
```
## Polymorphism
**Polymorphism** allows us to treat objects of different subclasses as objects of the same superclass. It ensures the correct method is called at runtime.
```java
Animal myPet = new Cat(); // A Cat is an Animal
myPet.eat(); // Calls the Animal version or overridden version
```
- **Exception:** You can only call methods that are defined in the Superclass. If `Cat` has a `meow()` method that isn't in `Animal`, you cannot call `myPet.meow()` while it is stored in an `Animal` variable.
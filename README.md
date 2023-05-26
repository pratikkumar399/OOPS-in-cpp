# OOPS in C++

Hello everyone, and welcome to this blog post. Today, we will discuss Object-Oriented Programming (OOP) in C++. This article will provide a brief overview of the essential concepts in OOP in C++.

## Introduction to OOP

Object-Oriented Programming is all about objects. In C++, unlike in C, we can use OOP to create objects that encapsulate both data members and functions into a single entity. Let's dive into the key terms in C++ OOP:

1. **Class**: A class is a fundamental building block in OOP. It contains both data members and functions. For example, a class "Car" may have properties like color and weight, as well as methods like drive and brake.

2. **Objects**: An object is an instance of a class. Each object has its own set of data members and can access the class's methods. For instance, a Mercedes, an Audi, and a Nano could be objects of the Car class.

3. **Encapsulation**: Encapsulation is the concept of bundling data members and methods within a class, hiding sensitive information and exposing only what is necessary. Access specifiers (public, private, protected) control the accessibility of class members.

4. **Abstraction**: Abstraction involves hiding complex implementation details and providing a simplified interface for users. It allows users to focus on the essential features of an object or system. Private access modifiers are used to achieve data abstraction or data hiding.

5. **Inheritance**: Inheritance allows a class to inherit properties and characteristics from another class. It promotes code reuse and establishes a parent-child relationship between classes. The child class (derived class) inherits features from the parent class (base class).

6. **Polymorphism**: Polymorphism refers to the ability of a function or method to take different forms depending on the context. There are two types of polymorphism in C++: compile-time polymorphism (function overloading) and runtime polymorphism (function overriding).

In the upcoming sections, we will delve deeper into each of these topics, providing code snippets and examples to enhance understanding.

## Class and Object Example

Let's begin with a code snippet illustrating a class and an object in C++:

```cpp
#include <iostream>
using namespace std;

class Car {
   private:
    int color;
    int weight;

   public:
    void drive() {
        cout << "Drive the car" << endl;
    }

    void brake() {
        cout << "Stop the car" << endl;
    }
};

int main() {
    Car obj1;
    obj1.drive();
    obj1.brake();
    return 0;
}

```

## Encapsulation

To understand the concept of encapsulation, let's first understand access specifiers.

Access modifiers help us decide how the member functions can be accessed outside the class. In C++, there are three access modifiers:

- **Private**: Data members declared as private cannot be accessed outside the class.

```cpp
class Private {
private:
    int x;
    void show();
};
```

- **Public**: Data members declared as public can be accessed outside the class.

```cpp
class Public {
public:
    int x;
    void show();
};
```

- **Protected**: Data members declared as protected can only be accessed inside the inherited classes.

```cpp
class Protected {
protected:
    int x;
    void display();
};
```

In C++, the data members of a class are public by default.

Now, let's discuss what encapsulation actually means. Encapsulation is the practice of hiding sensitive information. It can be defined as an entity that binds data members and methods into a single unit. This further helps us achieve data abstraction or data hiding.

## Abstraction

Abstraction means hiding the sensitive information and showing only the essential information to the user or the outside world. With abstraction, only important information is visible, while all the background details are hidden.

We can use the private access modifier in a class to hide important information. Therefore, we can decide which data members will be visible to the outside world and which ones will not.

## Inheritance

Inheritance is a concept in object-oriented programming (OOP) that allows us to share properties and characteristics of one class in another. It eliminates the need to create another class with the same set of variables and methods. The class that inherits from another class is known as the child class or derived class, while the class from which the properties are being inherited is known as the parent class or base class. Inheritance allows us to reuse the existing class instead of creating a new one.

Here's an example of inheritance in C++:

```cpp
#include <iostream>

using namespace std;

class Vehicle {
public:
    Vehicle() {
        cout << "This is a vehicle." << endl;
    }
};

class Car : public Vehicle {
public:
    Car() {
        cout << "This is a car." << endl;
    }
};

int main() {
    Car obj;
    return 0;
}
```

In the above code, the `Car` class inherits from the `Vehicle` class using the `public` visibility mode. The `public` visibility mode means that all the public members of the base class become public members of the child class. In this case, the output will be:

```
This is a vehicle.
This is a car.
```

Please note that the private members of the base class are never inherited.

Note: Use a colon (`:`) to inherit a class.

When discussing abstraction and encapsulation, we mentioned data hiding. Inheritance plays a significant role in achieving this.

In the code example above, after the colon, we simply write the name of the base class from which we want to inherit. Inheritance in C++ has a concept called visibility mode. This means we can inherit classes publicly or privately. By default, the visibility mode is private.

Consider the following code:

```cpp
class Car : public Vehicle
{
public:
    Car()
    {
        cout << "This is a car" << endl;
    }
};
```

In the above code, notice the use of the `public` keyword after the colon. This is the visibility mode and it determines how we inherit our classes. If we inherit in the public mode, all the public members of the base class become public members of the child class. In the case of private mode, all the public members of the base class become private in the child class. In this case, objects of the derived class cannot access the members of the base class. It's important to remember that private members of the base class are never inherited.

Inheritance is further divided into five types:

a) Single Inheritance: There is only one derived class derived from the base class.
b) Multiple Inheritance: Deriving a single class from multiple base classes is called multiple inheritance.
c) Hierarchical Inheritance: Multiple classes are derived from a single base class.
d) Multilevel Inheritance: One class derived from another class results in multilevel inheritance.
e) Hybrid Inheritance: It refers to a combination of multiple types of inheritance under one roof.

## Polymorphism

Polymorphism is an essential concept in OOP. It allows a function or method to have different forms depending on the type of object it is invoked with. Similar to how a cricket coach can be a father to someone, a husband to someone else, and a brother to another person, polymorphism allows methods to have different forms based on the calls they receive.

In C++, there are two types of polymorphism:

1. Run-time Polymorphism: In run-time polymorphism, the methods to be executed are decided at runtime. If the number of arguments passed and the method name is the same, the appropriate method is determined at runtime.

2. Compile-time Polymorphism: In compile-time polymorphism, the methods are invoked depending on the number of parameters. The function that matches the call is the one that runs during compile time.


### Run-time Polymorphism (Virtual Functions)

```cpp
#include <iostream>

class Shape {
public:
    virtual void draw() {
        std::cout << "Drawing a shape." << std::endl;
    }
};

class Circle : public Shape {
public:
    void draw() override {
        std::cout << "Drawing a circle." << std::endl;
    }
};

class Rectangle : public Shape {
public:
    void draw() override {
        std::cout << "Drawing a rectangle." << std::endl;
    }
};

int main() {
    Shape* shape1 = new Circle();
    Shape* shape2 = new Rectangle();

    shape1->draw(); // Calls draw() method of Circle class
    shape2->draw(); // Calls draw() method of Rectangle class

    delete shape1;
    delete shape2;

    return 0;
}
```

In the above code, we define a base class `Shape` and two derived classes `Circle` and `Rectangle`. The `Shape` class has a virtual method `draw()`. In the `main()` function, we create pointers of type `Shape` and assign objects of derived classes to them. When we call the `draw()` method using these pointers, the appropriate method based on the actual object type is called. This is run-time polymorphism as the decision on which method to invoke is made at runtime based on the object's type.

### Compile-time Polymorphism (Function Overloading)

```cpp
#include <iostream>

int add(int a, int b) {
    return a + b;
}

double add(double a, double b) {
    return a + b;
}

int main() {
    int result1 = add(3, 4);           // Calls the first add() function
    double result2 = add(2.5, 3.7);    // Calls the second add() function

    std::cout << "Result 1: " << result1 << std::endl;
    std::cout << "Result 2: " << result2 << std::endl;

    return 0;
}
```

In the above code, we have two functions named `add()` with different parameter types. One takes two integers as arguments, and the other takes two doubles. When we call the `add()` function with different argument types, the appropriate function is selected at compile time based on the argument types. This is compile-time polymorphism as the decision on which function to call is made during the compilation process.

> ## **Lets explore some more important concepts of OOPS:** 

1. `this`: It is a pointer that refers to the current instance of a class. It is used to access the members of the class within its member functions.

```cpp
class Person {
public:
    void printName() {
        cout << "Name: " << this->name << endl;
    }
private:
    string name;
};
```

2. `const`: It is used to declare constants or to specify that a member function does not modify the object's state. `const` objects cannot modify their member variables.

```cpp
class Circle {
public:
    Circle(double radius) : radius(radius) {}
    double getArea() const {
        return 3.14159 * radius * radius;
    }
private:
    const double radius;
};
```

3. `static`: It is used to declare class-level variables or methods that are shared among all instances of the class. Static members can be accessed without creating an object of the class.

```cpp
class Counter {
public:
    static int count;  // static member variable
    static void increment() {
        count++;
    }
};

int Counter::count = 0;  // static member variable definition

int main() {
    Counter::increment();  // accessing static member function
    cout << "Count: " << Counter::count << endl;  // accessing static member variable
    return 0;
}
```

4. `friend`: It is used to declare a function or class as a friend of another class. A friend function or class can access the private and protected members of the class.

```cpp
class Circle {
private:
    double radius;
public:
    Circle(double r) : radius(r) {}
    friend class Cylinder;  // Cylinder class is a friend of Circle
};

class Cylinder {
public:
    double getVolume(const Circle& circle) {
        double height = 10.0;
        return 3.14159 * circle.radius * circle.radius * height;
    }
};

int main() {
    Circle circle(5.0);
    Cylinder cylinder;
    cout << "Volume: " << cylinder.getVolume(circle) << endl;
    return 0;
}
```

5. `virtual`: It is used to declare a virtual function in the base class. Virtual functions can be overridden in derived classes, and the appropriate function is called based on the actual object type during run-time polymorphism.

```cpp
class Shape {
public:
    virtual void draw() {
        cout << "Drawing a shape." << endl;
    }
};

class Circle : public Shape {
public:
    void draw() override {
        cout << "Drawing a circle." << endl;
    }
};

int main() {
    Shape* shape = new Circle();
    shape->draw();  // Calls the overridden function in the Circle class
    delete shape;
    return 0;
}
```

6. `override`: It is used to explicitly indicate that a member function is intended to override a virtual function from the base class. It helps in preventing accidental errors and improves code readability.

```cpp
class Shape {
public:
    virtual void draw() {
        cout << "Drawing a shape." << endl;
    }
};

class Circle : public Shape {
public:
    void draw() override {  // Explicitly marked as an override
        cout << "Drawing a circle." << endl;
    }
};

int main() {
    Shape* shape = new Circle();
    shape->draw();  // Calls the overridden function in the Circle class
    delete shape;
    return 0;
}
```

7. `constructor` and `destructor`: Constructors are special member functions used for initializing objects of a class.

 They have the same name as the class and do not have a return type. Destructors are used to clean up the resources allocated by an object when it goes out of scope or is explicitly destroyed.

```cpp
class Person {
public:
    Person(const string& name) : name(name) {
        cout << "Person constructor called." << endl;
    }
    ~Person() {
        cout << "Person destructor called." << endl;
    }
private:
    string name;
};

int main() {
    Person person("Pratik");  // Constructor called
    // ...
    // Other code
    // ...
    return 0;  // Destructor called
}
```

8. `new` and `delete`: These are operators used for dynamic memory allocation and deallocation, respectively. `new` is used to allocate memory for an object on the heap, and `delete` is used to deallocate the memory and destroy the object.

```cpp
class Rectangle {
public:
    Rectangle(double w, double h) : width(w), height(h) {}
    double calculateArea() {
        return width * height;
    }
};

int main() {
    Rectangle* rect = new Rectangle(5.0, 10.0);  // Dynamic memory allocation
    double area = rect->calculateArea();
    cout << "Area: " << area << endl;
    delete rect;  // Memory deallocation
    return 0;
}
```

### Cohesion and Coupling in OOPs 

Cohesion and coupling are important concepts in software engineering that describe the relationships and interactions between different components or modules of a program. In C++, cohesion and coupling play a crucial role in designing and maintaining software systems. 

1. Cohesion: Cohesion refers to the degree of relatedness or unity among the members of a module or class. It measures how closely the responsibilities and functionalities of a module or class are related to each other. High cohesion is desirable as it indicates that the members of a module work together towards a common purpose, leading to more maintainable and understandable code.

Types of cohesion in C++:
- Functional cohesion: Members of a module or class work together to perform a single function or task.
- Sequential cohesion: Members are organized in a sequential order, where the output of one member becomes the input for the next member.
- Communicational cohesion: Members operate on the same data or communicate closely with each other.
- Temporal cohesion: Members are called in a specific order or within a specific time frame.
- Procedural cohesion: Members are grouped based on a common procedural logic or algorithm.

Example of high cohesion:
```cpp
class FileManager {
public:
    void openFile(const string& filename) {
        // Code to open a file
    }
    
    void readFile() {
        // Code to read data from the file
    }
    
    void closeFile() {
        // Code to close the file
    }
};
```

In the above example, all the methods in the `FileManager` class are closely related to file handling operations. They work together towards the common purpose of managing files, indicating high cohesion.

2. Coupling: Coupling refers to the degree of interdependence between different modules or classes in a system. It measures how closely one module relies on or knows about the internals of another module. Low coupling is desirable as it promotes modularity, reusability, and maintainability of code.

Types of coupling in C++:
- Tight coupling: Modules are highly dependent on each other, making changes in one module impact others significantly.
- Loose coupling: Modules have minimal or no knowledge of the internal workings of other modules, reducing the impact of changes.
- Content coupling: Modules share internal data directly, leading to high dependency.
- External coupling: Modules depend on externally defined data or interfaces.
- Control coupling: Modules control the behavior of other modules through parameters or flags.

Example of low coupling:
```cpp
class Database {
public:
    void insertData(const Data& data) {
        // Code to insert data into the database
    }
};

class Logger {
public:
    void logMessage(const string& message) {
        // Code to log a message
    }
};

class DataManager {
public:
    DataManager(Database& db, Logger& logger)
        : database(db), logger(logger) {}
    
    void processData(const Data& data) {
        // Process the data
        database.insertData(data);
        logger.logMessage("Data processed successfully");
    }
    
private:
    Database& database;
    Logger& logger;
};
```

In the above example, the `DataManager` class depends on the `Database` and `Logger` classes through their interfaces (references). It has no knowledge of the internal implementation details of the other classes, promoting loose coupling.

By considering both cohesion and coupling, you can design software systems that are more modular, maintainable, and extensible, leading to better code quality and easier development and maintenance.

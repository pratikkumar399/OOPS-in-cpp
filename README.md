# OOPS-in-c-
#Link of the blog - https://kontentkreator.tech/object-oriented-programming-in-cpp/
Hello , everyone welcome to the blog . Today I am going to discuss Object Oriented Programming in C++ . This article will briefly discuss everything you need to know about OOP's in c++ .

Some terms that are very important in C++ - 
1. Class 
2. Objects 
3. Encapsulation
4. Abstraction
5. Inheritence 
6. Polymorphism 


We will visit every topic one by one and understand what they actually mean . Also, I will be sharing with you snippets of code to help you understand the topics easily . So , lets get started .

Introduction to OOPS - 

After hearing this word Object-oriented , you might have got an idea , what it is all about . Yes, you guessed it right . It's all about objects . Objects are used to implement different scenarios from the real world . 
If you have used C , then you might have noticed that it uses functions and procedures to implement different things(that is why it is also called procedural language) . But in C++ we can use OOPS to create objects that can have both the data members and functions in a single entity . 
As you will get to know the concepts of OOPS , it will become easier for you to understand , the idea behind it's usage.

I will discuss the advantages of OOPS in the later part of this article , so that you can understand , what it means to use OOPS language . 

1. CLASS - This is where the concepts of OOPS begin . A class is a block where you can write both data members and functions inside it . Let us try to understand this with an example - 
Take car as a CLASS . Now the car has certain properties(or attributes) , like color and  weight . And the car can move by its own method like drive and brake . So , basically , you can say that the color and weight properties are the data members of the class , while the drive and brake options are functions of the class CAR . 

So , a class is a basic buliding block which contains both data members and functions . With the use of these functions we can get access to the data members and manipulate them according to our needs . The concept of classes will be more clear when , we will get to know more about objects, and different properties of class .

2.Objects - In the previous example we shaw that we have a car as a class and it has different properties like color , weight . Also it has its method like drive and brake . Now, when you  go to buy a car , you see that different car has different properties . So , different cars such as Mercedes , Audi , Nano , etc are objects of class CAR , and they have their own characteristics and behaviour . So , an object is an instance of a class . 
When we define a class , no memory is allocated , but when we create an object of the class , a block of memory gets allocated to it . So, a class gets memory block when it gets instantiated. 
Every object of a class has their own copy of the data members and we can create as many obejects we want .
To access the methods of the class use the dot operator (.) , along with the object .

A code snippet to show how a class and an object is programmed in CPP - 

#include<bits/stdc++.h>
using namespace std ;

class Car{
   int color , weight ;   // data members of the class 
   

//    The below methods are called the functions of the class Car
   void drive(){
       cout<<"Drive the car"<<endl;
   }
   void brake(){
       cout<<"Stop the car"<<endl;
   }
};

int main(){
  Car obj1 ; // creating the object of the class 
  obj1.drive() ; // calling the functions of the class 
 obj1.brake() ;  // calling the functions of the class to call the brake function
    return 0;
}

So, we can say that a class is a blueprint which represents a group of objects , which share common properties and methods .

3.Encapsulation -  To understand the concept of encapsulation , first let us understand access specifiers . 

Access modifiers helps us to decide, how the member functions can be accessed outside the class . 
There are three access modifiers used in C++ - 
   a)  Private 
   b) Public 
   c) Protected 

-> When something is declared public : data members can be accessible outside of the class  .
class Public
{
    // public access modifier
    public:   
    int x;            
    void show();  
}
-> When something is declared private : data members cannot be accessed outside 
 the class .
class Private
{
    // private access modifier
    private:   
    int x;            
    void show();   
}
 
-> When something is declared protected : data members can only be accessed inside the inherited(discussed later)  classes .  
class Protected
{
    // protected access modifier
    protected: 
    int x;            
    void display();  
}


In c++ the data members of a class are public by default. 

Now , let us discuss what encapsulation actually means . 
Suppose, you are working on a software, and you don't want to make the backend parts of the software visible to users.. 
Encapsulation hides the sensitive information. It can be defined as an entity which
binds data members and entity in a single information. This further helps us to achieve data abstraction or data hiding .

4. Abstraction - It means hiding the sensitive information and showing only the essential information to the user , or outside world .So , with abstraction only important information is visible and all the background details are hidden  . 

We can use the private access modifier in a class to hide the important information.
Therefore, we can decide which data members will be visible to outside world and which is not .

5. Inheritence  -  Suppose that we want to share some properties and characteristics of one class in another . In that case, we do not need to make another class with same set of variables and methods again . We have a concept called inheritence in OOPS , which allows us to do this. It simply means inheriting the methods and attributes from the another class. You might have heard of concept of inheriting properties in families . Similarly here , the class which inherits from another class is known as child class or derived class. And the class from which the properties are being inherited , are known as parent or base class . Thus, one can say that inheritence allows us reuse the existing class instead of creating a new one . 

Example of inheritence  : 

#include <bits/stdc++.h>

using namespace std;
class vehicle
{
public:
    vehicle()
    {
        cout << "This is a vehicle " << endl;
    }
};
class car : vehicle
{
public:
    car()
    {
        cout << "This is a car " << endl;
    }
};

int main()
{
    car obj;
    return 0;
}

Note  : Use : (colon)  to inherit a class .

Now , when we read about abstraction and encapsulation, you might have noticed that we discussed about data hiding . Inheritence has a very special role to play in this .

In the above code notice that after colon we have simply wrote the name of base class, the class from which we want to inherit . There is a thing called visibility mode i inheritence. This means we can inherit the classes publicly or privately. 
The default visibility mode is private . 

Take a look at the code below : 

class car : public  vehicle
{
public:
    car()
    {
        cout << "This is a car " << endl;
    }
};

Notice , how the public word has been used after the colon . This is called the visibility mode and it decides how we want to inherit our classes .
If we inherit it in public mode , then all the public members of the base class become
public class of the child class. While in the case of private mode , all the public members of the base class becomes private in the child class . In that case , the objects of the derived class cannot access the members of the base class  .
Always remember, that the private member of the base class are never inherited . 


Inheritence has been further divided into 5 types  :
 
a). Single inheritence 
b). Multiple inheritence 
c). Hierarchical inheritence 
d). Multilevel inheitence 
e). Hybrid inheritence 

a). Single Inheritence - There is only one derived class, derived from the base class.
b). Multiple inheritence - Deriving a single class from a single base class is called multiple inheritence.
c).Heirarchical inheritance-  Multiple classes are derived from a single base class .
d).Multilevel inheritence - One class derived from another class gives result to multilevel inheritence . 
e).Hybrid Inheritance - It can be said as multiple types of inheritance under one roof .

6.Polymorphism - Polymorphism is also a very important topic in OOPS. Due to this property a function or method can have different forms depending upon the type they are invoked . You might have seen that a cricket coach can be father to someone , husband for someone and brother for another. Similarly polymorphism allows methods to have different forms depending upon the calls they are given .

In C++ there are two types of polymorphism - 

1. Run time polymorphism 
2. Compile time polymorphism 

In compile time polymorphism , the methods are invoked depending upon the number of parameters . The function which matches the call is the one which runs during compile time . 

What if the number of arguements passed and the method name is same . Then there comes the importance of run- time polymorphism  . The methods to be run are decided at runtime , and hence the name .











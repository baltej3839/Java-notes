### declaring an array of limited size

```java
package com.engineeringdigest.javaInOneVideo;

public class Demo {
    public static void main(String[] args){
        int[] arr=new int[10];
        System.out.println(arr[0]);
    }
}
```
arr as ref is stored ins stack and the array itself is stored in the heap , stack points to the location of the array in the heap where it is stored

### methods of array
1. arr.length; --> find length of array


### Functions and methods
arr.length is not a method
length is a property of the array 

String a="Baltej";
String uppercase=a.toUpperCase();
toUpperCase() is a method as it uses ()


### what is property ?


### declaring and assigning an array of directly

```java
package com.engineeringdigest.javaInOneVideo;

public class Demo {
    public static void main(String[] args){
        int[] arr1={1,2,3,4};
        System.out.println(arr1[0]);
    }
}
```

### what is a hashcode ?
appears when appears while printing an array directly


### loop over an array just getting the value of each
i is the value of the elements in the array and not the index of the array
int after the for is needed to specify the elements in the array  
```java
package com.engineeringdigest.javaInOneVideo;

public class Demo {
    public static void main(String[] args){
        int[] arr1={1,12,2,3,4};
        for(int i:arr1){
            System.out.println(i);
        }
    }
}
```

### assign negative infinity
```java
package com.engineeringdigest.javaInOneVideo;

public class Demo {
    public static void main(String[] args){
        int i=Integer.MIN_VALUE;
    }
}
```

### what are methods in java ?


### how to run a program that has this strcture ?
```bash
baltejsingh@Dell:~/Java_project/JavaInOneVideo$ tree
.
├── JavaInOneVideo.iml
├── out
│   ├── production
│   │   └── JavaInOneVideo
│   │       └── test
│   │           ├── Car.class
│   │           └── test.class
│   └── test
│       ├── Car.class
│       └── test.class
└── src
    └── test
        ├── Car.java
        └── test.java

7 directories, 7 files
baltejsingh@Dell:~/Java_project/JavaInOneVideo$ javac -d out src/test/*.java
baltejsingh@Dell:~/Java_project/JavaInOneVideo$ java -cp out test.test
41
baltejsingh@Dell:~/Java_project/JavaInOneVideo$ 
```

### Four pillars of OOPS
1. Encapsulation --> bundling of data and methods into a single unit and this unit is called a class , along with this data can also hidden
If the things are to be hidden then **private** is used in front of the variable

2. Inheritence -: Inheritance allows to inherit some properties of the Parent class to the child class
3. Polymorphism
4. Abstraction --> hiding implementation details


### Understanding Encapsulation
a class can have 
1. properties aka fields aka instance variables
2. behaviour

### Example of a instance variable
name is a instance variable
```java
package test;

public class Student  {
    String name;
    public static void main(String[] args){
    }
}
```


### Example of a local variable
name is a local variable and this can the variable inside any method and not the class directly

```java
package test;

public class Student  {

    public static void main(String[] args){
        String name;
    }
}
```




### Understanding inheritance
Inheritance allows to inherit some properties of the Parent class to the child class
Below is an example
extends is used in the child class to inherit the props of parent class
  
```java
package test;

public class Animal {
    String name;
    String age;

}   
```

```java
package test;

// child class and taking properties from parent class Animal
public class Cat extends Animal{
    String breed;
}
```

```java
package test;

public class test {
     public static void main(String[] args){
         Cat cat= new Cat();
         cat.name="bob";
     }
}

```


### Understanding polymorphism

```java
package test;

public class Animal {
    public void makeSound(){
        System.out.println("Same sound");
    }
}


package test;

// child class and taking properties from parent class Animal
public class Cat extends Animal{
    public void makeSound(){
        System.out.println("Meow ");
    }
}


package test;

public class Dog extends Animal{
    public void makeSound(){
        System.out.println("Woof ");
    }
}


package test;

public class test {
     public static void main(String[] args){
         Animal dog=new Dog();
         dog.makeSound();

     }
}

```


### What is access modifier in java ?


### What is method overloading?
When 2 methods have same name , return type is same, but params are different



### What is signature ?
signature does not include return type, access modifier
 
### how to pass multiple unknown params into a method ?

```java
package test;

public class test {
     public static void main(String[] args){
            System.out.println(sum(1,22,4,4));
     }

     public static int sum(int... a){
            int sum=0;
            for (int i:a){
                sum+=i;
            }
            return sum;
     }

}
```

### Understanding Constructor
is a special method to initialize the object
```java
         Cat cat= new Cat();
```

way to overload a default constructor without param

```java
package test;

public class Student  {
    private String name;
    private int rollNumber;
    int age;

    public Student(){
        this.age=10;
    }
}

```

way to write a default constructor with params

```java
package test;

public class Student  {
     String name;
     int rollNumber;
    int age;

    public Student(String name,int rollNumber,int age){
        this.age=age;
        this.name=name;
        this.rollNumber=rollNumber;

    }
}

```

### What is method overriding ?
if a parent class has the same method in the child class as well , then the child class will get priority when called

```java
package test;

public class Animal {

    public void sayHello(){
        System.out.print("");
    }
}


package test;

public class Dog extends Anima {
    public void sayHello(){
        System.out.print("woof");
    }
}


package test;

public class test {
     public static void main(String[] args){
         Dog dog=new Dog();
         dog.sayHello();

     }
}
```

### Inheritence can be multi level as well


### Understanding use of super();
super() denotests the parent class
it is the first statement in the constructor and not the 2nd or later on, because we want the parent constructor to instantiate first 

super refers to the immediate parent

super can be used to invoke (super class) parent class constructor, methods, fields 
```java
package test;

public class Parent extends Grandparent{

    public Parent (int a){
        super();
        System.out.println("Parent constructor is called");
    }

}
```

```java
package test;

public class Grandparent {

    public Grandparent(){
        System.out.println("Grandparent constructor called");
    }



    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    private String name;
    private int age;
}


package test;

public class Parent extends Grandparent{

    public Parent (){
        super();
        System.out.println("Parent constructor is called");
    }

    public void parentMethod(){
        System.out.println("Parent method called");
    }



}


package test;

public class Child extends Parent{

    public Child(){
        super();
        System.out.println("Child constructor called");
    }

    public void childMethod(){
        super.parentMethod();
        System.out.println("Child Method called ");
    }


}
package test;

public class test {
     public static void main(String[] args){
            Child child= new Child();
            child.childMethod();

     }
}

```

in the code **new** means dynamic memory allocation

### Constructor chaining

```java
package test;

public class Grandparent {

    private String name;
    private int age;
    public Grandparent(String name,int age){
        this.age=age;
        this.name=name;
        System.out.println("Grandparent constructor called");
    }



    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

}


package test;

public class Parent extends Grandparent{

    public Parent ( String name,int age){
        super(name,age);
        System.out.println("Parent constructor is called");
    }

    public void parentMethod(){
        System.out.println("Parent method called");
    }



}

package test;

public class Child extends Parent{

    public Child(String name, int age){
        super(name,  age);
        System.out.println("Child constructor called");
    }

    public void childMethod(){
        super.parentMethod();
        System.out.println("Child Method called ");
    }


}



package test;

public class test {
     public static void main(String[] args){
            Child child= new Child("Me", 21);
            System.out.println(child.getAge());
         System.out.println(child.getName());


     }
}

```

## Prompt
baltejsingh@Dell:~/Java_project/JavaInOneVideo$ tree
.
├── JavaInOneVideo.iml
├── out
│   ├── production
│   │   └── JavaInOneVideo
│   │       └── test
│   │           ├── Animal.class
│   │           ├── Cat.class
│   │           ├── Dog.class
│   │           └── test.class
│   └── test
│       ├── Anima.class
│       ├── Animal.class
│       ├── BankAccount.class
│       ├── Car.class
│       ├── Cat.class
│       ├── Child.class
│       ├── Dog.class
│       ├── Grandparent.class
│       ├── Parent.class
│       ├── Student.class
│       └── test.class
└── src
    ├── test
    │   ├── Child.java
    │   ├── Grandparent.java
    │   ├── Parent.java
    │   └── test.java
    └── test2
        ├── Animal.java
        ├── Cat.java
        └── Dog.java

8 directories, 23 files





### Anotation
@ is used for giving it to method or behaviour
below is eg and will give error if no override is there
 

```java
package test2;


public class Animal {

    public void sayHello(){
        System.out.print("");
    }
}


package test2;

public class Cat extends  Animal{
    public void sayHello(){
        System.out.print("Meon");
    }
}


package test2;

public class Dog extends Animal {

    @Override
    public void sayHello(){
        System.out.print("woof");
    }
}

package test;

import test2.Dog;

public class test {
     public static void main(String[] args){
         Dog dog= new Dog();
         dog.sayHello();

     }
}

```

Java does not support multiple class interitance for the same class as it creats ambiguity as 2 different classes can call a behaviour and that behavoiurs can be inheritied and then it cannot be decided to which behivour it is being called to

Java supports interfaced approach



### What is Java interface and how it solves 


### Polymorphism
allows methods to do different things based on the object it is acting upon, even though the method name and its signature might be the same.


### Compile time polymorphism

### example of overloaded methods
```java

```

check why this throws error ?

    public int add(float a , float b){
        return a+b;
    }



### Prompt
why is the double one throwing error, package MultipleInheritence;

public class Calculator {

    public int add(int a , int b){
        return a+b;
    }

    public int add(int a , int b, int c){
        return a+b+c;
    }


    public int add(double a , double b){
        return a + b;
    }

}

Ans
Good catch — this is a **classic Java overloading confusion** 👀

---

# ❌ Problem in your code

```java
public int add(double a , double b){
    return a + b;
}
```

👉 Error happens because:

* `a + b` → result is **double**
* But your method return type is **int**

---

# 🔥 Why Java throws error

Java **does NOT automatically convert `double → int`** (because data loss can happen)

So this is invalid:

```java
return a + b; // ❌ double → int (not allowed)
```

---

# ✅ Fix 1 (Best solution)

Change return type to `double`:

```java
public double add(double a , double b){
    return a + b;
}
```

---

# ✅ Fix 2 (Not recommended, but works)

Force conversion (type casting):

```java
public int add(double a , double b){
    return (int)(a + b);
}
```

👉 But this will **cut decimal values**

Example:

```java
add(2.5, 3.5) → 6.0 → cast → 6
```

---

# 🧠 Important concept (INTERVIEW GOLD)

This is called **Method Overloading**

Your methods:

```java
add(int, int)
add(int, int, int)
add(double, double)
```

✔️ Valid because:

* Same name
* Different parameters

---

# ⚠️ One more subtle issue

If you call:

```java
add(5, 6)
```

👉 Java chooses:

```java
add(int, int)
```

But if you call:

```java
add(5.0, 6.0)
```

👉 Java chooses:

```java
add(double, double)
```

---

# 🚀 Final Correct Code

```java
package MultipleInheritence;

public class Calculator {

    public int add(int a , int b){
        return a + b;
    }

    public int add(int a , int b, int c){
        return a + b + c;
    }

    public double add(double a , double b){
        return a + b;
    }
}
```

---

If you want next level understanding 🧠
I can show you:

* How Java decides which overloaded method to call (method resolution)
* Tricky interview cases (like `add(5, 5.0)` 😈)

Just say **“overloading deep dive”**


 ### example of compile time polymorphism (method overloading)

via the use of method overloading, we are archiving compile time polymorphims
as it is being decided on the compile time that which method will be called
poly means many 
morph means forms    

 ```java

package MultipleInheritence;

public class Calculator {

    public int add(int a , int b){
        return a+b;
    }

    public int add(int a , int b, int c){
        return a+b+c;
    }


    public double add(double a , double b){
        return a + b;
    }

}



package MultipleInheritence;

public class test {

    public static void main(String[] args){
        Calculator cal= new Calculator();
        System.out.println(cal.add(5,10));
        System.out.println(cal.add(5,10,15));
        System.out.println(cal.add(5.5,10.6));
    }


}

 ```


 ### Runtime polymorphism

this is achived by **method overriding** 
so Runtime polymorphism is **method overriding** 
aka **Dymaic method dispatch**

below is aslo an example of **upcasting**
when a lower hierarchy object is being put in the reference of the upper  hierarchy object

also check by **downcasting**

whatever object is given as reference, on only its methods can be accessed by it and not its children classes
eg.
   Anima cat= new Cat();
        cat.sayHello();

        here only Anima methods can be accessed and not the once in the Cat as the reference is of Anima


```java
package MultipleInheritence;

public class Anima {


    public void sayHello(){
        System.out.println("...");
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public void eat(){
        System.out.println("this animal eats food");
    }

    private String name;
    private int age;


}


package MultipleInheritence;

public class Cat extends Anima{

    @Override
    public void sayHello(){
        System.out.println("emo");
    }
}




package MultipleInheritence;

public class Dog extends Anima{


    @Override
    public void sayHello(){
        System.out.println("Wooff");
    }
}


package MultipleInheritence;

public class test {

    public static void main(String[] args){
        Anima myAnima= new Anima();
        myAnima.sayHello();

        Anima dog= new Dog();
        dog.sayHello();

        Anima cat= new Cat();
        cat.sayHello();
    }


}



```

### Concreat methods
which have a definition 

### Abstract methods
methods which dont have a body
  
### Understanding abstraction

Abstract class' object cannot be created as the definition of the methods in the abstract class has empty body but the reference of the abstract class can be given


```java
package abstraction;

public abstract class Animal {

    public abstract void sayHello();

    public void sleep(){
        System.out.println("zzz...");
    }
}

package abstraction;

public class Dog extends Animal{
    @Override
    public void sayHello() {
        System.out.println("woof");
    }
}


package abstraction;

public class Test {
    public static void main(String[] args){
        Dog dog= new Dog();
        dog.sayHello();
    }
}



```


If a property is not having a public or private access modifier than it can be accessed within the package but not in the other packages


if a method is package private then and its abstract class, then it cant be override in another class which is extending that
 

if a method is protected then it can only be used if the class in which it has to be used is extending the parent class

### prompt
if a class has protected method and that class is extending in Dog, then in test, the dog is extended, then can that protected method be used in test
Answer-:Good question — this is where many people get confused in Java access control 👀

Let’s break it clearly.

---

# 🧠 Scenario you described

* Class **A** → has `protected` method
* Class **Dog extends A**
* Class **test extends Dog**

👉 Now you are asking:
**Can `test` use that protected method?**

---

# ✅ Short Answer

👉 **YES — but only through inheritance (inside the class), not through object reference from outside package**

---

# 🔥 Rule of `protected` (VERY IMPORTANT)

`protected` is accessible:

1. ✅ Inside same package (any class)
2. ✅ In subclasses (even in different package)
3. ❌ NOT via object reference outside package (this is the tricky part)

---

# 🧩 Case 1: Using inside `test` (extends Dog)

```java
class test extends Dog {
    public static void main(String[] args) {
        test t = new test();
        t.protectedMethod(); // ✅ WORKS
    }
}
```

👉 Works because:

* `test` is indirectly a subclass of A
* Access happens via inheritance

---

# 🧩 Case 2: Using via object (common mistake)

```java
class test {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.protectedMethod(); // ❌ ERROR (if different package)
    }
}
```

👉 Even though `Dog` has access, `test` **does NOT get access via object**

---

# 🔥 Golden Rule (remember this for interviews)

> Protected = “accessible in subclass, but NOT freely accessible via object outside package”

---

# 🧠 Visual understanding

```
A (protected method)
  ↑
Dog
  ↑
test
```

✔ test can use it because of inheritance chain
❌ But cannot use it like normal public method from outside

---

# 🚀 Final summary

| Scenario                   | Works? |
| -------------------------- | ------ |
| Same package               | ✅      |
| Subclass (any package)     | ✅      |
| Via object outside package | ❌      |

---

# 💡 Real interview trap

They will ask:

```java
Dog d = new Dog();
d.protectedMethod();
```

👉 You might think YES (because Dog extends A)

But answer is ❌ **NO (if different package)**

---

If you want next level 🔥
I can give you:

* 5 tricky MCQs on access modifiers (asked in interviews)
* Deep comparison: `private vs default vs protected vs public`

Just say **“access modifier test”** 😎


Abstract classes should not have public constructors as the constructors of the abstract classes can only be called in the constructors of there sub classes. So you protected instead of public

### Access modifiers
these are keywords which decide visiblity of class, methods, fields  like public , private , protected and default 


### Prompt
baltejsingh@Dell:~/Java_project/JavaInOneVideo$ javac -d out src/accessModifier/*.java src/test/*.java
src/test/test.java:6: error: <identifier> expected
    Student.sayBye();
                  ^
1 error, package accessModifier;

public class Student {
    public static String sayBye(){
        return "Bye..";
    }
}, package test;

import accessModifier.Student;

public class test {
    Student.sayBye();

}, check what is wrong, i declared the method of sayBye to static ,but still not able to call it just using the class itself

Ans

Good, this is a **syntax mistake + Java rule confusion**, not a static issue 👍

---

# ❌ Problem in your code

```java
public class test {
    Student.sayBye();
}
```

👉 This line is **outside any method**

---

# 🔥 Why error comes

Java expects only:

* variables
* methods
* constructors
* blocks

inside a class

But you wrote:

```java
Student.sayBye();
```

👉 That is a **statement**, and statements are only allowed **inside methods**

So compiler says:

```
<identifier> expected
```

---

# ✅ Correct way

You must call it inside `main()`:

```java
package test;

import accessModifier.Student;

public class test {
    public static void main(String[] args) {
        System.out.println(Student.sayBye());
    }
}
```

---

# 💡 Important concept

### ✔️ Static method means:

You can call it using class name:

```java
Student.sayBye(); ✅
```

BUT ❗ still must be inside a method

---

# 🧠 Mental model (very important)

Think:

```
Class → blueprint
Method → execution block
Statements → only run inside methods
```

---

# ❌ Wrong vs ✅ Right

### ❌ Wrong

```java
public class test {
    Student.sayBye(); // ❌ illegal
}
```

---

### ✅ Right

```java
public class test {
    public static void main(String[] args) {
        Student.sayBye(); // ✅ valid
    }
}
```

---

# ✅ Compile & run

```bash
javac -d out src/accessModifier/*.java src/test/*.java
java -cp out test.test
```

---

# 🔥 Bonus tip (naming)

```java
public class test
```

👉 Change to:

```java
public class Test
```

(Java standard — helps in interviews + readability)

---

If you want next level 🚀
I can show you:

* Difference between static vs non-static in memory (VERY important)
* Why `main` is static
* Real-world use of static methods

Just say **“static deep dive”** 😎


#### Making a private constructor

### Calling a method directly from the class without making an object of that
done by using static with that method which needs to be called like that

```java
package accessModifier;

public class Student {
    public static void sayBye(){
        System.out.println("Bye");
    }
}


package test;

import accessModifier.Student;

public class test {
     public static void main(String[] args) {
        Student.sayBye();
    }

}



```



### I want that everyone should call the static methods without creating an object of it
then use private constructor for that, as it wont allow to make an object of that class

the below would give me error as it wont allow me to make an object as the constructor is private

```java
package accessModifier;

public class Student {

    private Student(){
        
    }

    public static void sayBye(){
        System.out.println("Bye");
    }
}


package test;

import accessModifier.Student;

public class test {
     public static void main(String[] args) {
        Student student= new Student();

    }

}

```

### Singleton pattern of object creation 
if I want to make sure that an object of a class is just made once and not more than that

```java
package test;

public class School {

    private static School instance;

    private  School(){

    }

    public static School getInstance(){
        if (instance==null){
            instance = new School();

        }
        return instance;
    }
}


package test;

import accessModifier.Student;

public class test {
      public static void main(String[] args) {
          School.getInstance();
     }

}

```

+--------------------------------------+---------+-------------------------+-----------+--------+
| Context \ Access Modifier            | private | default (no modifier)   | protected | public |
+--------------------------------------+---------+-------------------------+-----------+--------+
| Same Class                           | Yes     | Yes                     | Yes       | Yes    |
| Same Package                         | No      | Yes                     | Yes       | Yes    |
| Subclass (same package)              | No      | Yes                     | Yes       | Yes    |
| Subclass (different package)         | No      | No                      | Yes       | Yes    |
| Different Package (non-subclass)     | No      | No                      | No        | Yes    |
+--------------------------------------+---------+-------------------------+-----------+--------+


### Understanding Static

static attaches a field , method to the class itself, so whenever class is called , then that field or method remainds in memory and gets updated according to the set condition
if you want to attach a field , property to a class then use static like below

```java

package accessModifier;

public class Student {
    public static int count=0;


    public Student(){
        count++;
    }
}

package test;


import accessModifier.Student;

public class test {
      public static void main(String[] args) {
          Student student1= new Student();
          Student student2= new Student();
          Student student3= new Student();
          Student student4= new Student();
          Student student5= new Student();
          System.out.println(Student.count);
      }

}
```

### Use of final keyword

once it is assigned then it can be used to 
here if the final keyword is used then its value cannot be changed using a setter or any other way

final keyword can be used for methods and classes as well
methods cannot be overriden if final used
classes cannot be extended if final is used with it


final is not used for constructors as the constructors cannot be overriden anyways

```java
package test;

public class Car extends Vehicle{

    public int getSpeedLimit() {
        return speedLimit;
    }

    // I want to implement a limit
    private final int speedLimit=200;


    @Override
    public void accelerate() {

    }

    @Override
    public void deaccelerate() {

    }
}

```

### Prompt
how to run this, baltejsingh@Dell:~/Java_project/JavaInOneVideo$ tree
.
├── JavaInOneVideo.iml
├── out
│   ├── abstraction
│   │   ├── ABC.class
│   │   ├── Animal.class
│   │   ├── Dog.class
│   │   └── Test.class
│   ├── accessModifier
│   │   └── Student.class
│   ├── MultipleInheritence
│   │   ├── Anima.class
│   │   ├── camera.class
│   │   ├── Cat.class
│   │   ├── Dog.class
│   │   ├── musicPlayer.class
│   │   ├── phone.class
│   │   ├── smartPhone.class
│   │   └── test.class
│   ├── production
│   │   └── JavaInOneVideo
│   │       └── com
│   │           └── engineering
│   │               └── digest
│   │                   └── intefaces
│   │                       ├── Animal.class
│   │                       ├── Dog.class
│   │                       └── Test.class
│   ├── test
│   │   ├── Anima.class
│   │   ├── Animal.class
│   │   ├── BankAccount.class
│   │   ├── Car.class
│   │   ├── Cat.class
│   │   ├── Child.class
│   │   ├── Dog.class
│   │   ├── Grandparent.class
│   │   ├── Parent.class
│   │   ├── School.class
│   │   ├── Student.class
│   │   └── test.class
│   └── test2
│       ├── Animal.class
│       ├── Cat.class
│       └── Dog.class
└── src
    └── com
        └── engineering
            └── digest
                └── intefaces
                    ├── Animal.java
                    ├── Dog.java
                    └── Test.java

17 directories, 35 files
baltejsingh@Dell:~/Java_project/JavaInOneVideo$ 

ans:

### Interfaces in java
are blueprints for making a class
interfaces only have **abstract methods** and **static constants**

Interfaces has 2 objectives
1. multiple inheritence
2. abstraction  


Interfaces can have static and default methods also 
Static methods can only be accessed only through the interfaces and not classes that extending it
1. Abstract methods
2. Static constants
3. Static methods
4. Default methods


```java
package com.engineering.digest.intefaces;

// future classes will implement this
public interface Animal {

    int max_age=230;

    public abstract void eat();

    void sleep();


    // once you have 1000s of business logic then this method can tell what interface does
    // this also does not throw error on the sub classes to implement this method
    public static void info(){
        System.out.println("This is an animal instance");
    }
}


package com.engineering.digest.intefaces;

public class Test {
    public static void main(String[] args){
        Dog dog = new Dog();
        System.out.println(dog.max_age);
        System.out.println(Animal.max_age);
        // this will give error 
        Dog.info();

        // this will work
        Animal.info();

    }
}

```

Default is a concreat method 
Static methods can be called using the interface

See if we write a method in the Animal interface, then the sub classes will give error to implement that but if the default is used , then the sub classes will not throw error to imeplement them 
then the default method of the intefaces will be called using the 




### Here I want to use interfaces for multiple inheritance
```java
// Phone interface
interface Phone {
    void call();
}

// Camera interface
interface Camera {
    void takePhoto();
}

// MusicPlayer interface
interface MusicPlayer {
    void playMusic();
}

// SmartPhone class implementing multiple interfaces
class SmartPhone implements Phone, Camera, MusicPlayer {

    @Override
    public void call() {
        System.out.println("Calling from smartphone...");
    }

    @Override
    public void takePhoto() {
        System.out.println("Taking photo...");
    }

    @Override
    public void playMusic() {
        System.out.println("Playing music...");
    }
}

// Test class
public class Test {
    public static void main(String[] args) {
        SmartPhone sp = new SmartPhone();

        sp.call();
        sp.takePhoto();
        sp.playMusic();
    }
}
```


### Difference between abstract class and intefaces
in abstract classes, there are instance variables and if there are instance variables, then to initliaze them , there is constructor also
Here abstract classes can extend just 1 class
But interfaces are not this way
1 class can implement multiple interfaces

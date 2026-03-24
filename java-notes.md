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

### Prompt
I know that this is private variable and it is declared as final so it cant be changed but what is it , like what datatype is it, here, and what is it overall, private final GameState gameState; ?

Great question — this is exactly the kind of thing that builds strong Java fundamentals 🔥

---

# 🧠 Let’s break this line:

```java
private final GameState gameState;
```

---

# ✅ 1. What **datatype** is it?

👉 `GameState` is the **data type**

So this means:

```java
gameState → reference variable of type GameState
```

---

# 💡 What is `GameState`?

It can be:

* a **class**
* an **enum** (very common for states)
* an **interface**

### Example (most common case):

```java
public enum GameState {
    START,
    PLAYING,
    PAUSED,
    GAME_OVER
}
```

👉 Then:

```java
GameState gameState;
```

means:
👉 variable that can store one of these states

---

# ✅ 2. What is `gameState`?

👉 It is a **reference variable (object reference)**

Not a primitive like:

* `int`
* `double`

Instead:
👉 it stores **reference to an object/value of type GameState**

---

# ✅ 3. What does `private` mean?

👉 Only accessible **inside the same class**

---

# ✅ 4. What does `final` mean here?

👉 VERY IMPORTANT:

```java
final GameState gameState;
```

Means:

👉 You can assign it **ONLY ONCE**

---

### ✔️ Example:

```java
this.gameState = GameState.START; // ✅ allowed
```

After that ❌:

```java
this.gameState = GameState.PAUSED; // ❌ ERROR
```

---

# ⚠️ Important subtle point (INTERVIEW GOLD)

If it were an object:

```java
private final List<String> list;
```

👉 You cannot change reference:

```java
list = new ArrayList<>(); ❌
```

BUT you can change contents:

```java
list.add("Hello"); ✅
```

---

# 🔥 Final Understanding

```java
private final GameState gameState;
```

👉 Means:

* `GameState` → data type (class/enum/interface)
* `gameState` → reference variable
* `private` → only inside class
* `final` → assign once, cannot reassign

---

# 🧠 Simple analogy

Think like this:

```id="8vctow"
GameState = blueprint/type
gameState = variable (pointer to that type)
final = can point only once
```

---

# 🚀 Example full usage

```java
public class Game {
    private final GameState gameState;

    public Game() {
        this.gameState = GameState.START;
    }
}
```

---

If you want next level 🔥
I can explain:

* Difference between `final`, `finally`, `finalize` (very common interview question 😈)
* When to use `final` in real projects (React-style immutability mindset)

Just say **“final deep dive”** 😎

### Prompt
i know that serialiazable must an interface as it is being implemented, pl explain what it does, import 

java.io.Serializable;
public class SudokuGame implements Serializable {

Ans:
Good, you’re asking the **right conceptual question** now 🔥

---

# 🧠 What is `Serializable`?

```java
import java.io.Serializable;
```

👉 `Serializable` is a **marker interface**

---

# ❗ What is a *marker interface*?

👉 An interface with **no methods**

```java
public interface Serializable {
}
```

👉 It doesn’t force you to implement anything
👉 It just **marks your class**

---

# 🚀 So what does it actually DO?

When you write:

```java
public class SudokuGame implements Serializable
```

👉 You are telling Java:

> “This object can be converted into a byte stream (saved, sent, or stored)”

---

# 🔥 Real meaning (IMPORTANT)

### Serialization =

👉 Converting object → bytes

### Deserialization =

👉 Converting bytes → object

---

# 📦 Why do we need this?

So that your object can be:

### ✅ Saved to file

```java
ObjectOutputStream → writeObject()
```

### ✅ Sent over network

(Sockets, APIs, distributed systems)

### ✅ Cached / stored

(Redis, sessions, etc.)

---

# 🧩 Example

```java
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception {

        SudokuGame game = new SudokuGame();

        ObjectOutputStream out = new ObjectOutputStream(
            new FileOutputStream("game.ser")
        );

        out.writeObject(game); // ✅ works because Serializable
        out.close();
    }
}
```

---

# ❌ What if NOT Serializable?

```java
public class SudokuGame {
}
```

👉 Then:

```java
out.writeObject(game);
```

💥 Throws error:

```text
java.io.NotSerializableException
```

---

# 🧠 Important concepts

## 1. No methods, still useful 🤯

Because JVM checks:

```id="o1x3bc"
instanceof Serializable
```

---

## 2. You control what gets saved

```java
transient int tempData;
```

👉 `transient` → NOT serialized

---

## 3. serialVersionUID (advanced but important)

```java
private static final long serialVersionUID = 1L;
```

👉 Used to ensure compatibility while deserialization

---

# 🔥 Simple analogy

```id="i7q2gq"
Serializable = "This object is allowed to be packed into a box (bytes)"
```

Without it:

```id="h0k5u7"
Java says → “I don’t trust this object to be packed” ❌
```

---

# 🚀 Final summary

| Concept      | Meaning                        |
| ------------ | ------------------------------ |
| Serializable | Marker interface               |
| Purpose      | Convert object → bytes         |
| Use cases    | File save, network, caching    |
| Methods?     | ❌ None                         |
| Required?    | Only if you want serialization |

---

# 💡 Real-world insight (VERY useful for you)

In backend (like your MERN / Java learning):

* Sessions → serialized
* APIs → objects → JSON (similar idea)
* Distributed systems → serialization everywhere

---

If you want next level 🔥
I can show you:

* How serialization works internally (byte stream structure)
* Difference between Java serialization vs JSON (VERY IMPORTANT)
* Why Java serialization is considered unsafe sometimes 😈

Just say **“serialization deep dive”**

### Prompt

package sudoku.problemDomain;

public class Coordinates {

    private final int x;
    private final int y;


    public Coordinates(int x, int y) {
        this.x = x;
        this.y = y;
    }

    public int getX() {
        return x;
    }

    public int getY() {
        return y;
    }

    @Override
    public boolean equals(Object o){
        if (this==o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Coordinates that = (Coordinates) o;
        return x==that.x && y==that.y;
    }

    @Override
    public int hashCode(){
        return Objects.hash(x,y);
    }
}


Ans
Good question — this is **very important in Java**, especially for your Sudoku game 👇

---

## 🔍 Why is `equals()` used here?

By default, every Java class inherits `equals()` from `Object`.

👉 Default behavior:

```java
obj1.equals(obj2)
```

checks **memory address (reference)**, NOT actual values.

---

### ❌ Without overriding `equals()`

```java
Coordinates c1 = new Coordinates(1, 2);
Coordinates c2 = new Coordinates(1, 2);

System.out.println(c1.equals(c2)); // ❌ false
```

Even though values are same, objects are different → result = `false`

---

### ✅ With your overridden `equals()`

Now it compares **values of x and y**

```java
System.out.println(c1.equals(c2)); // ✅ true
```

---

## 🧠 How your `equals()` works (line by line)

```java
if (this == o) return true;
```

👉 If both references point to same object → directly true
(fast check)

---

```java
if (o == null || getClass() != o.getClass()) return false;
```

👉 Safety check:

* `o == null` → avoid crash
* `getClass()` → ensures same class (Coordinates only)

---

```java
Coordinates that = (Coordinates) o;
```

👉 Typecasting Object → Coordinates
Now you can access `that.x` and `that.y`

---

```java
return x == that.x && y == that.y;
```

👉 Actual comparison:

* x same?
* y same?

If both match → objects are logically equal ✅

---

## ⚡ Why is this important in your Sudoku game?

Imagine you store coordinates like:

```java
Set<Coordinates> visitedCells = new HashSet<>();
```

Without `equals()`:

* `(1,2)` and `(1,2)` are treated as different ❌

With `equals()`:

* They are treated as same cell ✅

---

## 🔗 Why `hashCode()` is also needed?

Whenever you override `equals()`, you MUST override `hashCode()`

Because collections like:

* `HashSet`
* `HashMap`

use **hashCode first, then equals**

---

### Your implementation:

```java
return Objects.hash(x, y);
```

👉 This generates a unique hash based on x and y

---

## 🧠 Simple Real-Life Analogy

Think of `Coordinates` like a **location on Sudoku board**

| Object | x | y |
| ------ | - | - |
| A      | 2 | 3 |
| B      | 2 | 3 |

* Default → A ≠ B ❌ (different objects)
* With equals → A = B ✅ (same position)

---

## 🚀 Final Summary

* `equals()` → compares **content (x, y)**
* `==` → compares **memory reference**
* Needed when:

  * Comparing objects logically
  * Using collections (`Set`, `Map`)
* `hashCode()` must match `equals()`

---

If you want next level understanding, I can show you:
👉 how bugs happen in `HashSet` if `hashCode()` is missing
👉 or how Java internally uses both together (very useful for interviews)

### Prompt
explain this part , Coordinates that = (Coordinates) o;
        return x==that.x && y==that.y;

        ans:
        Alright Baltej, let’s zoom into these two lines — this is the **core of your equality logic** 👇

```java
Coordinates that = (Coordinates) o;
return x == that.x && y == that.y;
```

---

# 🔹 1. What is this line doing?

```java
Coordinates that = (Coordinates) o;
```

### 👉 Problem:

`o` is of type `Object`

```java
public boolean equals(Object o)
```

So Java only knows:

> “o is some object… I don’t know which type”

---

### 👉 Solution: Typecasting

```java
(Coordinates) o
```

You are telling Java:

> “Trust me, this `o` is actually a `Coordinates` object”

Then you store it in:

```java
Coordinates that
```

---

### 🔥 Why is this safe?

Because you already checked earlier:

```java
if (o == null || getClass() != o.getClass()) return false;
```

So now you KNOW:
✅ `o` is not null
✅ `o` is exactly a `Coordinates` object

👉 That’s why casting won’t crash

---

# 🔹 2. What does this line do?

```java
return x == that.x && y == that.y;
```

Now you are comparing:

| Current Object (`this`) | Other Object (`that`) |
| ----------------------- | --------------------- |
| `x`                     | `that.x`              |
| `y`                     | `that.y`              |

---

### 👉 Meaning:

```java
x == that.x
```

✔ same row (or x-position)

```java
y == that.y
```

✔ same column (or y-position)

---

### 👉 Final logic:

```java
return x == that.x && y == that.y;
```

👉 Only return `true` if BOTH match

---

# 🧠 Example

```java
Coordinates c1 = new Coordinates(2, 3);
Coordinates c2 = new Coordinates(2, 3);
Coordinates c3 = new Coordinates(2, 4);
```

---

### Case 1:

```java
c1.equals(c2)
```

After casting:

```java
that = c2
```

Check:

```java
2 == 2  ✅
3 == 3  ✅
```

👉 Result: `true`

---

### Case 2:

```java
c1.equals(c3)
```

Check:

```java
2 == 2  ✅
3 == 4  ❌
```

👉 Result: `false`

---

# ⚡ Important Insight (Interview Level)

This line:

```java
Coordinates that = (Coordinates) o;
```

is needed because:

* Java uses **generic Object type in equals()**
* You must **cast back to your class** to access its fields

---

# 🚀 One-line understanding

👉 “Convert the generic object into a Coordinates object, then compare their x and y values.”

---

If you want, I can next show you:
👉 what happens if you forget the type check (it can crash your program)
👉 or how `instanceof` can replace `getClass()` (very commonly asked)


### Prompt 
so hashcode is also inbult in the class, @Override
    public int hashCode(){
        return Objects.hash(x,y);
    } and why does it need to be overriden 

    ans: 


Yes — **`hashCode()` is also inbuilt**, just like `equals()` 👍

It comes from the base class:
👉 `java.lang.Object`

---

# 🔹 1. What is default `hashCode()`?

If you DON’T override it:

```java
Coordinates c1 = new Coordinates(1,2);
Coordinates c2 = new Coordinates(1,2);

System.out.println(c1.hashCode());
System.out.println(c2.hashCode());
```

👉 You’ll get **different numbers** ❌

Because default `hashCode()` is based on:

> memory address (just like `==`)

---

# 🔹 2. Why do we override it?

Because of this rule in Java:

### ⚠️ Golden Rule:

> If two objects are equal using `equals()`, they MUST have the same `hashCode()`

---

### ❌ Problem if you don’t override

```java
Set<Coordinates> set = new HashSet<>();

set.add(new Coordinates(1,2));
set.add(new Coordinates(1,2));
```

👉 Expected: only 1 element
👉 Actual (without hashCode override): 2 elements ❌

---

### 🧠 Why this happens?

`HashSet` works like this:

1. First → uses `hashCode()` to find bucket
2. Then → uses `equals()` to check equality

---

### ❌ Without overriding:

* hashCode different → goes to different buckets
* equals() never even checked properly

👉 Duplicate gets stored ❌

---

### ✅ With your override:

```java
@Override
public int hashCode(){
    return Objects.hash(x, y);
}
```

👉 Now:

* same x,y → same hashCode
* same bucket → equals() runs → duplicate prevented ✅

---

# 🔹 3. What does `Objects.hash(x, y)` do?

It generates a number based on:

```java
x and y values
```

👉 So:

```java
(1,2) → same hash
(1,2) → same hash
(2,3) → different hash
```

---

# 🔹 4. Why both `equals()` and `hashCode()` together?

Think like this 👇

| Step | Method used  | Purpose                |
| ---- | ------------ | ---------------------- |
| 1    | `hashCode()` | Find location (bucket) |
| 2    | `equals()`   | Confirm exact match    |

---

# 🧠 Real-life analogy

Imagine a library 📚

* `hashCode()` → which shelf to go to
* `equals()` → which exact book on that shelf

---

# 🔥 Final takeaway

* Yes, `hashCode()` is **already in Object class**
* But default version is based on **memory → not useful**
* When you override `equals()`:
  👉 You MUST override `hashCode()`
* Otherwise:
  ❌ Collections like `HashSet`, `HashMap` break

---

# 🚀 One-line summary

👉 `equals()` checks *"Are they logically same?"*
👉 `hashCode()` helps *"Find them quickly in memory"*

---

If you want next level clarity, I can show:
👉 internal working of `HashMap` with buckets (very useful for interviews 🔥)


### Prompt
Why build an interface like this ?
package sudoku.problemDomain;

import java.io.IOException;

public interface IStorage {
    void updateGameData(SudokuGame game) throws IOException;
    SudokuGame getGameData() throws IOException;
}
Ans
Great question — this is actually a **very important design concept** (used in real-world systems) 👇

---

# 🔹 Why build an interface like `IStorage`?

```java
public interface IStorage {
    void updateGameData(SudokuGame game) throws IOException;
    SudokuGame getGameData() throws IOException;
}
```

👉 This is about **decoupling your game logic from storage logic**

---

# 🧠 Think of it like this

Your Sudoku game needs to:

* Save game state
* Load game state

But **how** it does that can vary:

* File system 💾
* Database 🗄️
* Cloud ☁️
* Memory (for testing)

---

## 🔥 Without interface (bad design)

```java
FileStorage storage = new FileStorage();
storage.save(game);
```

👉 Problem:

* Your game is now tightly tied to **FileStorage**
* Changing storage later = rewrite code 😓

---

## ✅ With interface (your design)

```java
IStorage storage = new FileStorage();
storage.updateGameData(game);
```

👉 Now your game only knows:

> “I just need something that can store and retrieve game data”

It DOESN’T care how it’s done 🎯

---

# 🔹 What this enables

## 1. 🔄 Easy swapping of implementations

You can create multiple classes:

```java
class FileStorage implements IStorage
class DatabaseStorage implements IStorage
class CloudStorage implements IStorage
```

And switch anytime:

```java
IStorage storage = new DatabaseStorage(); // no code change elsewhere
```

---

## 2. 🧪 Easy testing (VERY IMPORTANT)

You can create a fake storage:

```java
class FakeStorage implements IStorage
```

👉 Used for testing without real file/database

---

## 3. 🧱 Clean architecture

* `SudokuGame` → game logic
* `IStorage` → contract
* Implementation → separate

👉 This follows **Separation of Concerns**

---

# 🔹 What does this interface define?

It defines a **contract**:

### ✏️ Method 1

```java
void updateGameData(SudokuGame game)
```

👉 Save the game state

---

### 📖 Method 2

```java
SudokuGame getGameData()
```

👉 Load the game state

---

### ⚠️ Why `throws IOException`?

Because storage might involve:

* File reading/writing
* Network calls

👉 These can fail → Java forces you to handle it

---

# 🧠 Real-life analogy

Think of `IStorage` like a **USB port standard**

* Interface = USB standard 🔌
* Implementations = pen drive, hard disk, phone

👉 Laptop doesn’t care what device it is
👉 It just knows how to interact via USB

---

# 🚀 Final Summary

* Interface = **contract**
* It hides implementation details
* Makes your code:

  * Flexible ✅
  * Testable ✅
  * Maintainable ✅

---

# ⚡ One-line understanding

👉 “`IStorage` tells WHAT to do, not HOW to do it.”

---

If you want, I can show you:
👉 how to implement `FileStorage` for this
👉 or how this fits into MVC architecture (very useful for your project 🔥)


    

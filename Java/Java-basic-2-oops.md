

### 🚀 🧠 OOPs in Java (Core Concept)

---

### 📝 OOPs – Overview

👉 OOPs = Object-Oriented Programming

### 4 Pillars:

1. Encapsulation → data hiding

2. Inheritance → reuse code

3. Polymorphism → many forms

4. Abstraction → hide logic

---

### 🔹 1. Class & Object

### Class

Blueprint of object

```java
class Student {
    int age;

    void show() {
        System.out.println(age);
    }
}
```

---

### Object

Instance of class

```java
Student s = new Student();
s.age = 20;
s.show();
```

---

### 🔹 2. Encapsulation

👉 Wrapping data + methods
👉 Use **private + getter/setter**

```java
class Student {
    private int age;

    public void setAge(int age) {
        this.age = age;
    }

    public int getAge() {
        return age;
    }
}
```

---

### Why?

* Data hiding
* Control access

---

### 🔹 3. Inheritance

👉 One class uses another class properties

```java
class Animal {
    void eat() {
        System.out.println("Eating");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Barking");
    }
}
```

---

### Types

* Single
* Multilevel
* Hierarchical
  (❌ Multiple inheritance via class not allowed)

---

### 🔹 4. Polymorphism

👉 One method, many forms

---

### 1. Compile Time (Overloading)

```java
class Test {
    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
}
```

---

### 2. Runtime (Overriding)

```java
class Animal {
    void sound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Bark");
    }
}
```
---

#### 📝 Overloading vs Overriding (Text Notes)

---

#### 🔹 Overloading

* Same method name, **different parameters**
* Parameters must differ by **number / type / order**
* Return type alone is **not enough**
* Happens in **same class**
* **No inheritance required**
* Resolved at **compile time**

---

####🔹 Overriding

* Same method in **parent and child class**
* Method name and parameters must be **exactly same**
* Return type must be **same or subclass (covariant)**
* **Inheritance required**
* Resolved at **runtime**
* Access level cannot be **reduced**

---

#### 🔥 Important Points

* Changing parameter type in child → **overloading, not overriding**
* Changing only return type → **not allowed**
* `final` method → **cannot override**
* `static` method → **not overriding (method hiding)**

---

#### ⚡ Quick Difference

* Overloading → **same name, different input**
* Overriding → **same method, different behavior**

---

#### 🧠 One Line

👉 **Overloading = compile-time**
👉 **Overriding = runtime**

---

#### 🔹 5. Abstraction

👉 Hiding implementation, showing only functionality

---

#### Abstract Class

```java
abstract class Animal {
    abstract void sound();
}

class Dog extends Animal {
    void sound() {
        System.out.println("Bark");
    }
}
```

---

#### Interface

```java
interface Animal {
    void sound();
}

class Dog implements Animal {
    public void sound() {
        System.out.println("Bark");
    }
}
```

---

##### 🔥 Important Differences

### Abstract vs Interface

| Abstract                | Interface               |
| ----------------------- | ----------------------- |
| Can have constructor    | No constructor          |
| Can have normal methods | Mostly abstract methods |
| Single inheritance      | Multiple allowed        |

---

#### 🔥 Interview Points

* Encapsulation → data hiding
* Inheritance → code reuse
* Polymorphism → flexibility
* Abstraction → hide complexity

---

#### ⚡ Quick Revision

* Class → blueprint
* Object → instance
* Encapsulation → private + getter/setter
* Inheritance → extends
* Polymorphism → overloading/overriding
* Abstraction → abstract/interface

---


#### 📝 Interface vs Abstract Class

| Feature          | Interface                                     | Abstract Class                     |
| ---------------- | --------------------------------------------- | ---------------------------------- |
| Keyword          | `interface`                                   | `abstract class`                   |
| Methods          | By default abstract (can have default/static) | Can have abstract + normal methods |
| Variables        | public static final (constants)               | Can have any type                  |
| Constructor      | ❌ Not allowed                                 | ✔ Allowed                          |
| Inheritance      | Multiple (`implements`)                       | Single (`extends`)                 |
| Access Modifiers | public by default                             | Any (private, protected, etc.)     |

---

#### 🔹 Interface Example

```java
interface Animal {
    void sound(); // abstract

    default void eat() {
        System.out.println("Eating");
    }
}

class Dog implements Animal {
    public void sound() {
        System.out.println("Bark");
    }
}
```

---

#### 🔹 Abstract Class Example

```java
abstract class Animal {
    abstract void sound();

    void eat() {
        System.out.println("Eating");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Bark");
    }
}
```

---

#### 🔥 Key Differences (Interview Focus)

### 1. Multiple Inheritance

```java
class A {}
class B {}

class C extends A, B {} // ❌ not allowed
```

```java
interface A {}
interface B {}

class C implements A, B {} // ✔ allowed
```

---

### 2. Variables

```java
interface A {
    int x = 10; // always public static final
}
```

```java
abstract class A {
    int x = 10; // normal variable
}
```

---

### 3. Constructor

```java
abstract class A {
    A() {
        System.out.println("Constructor");
    }
}
```

👉 Interface → ❌ no constructor

---

#### 🔥 When to use what?

👉 Use **Interface**:

* Multiple inheritance needed
* 100% abstraction
* Contract (API)

👉 Use **Abstract Class**:

* Common logic needed
* Partial abstraction
* Shared code

---

#### ⚡ Quick Revision

* Interface → multiple inheritance
* Abstract → partial implementation
* Interface → no constructor
* Abstract → constructor allowed

---

#### 🧠 1-Line

👉 **Interface = contract**
👉 **Abstract class = base class with logic**

---
Perfect 👍 — now **Inheritance Deep (very short notes)**

---

#### 📝 Inheritance (Java)

### 🔹 Definition

👉 **Child class acquires properties & methods of parent class**

---

#### 🔹 Types

* Single
* Multilevel
* Hierarchical
* ❌ Multiple (not allowed via class)

---

#### 🔹 `extends`

👉 Used to inherit class

---

#### 🔹 `super` keyword

👉 Refers to **parent class**

Uses:

* Call parent method
* Access parent variable
* Call parent constructor

---

#### 🔹 Constructor Chaining

👉 Parent constructor runs **first**, then child

👉 If not written → **default `super()` is added automatically**

---

#### 🔹 Method Overriding

👉 Child can **change parent method behavior**

---

#### 🔹 `this` keyword

👉 Refers to **current object**

Uses:

* Access current variable
* Call current constructor

---

#### 🔹 `final`

* final variable → cannot change
* final method → cannot override
* final class → cannot extend

---

#### 🔹 `protected`

👉 Accessible:

* Same package
* Child class (even different package)

---

#### 🔹 IS-A Relationship

👉 Inheritance represents **IS-A**

Example:

* Dog IS-A Animal

---

#### 🔥 Important Points

* Java supports **single inheritance (class)**
* Use **interface for multiple inheritance**
* Constructor is **not inherited**
* Private members are **not directly accessible**

---

#### ⚡ Quick Revision

* extends → inheritance
* super → parent
* this → current
* final → cannot change
* parent constructor → first

---


##### 📝 Encapsulation (Short Notes)

##### 🔹 Definition

👉 **Binding data + methods in one class & hiding data**

---

##### 🔹 How?

* Make variables **private**
* Provide **getter/setter**

---

##### 🔹 Why?

* Data protection
* Controlled access
* Validation possible

---

##### 🔹 Getter / Setter

* Getter → read value
* Setter → update value

---

##### 🔹 Immutable Class (Important)

👉 Object cannot change after creation

Rules:

* Class → final
* Variables → private final
* No setter
* Only getter

---

##### 🔹 Benefit

👉 Thread-safe, secure

---

##### 🔹 Quick Points

* Use private variables
* Expose only needed methods
* Hide internal logic

---

##### ⚡ Encapsulation 1-Line

👉 **Data hiding + controlled access**

---

# 📝 Access Modifiers (Short Notes)

##### 🔹 Types

| Modifier  | Access                     |
| --------- | -------------------------- |
| private   | Only same class            |
| default   | Same package               |
| protected | Same package + child class |
| public    | Everywhere                 |

---

##### 🔹 Visibility

| Modifier  | Class | Package | Child | Outside |
| --------- | ----- | ------- | ----- | ------- |
| private   | ✔     | ❌       | ❌     | ❌       |
| default   | ✔     | ✔       | ❌     | ❌       |
| protected | ✔     | ✔       | ✔     | ❌       |
| public    | ✔     | ✔       | ✔     | ✔       |

---

##### 🔹 Important Points

* **private** → most restricted
* **public** → least restricted
* **default** → no keyword
* **protected** → useful in inheritance

---

##### 🔹 Class Modifier

* Top-level class → only **public / default**
* Cannot use → private / protected

---

##### ⚡ Quick Revision

* private → only class
* default → same package
* protected → package + child
* public → everywhere

---

##### 🧠 One Line

👉 **Access modifier controls visibility**

---




👉 **Inheritance = reuse parent code in child**

---



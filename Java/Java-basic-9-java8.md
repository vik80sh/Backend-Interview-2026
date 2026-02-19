Perfect 🔥 this is **VERY IMPORTANT (Java 8 is asked in almost every interview)**

We will do **short + powerful notes (step by step)**

---

# 🚀 Java 8 Features – Overview

```
1. Lambda Expression
2. Functional Interface
3. Stream API
4. forEach()
5. Optional
6. Method Reference
7. Default & Static methods (Interface)
```

---

# 1. Lambda Expression

👉 Short way to write function (no class needed)

---

### Normal way:

```java
Runnable r = new Runnable() {
    public void run() {
        System.out.println("Hello");
    }
};
```

---

### Lambda:

```java
Runnable r = () -> System.out.println("Hello");
```

---

### Syntax:

```
(parameters) -> expression
```

---

### Example:

```java
(a, b) -> a + b
```

---

### Use:

* reduce boilerplate
* clean code

---

### Quick Note:

```
Lambda → function without name
```

---

# 2. Functional Interface

👉 Interface with **only ONE abstract method**

---

### Example:

```java
@FunctionalInterface
interface MyInterface {
    void show();
}
```

---

### Use with lambda:

```java
MyInterface m = () -> System.out.println("Hi");
```

---

### Built-in Functional Interfaces:

* Predicate → boolean
* Function → input → output
* Consumer → takes input
* Supplier → returns value

---

### Quick Note:

```
Functional Interface → single abstract method
```

---

# 3. Stream API 🔥 (VERY IMPORTANT)

👉 Process collection data **in functional style**

---

### Example:

```java
List<Integer> list = Arrays.asList(1,2,3,4,5);

list.stream()
    .filter(x -> x % 2 == 0)
    .map(x -> x * x)
    .forEach(System.out::println);
```

---

### Output:

```
4
16
```

---

### Steps:

```
Collection → stream() → operations → result
```

---

### Types of operations:

#### Intermediate (lazy)

* filter()
* map()
* sorted()

#### Terminal

* forEach()
* collect()
* count()

---

### Quick Note:

```
Stream → process data (no modification)
```

---

# 4. forEach()

👉 Loop using lambda

---

### Example:

```java
list.forEach(x -> System.out.println(x));
```

OR

```java
list.forEach(System.out::println);
```

---

### Quick Note:

```
forEach → iterate collection
```

---

# 5. Optional

👉 Avoid **NullPointerException**

---

### Example:

```java
Optional<String> name = Optional.ofNullable(null);

System.out.println(name.orElse("Default"));
```

👉 Output:

```
Default
```

---

### Methods:

* isPresent()
* get()
* orElse()
* orElseGet()

---

### Quick Note:

```
Optional → handle null safely
```

---

# 6. Method Reference

👉 Shorter lambda

---

### Example:

```java
list.forEach(System.out::println);
```

---

Instead of:

```java
x -> System.out.println(x)
```

---

### Types:

* Static → Class::method
* Instance → obj::method
* Constructor → Class::new

---

### Quick Note:

```
Method Reference → shortcut lambda
```

---

# 7. Default & Static Methods (Interface)

👉 Interface can have method body

---

### Example:

```java
interface A {
    default void show() {
        System.out.println("Hello");
    }
}
```

---

### Static method:

```java
interface A {
    static void test() {
        System.out.println("Hi");
    }
}
```

---

### Why needed?

👉 Backward compatibility (old code should not break)

---

### Quick Note:

```
Interface can have implementation
```

---

# 🔥 Stream Flow (Important)

```
list.stream()
    .filter()
    .map()
    .collect()
```

👉 Lazy execution → runs only when terminal op is called

---

# 🔥 Interview Questions

---

### Q1. What is Lambda?

👉 Function without name, used with functional interface

---

### Q2. What is Functional Interface?

👉 Interface with one abstract method

---

### Q3. Difference map vs flatMap?

👉 map → 1:1
👉 flatMap → 1:many (flatten)

---

### Q4. Stream vs Collection?

| Stream          | Collection |
| --------------- | ---------- |
| process data    | store data |
| lazy            | eager      |
| no modification | modifiable |

---

### Q5. Why Optional?

👉 Avoid null pointer exception

---

### Q6. Intermediate vs Terminal?

👉 Intermediate → lazy
👉 Terminal → triggers execution

---

# 🔥 Quick Revision

```
Lambda → short function
FI → one method
Stream → process data
Optional → null safety
Method Ref → shortcut
```

---


---

Just say **"exception"** 👍

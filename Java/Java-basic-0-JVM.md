Great 👍 let’s build **interview-level + revision-friendly notes** step by step.

---

# 🚀 JVM + Memory (Java) – Complete Notes

This is **one of the most important topics** for interviews (especially backend roles).

---

# 1. What is JVM?

**JVM (Java Virtual Machine)** is a part of JRE that:

✔ Runs Java bytecode
✔ Converts bytecode → machine code
✔ Manages memory
✔ Handles garbage collection

👉 Java code flow:

```
.java → (javac) → .class (bytecode) → JVM → machine code
```

---

# 2. JVM Architecture (High Level)

JVM has 3 main parts:

```
1. Class Loader
2. Runtime Data Area (Memory)
3. Execution Engine
```

---

## 2.1 Class Loader

Loads `.class` files into memory.

### Types:

* Bootstrap ClassLoader → loads core Java classes
* Extension ClassLoader → loads extension libraries
* Application ClassLoader → loads user classes

---

## 2.2 Execution Engine

Executes bytecode:

* Interpreter → line-by-line execution
* JIT Compiler → converts frequently used code to native code

👉 JIT makes Java fast 🚀

---

# 3. JVM Memory Structure (MOST IMPORTANT)

```
            JVM Memory
--------------------------------
|   Method Area (Class Area)    |
--------------------------------
|            Heap              |
--------------------------------
|   Stack (per thread)         |
--------------------------------
|   PC Register                |
--------------------------------
|   Native Method Stack        |
--------------------------------
```

---

# 4. Heap Memory

👉 **Shared among all threads**

Used to store:

* Objects
* Instance variables

---

## Heap is divided into:

```
Young Generation
   - Eden
   - Survivor (S0, S1)

Old Generation (Tenured)
```

---

### How objects move:

1. New object → Eden
2. Survive GC → Survivor
3. Survive more → Old Gen

---

### Types of GC:

* Minor GC → Young Gen
* Major GC → Old Gen
* Full GC → Entire Heap (slow ⚠️)

---

# 5. Stack Memory

👉 **Thread-specific (each thread has its own stack)**

Stores:

* Method calls
* Local variables
* References

---

### Example:

```java
void test() {
    int a = 10;   // stored in stack
}
```

---

### Important:

❗ Stack is very fast
❗ Memory automatically freed after method ends

---

# 6. Heap vs Stack (Very Important)

| Feature | Heap    | Stack     |
| ------- | ------- | --------- |
| Shared  | Yes     | No        |
| Stores  | Objects | Variables |
| Speed   | Slower  | Faster    |
| Size    | Large   | Small     |
| GC      | Yes     | No        |

---

# 7. Method Area (Class Area)

Stores:

* Class metadata
* Static variables
* Method code

---

### Example:

```java
class A {
    static int x = 10; // stored in Method Area
}
```

---

# 8. PC Register

👉 Each thread has its own PC register

Stores:

* Current executing instruction address

---

# 9. Native Method Stack

Used for:

* Native (non-Java) methods (like C/C++)

---

# 10. String Pool (Important for Interviews)

👉 Stored in Heap

Example:

```java
String a = "hello";
String b = "hello";
```

👉 Only **one object is created** in String Pool

---

But:

```java
String c = new String("hello");
```

👉 Creates **new object in heap**

---

# 11. Garbage Collection (GC)

👉 Automatic memory cleanup

Removes:

* Unused objects

---

### Example:

```java
A obj = new A();
obj = null;  // eligible for GC
```

---

## How GC decides?

👉 Object is eligible if **no reference points to it**

---

## Ways to make eligible:

* Set to `null`
* Reassign reference
* Object goes out of scope

---

# 12. finalize() Method (Deprecated ⚠️)

```java
protected void finalize() {
    System.out.println("Object destroyed");
}
```

❗ Not reliable
❗ Removed in newer Java versions

---

# 13. Memory Leak in Java

👉 Happens when objects are not used but still referenced

Example:

```java
List list = new ArrayList();
while(true){
    list.add(new Object()); // memory leak
}
```

---

# 14. OutOfMemoryError vs StackOverflowError

### OutOfMemoryError

👉 Heap is full

```
Exception in thread "main" java.lang.OutOfMemoryError
```

---

### StackOverflowError

👉 Too many method calls (recursion)

```java
void test(){
    test(); // infinite recursion
}
```

---

# 15. Escape Analysis (Advanced)

👉 JVM decides:

* Object should go in stack or heap

If object doesn't escape method → stored in stack

---

# 16. Interview Questions

---

### Q1. Why Java is platform independent?

👉 Because JVM runs bytecode on any OS

---

### Q2. Why Java is not 100% pure object-oriented?

👉 Because of primitive types (int, char, etc.)

---

### Q3. What happens when you create an object?

```java
A obj = new A();
```

Steps:

1. Class loaded
2. Memory allocated in heap
3. Constructor called
4. Reference stored in stack

---

### Q4. Where are static variables stored?

👉 Method Area

---

### Q5. Is JVM thread-safe?

👉 Yes (memory management + GC)

---

### Q6. Difference between JDK, JRE, JVM?

| Component | Role            |
| --------- | --------------- |
| JDK       | Development kit |
| JRE       | Runtime         |
| JVM       | Executes code   |

---

# 17. Visual Flow (Easy Revision)

```
Stack → Method calls, local vars
Heap → Objects
Method Area → Class + static
```

---

# 🔥 Interview Tip

If interviewer asks:

👉 "Explain JVM memory"

Answer structure:

1. JVM overview
2. Memory areas
3. Heap vs Stack
4. GC basics

👉 This shows **senior-level understanding**

---


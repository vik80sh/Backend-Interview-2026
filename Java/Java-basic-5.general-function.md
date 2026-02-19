Good 👍 very important concept (base of Java 8)

---

# #### 🔹 What is stream() ?

👉 `stream()` is a method that converts a **collection into a Stream**

👉 Stream = **sequence of elements for processing (functional style)**

---

# #### 🔹 Simple Meaning

👉 Collection → data storage
👉 Stream → data processing

---

# #### 🔹 Example

```java
List<Integer> list = Arrays.asList(1,2,3,4);

list.stream()
    .forEach(System.out::println);
```

👉 Here:

* `list` → data
* `stream()` → convert to stream
* `forEach()` → process data

---

# #### 🔹 Why we use stream() ?

👉 To perform operations like:

* filter
* map
* sort
* collect

👉 In **simple and readable way**

---

# #### 🔹 Without Stream (old way)

```java
for(int i : list) {
    if(i % 2 == 0) {
        System.out.println(i);
    }
}
```

---

# #### 🔹 With Stream

```java
list.stream()
    .filter(i -> i % 2 == 0)
    .forEach(System.out::println);
```

👉 Cleaner and shorter

---

# #### 🔹 Important Points

* Stream **does not store data**
* It **processes data**
* Does not modify original collection

---

# #### 🔹 Types of Stream

* `stream()` → sequential
* `parallelStream()` → parallel processing

---

# #### 🔹 Stream Flow

👉 Source → Intermediate → Terminal

Example:

```java
list.stream()              // source
    .filter(x -> x > 2)   // intermediate
    .forEach(System.out::println); // terminal
```

---

# #### 🔥 Interview One-Liner

👉 `stream()` converts collection into stream for processing

---

# #### ⚡ Quick Revision

* Collection → store
* Stream → process
* stream() → convert
* operations → filter, map

---
Good 👍 very important concept (base of Java 8)

---

# #### 🔹 What is stream() ?

👉 `stream()` is a method that converts a **collection into a Stream**

👉 Stream = **sequence of elements for processing (functional style)**

---

# #### 🔹 Simple Meaning

👉 Collection → data storage
👉 Stream → data processing

---

# #### 🔹 Example

```java
List<Integer> list = Arrays.asList(1,2,3,4);

list.stream()
    .forEach(System.out::println);
```

👉 Here:

* `list` → data
* `stream()` → convert to stream
* `forEach()` → process data

---

# #### 🔹 Why we use stream() ?

👉 To perform operations like:

* filter
* map
* sort
* collect

👉 In **simple and readable way**

---

# #### 🔹 Without Stream (old way)

```java
for(int i : list) {
    if(i % 2 == 0) {
        System.out.println(i);
    }
}
```

---

# #### 🔹 With Stream

```java
list.stream()
    .filter(i -> i % 2 == 0)
    .forEach(System.out::println);
```

👉 Cleaner and shorter

---

# #### 🔹 Important Points

* Stream **does not store data**
* It **processes data**
* Does not modify original collection

---

# #### 🔹 Types of Stream

* `stream()` → sequential
* `parallelStream()` → parallel processing

---

# #### 🔹 Stream Flow

👉 Source → Intermediate → Terminal

Example:

```java
list.stream()              // source
    .filter(x -> x > 2)   // intermediate
    .forEach(System.out::println); // terminal
```

---

# #### 🔥 Interview One-Liner

👉 `stream()` converts collection into stream for processing

---

# #### ⚡ Quick Revision

* Collection → store
* Stream → process
* stream() → convert
* operations → filter, map

---


👉 Next important 🔥
**filter(), map(), reduce() (core of Stream API)**

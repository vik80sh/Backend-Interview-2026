
👉 **Collections Framework (VERY IMPORTANT for interviews 🔥)**

Almost every Java interview has questions from this.

---

##### 📌 Topics in Collection

We will go step by step:

1. **Collection vs Collections**
2. **List**

   * ArrayList
   * LinkedList
3. **Set**

   * HashSet
   * LinkedHashSet
   * TreeSet
4. **Map**

   * HashMap
   * LinkedHashMap
   * TreeMap
5. **Queue**

   * PriorityQueue
6. **Iterator**
7. **Comparable vs Comparator**

---

##### 📝 Step 1: Collection vs Collections

---

#### 🔹 Collection

👉 **Interface (root of collection framework)**

* Present in `java.util`
* Parent of List, Set, Queue

👉 Used to store **group of objects**

---

#### 🔹 Collections

👉 **Utility class**

* Provides static methods
* Sorting, searching, etc

👉 Example idea:

```java
Collections.sort(list);
```

---

##### 🔥 Quick Difference

* Collection → interface
* Collections → utility class

---

##### 📝 Step 2: List (Important)

👉 **Ordered collection (index based)**

* Allows duplicates
* Maintains insertion order

---

#### 🔹 ArrayList

👉 Internally uses **dynamic array**

* Fast for read
* Slow for insert/delete (shift required)

---

#### 🔹 LinkedList

👉 Uses **doubly linked list**

* Fast insert/delete
* Slow read

---

#### 🔥 Difference (Important)

* ArrayList → fast read
* LinkedList → fast insert

---

#### 📝 Step 3: Set

👉 **No duplicate elements**

---

#### 🔹 HashSet

* No order
* Uses hashing
* Fast

---

#### 🔹 LinkedHashSet

* Maintains insertion order

---

#### 🔹 TreeSet

* Sorted (ascending)
* Uses tree structure

---

#### 📝 Step 4: Map (VERY IMPORTANT)

👉 Stores **key-value pairs**

* Key must be unique
* Value can duplicate

---

#### 🔹 HashMap

* No order
* Allows 1 null key

---

#### 🔹 LinkedHashMap

* Maintains insertion order

---

#### 🔹 TreeMap

* Sorted by key

---

#### 📝 Step 5: Queue

👉 **FIFO (First In First Out)**

---

#### 🔹 PriorityQueue

* Elements sorted by priority

---

#### 📝 Step 6: Iterator

👉 Used to **traverse collection**

---

#### Example idea:

```java
Iterator it = list.iterator();
```

---

#### 📝 Step 7: Comparable vs Comparator

👉 Used for **sorting**

---

#### Comparable

* Inside class
* `compareTo()`

---

#### Comparator

* Separate class
* `compare()`

---

#### ⚡ Quick Revision

* List → ordered, duplicate
* Set → no duplicate
* Map → key-value
* Queue → FIFO
* ArrayList → fast read
* LinkedList → fast insert
* HashMap → no order
* TreeMap → sorted

---

---

#### 🔹 List (Interface)

👉 **Ordered collection (index based)**
👉 Allows **duplicates**
👉 Maintains **insertion order**

---

#### 🔹 ArrayList

👉 **Dynamic array implementation of List**

---

### 📌 Features

* Stores elements in **continuous memory**
* **Fast read (get)** → O(1)
* **Slow insert/delete (middle)** → shifting required
* Allows duplicates & null

---

### 📌 Example

```java
import java.util.*;

class Test {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();

        list.add("A");
        list.add("B");
        list.add("A");

        System.out.println(list);      // [A, B, A]
        System.out.println(list.get(1)); // B

        list.remove(1);
        System.out.println(list);      // [A, A]
    }
}
```

---

### 📌 Common Methods

* `add()` → add element
* `get(index)` → get value
* `set(index, val)` → update
* `remove(index)` → delete
* `size()` → length

---

### 📌 Use Case

👉 Use when:

* More **reading**
* Less **insertion/deletion**

---

#### 🔹 LinkedList

👉 **Doubly Linked List implementation**

---

### 📌 Features

* Each element stores **data + pointer**
* **Fast insert/delete** → O(1) (no shifting)
* **Slow read** → traversal required
* Allows duplicates & null

---

### 📌 Example

```java
import java.util.*;

class Test {
    public static void main(String[] args) {
        List<String> list = new LinkedList<>();

        list.add("A");
        list.add("B");
        list.add("C");

        System.out.println(list); // [A, B, C]

        list.add(1, "X");
        System.out.println(list); // [A, X, B, C]

        list.remove("B");
        System.out.println(list); // [A, X, C]
    }
}
```

---

### 📌 Extra Methods (LinkedList specific)

* `addFirst()`
* `addLast()`
* `removeFirst()`
* `removeLast()`

---

### 📌 Use Case

👉 Use when:

* Frequent **insert/delete**
* Not much **random access**

---

#### 🔥 ArrayList vs LinkedList

| Feature       | ArrayList   | LinkedList  |
| ------------- | ----------- | ----------- |
| Structure     | Array       | Linked list |
| Read (get)    | Fast        | Slow        |
| Insert/Delete | Slow        | Fast        |
| Memory        | Less        | More        |
| Access        | Index based | Sequential  |

---

#### ⚡ Quick Revision

* ArrayList → fast read
* LinkedList → fast insert
* Both → allow duplicates
* Both → maintain order

---
Perfect 👍 same format — **clean + short + example + methods + use case**

---

#### 🔹 Set (Interface)

👉 **Collection that does NOT allow duplicates**
👉 Not index-based
👉 Order depends on implementation

---

#### 🔹 HashSet

👉 **Hash table based implementation**

---

### 📌 Features

* **No duplicate elements**
* **No insertion order**
* Allows **1 null**
* Fast operations → O(1)

---

### 📌 Example

```java
import java.util.*;

class Test {
    public static void main(String[] args) {
        Set<String> set = new HashSet<>();

        set.add("A");
        set.add("B");
        set.add("A");

        System.out.println(set); // [A, B] (order not fixed)

        set.remove("B");
        System.out.println(set); // [A]
    }
}
```

---

### 📌 Common Methods

* `add()` → add element
* `remove()` → delete
* `contains()` → check value
* `size()` → count

---

### 📌 Use Case

👉 Use when:

* Need **unique elements**
* Order **not important**
* Need **fast performance**

---

#### 🔹 LinkedHashSet

👉 **HashSet + maintains insertion order**

---

### 📌 Features

* No duplicates
* Maintains **insertion order**
* Slightly slower than HashSet

---

### 📌 Example

```java
Set<String> set = new LinkedHashSet<>();

set.add("B");
set.add("A");
set.add("C");

System.out.println(set); // [B, A, C]
```

---

### 📌 Use Case

👉 Use when:

* Need **unique elements**
* Want **insertion order**

---

#### 🔹 TreeSet

👉 **Sorted Set (Red-Black Tree)**

---

### 📌 Features

* No duplicates
* Elements **sorted (ascending)**
* Does NOT allow null
* Slower → O(log n)

---

### 📌 Example

```java
Set<Integer> set = new TreeSet<>();

set.add(5);
set.add(1);
set.add(3);

System.out.println(set); // [1, 3, 5]
```

---

### 📌 Extra Methods

* `first()` → smallest
* `last()` → largest
* `higher()` → next greater
* `lower()` → next smaller

---

### 📌 Use Case

👉 Use when:

* Need **sorted data**
* No duplicates

---

#### 🔥 HashSet vs LinkedHashSet vs TreeSet

| Feature     | HashSet | LinkedHashSet | TreeSet  |
| ----------- | ------- | ------------- | -------- |
| Order       | ❌ No    | ✅ Yes         | ✅ Sorted |
| Duplicate   | ❌ No    | ❌ No          | ❌ No     |
| Null        | ✅ Yes   | ✅ Yes         | ❌ No     |
| Performance | Fast    | Medium        | Slow     |

---

#### ⚡ Quick Revision

* HashSet → fast, no order
* LinkedHashSet → order maintained
* TreeSet → sorted

---

Perfect 👍 let’s do **Map properly (very important 🔥)**

---

#### 🔹 Map (Interface)

👉 Stores **key-value pairs**
👉 **Key must be unique**, value can duplicate

---

#### 🔹 HashMap

👉 **Hash table based implementation**

---

### 📌 Features

* No duplicate keys
* No order
* Allows **1 null key, multiple null values**
* Fast → O(1)

---

### 📌 Example

```java
import java.util.*;

class Test {
    public static void main(String[] args) {
        Map<Integer, String> map = new HashMap<>();

        map.put(1, "A");
        map.put(2, "B");
        map.put(1, "C");

        System.out.println(map); // {1=C, 2=B}

        System.out.println(map.get(1)); // C

        map.remove(2);
        System.out.println(map); // {1=C}
    }
}
```

---

### 📌 Common Methods

* `put(key, value)` → insert
* `get(key)` → fetch
* `remove(key)` → delete
* `containsKey()`
* `containsValue()`
* `keySet()`
* `values()`

---

### 📌 Use Case

👉 Use when:

* Fast lookup needed
* Order not important

---

#### 🔹 LinkedHashMap

👉 **HashMap + maintains insertion order**

---

### 📌 Features

* Same as HashMap
* Maintains **insertion order**

---

### 📌 Example

```java
Map<Integer, String> map = new LinkedHashMap<>();

map.put(2, "B");
map.put(1, "A");

System.out.println(map); // {2=B, 1=A}
```

---

### 📌 Use Case

👉 Use when:

* Need **order + fast access**

---

#### 🔹 TreeMap

👉 **Sorted Map (Red-Black Tree)**

---

### 📌 Features

* Sorted by **key**
* No null key allowed
* Slower → O(log n)

---

### 📌 Example

```java
Map<Integer, String> map = new TreeMap<>();

map.put(5, "A");
map.put(1, "B");
map.put(3, "C");

System.out.println(map); // {1=B, 3=C, 5=A}
```

---

### 📌 Extra Methods

* `firstKey()`
* `lastKey()`
* `higherKey()`
* `lowerKey()`

---

### 📌 Use Case

👉 Use when:

* Need **sorted data**

---

#### 🔥 HashMap vs LinkedHashMap vs TreeMap

| Feature       | HashMap | LinkedHashMap | TreeMap  |
| ------------- | ------- | ------------- | -------- |
| Order         | ❌ No    | ✅ Yes         | ✅ Sorted |
| Duplicate Key | ❌ No    | ❌ No          | ❌ No     |
| Null Key      | ✅ Yes   | ✅ Yes         | ❌ No     |
| Performance   | Fast    | Medium        | Slow     |

---

#### ⚠️ Interview Traps (VERY IMPORTANT)

👉 `put()` with same key → **overwrite value**

```java
map.put(1, "A");
map.put(1, "B"); // replaces A
```

---

👉 `get()` of missing key → **null**

---

👉 Iteration:

```java
for(Integer key : map.keySet()) {
    System.out.println(key + " " + map.get(key));
}
```

---

👉 HashMap is **not thread-safe**

---

#### ⚡ Quick Revision

* Map → key-value
* HashMap → fast, no order
* LinkedHashMap → order
* TreeMap → sorted
* Key → unique

---




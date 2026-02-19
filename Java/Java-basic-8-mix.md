Perfect 👍 — this is **VERY IMPORTANT for interviews**, especially when using **HashMap, HashSet, caching, etc.**

Let’s build **clear + practical + interview-ready notes** 👇

---

# 🚀 equals() & hashCode() – Complete Java Notes

---

# 1. What is equals()?

👉 Used to **compare content (logical equality)** of objects.

### Default behavior (from Object class):

```java
public boolean equals(Object obj)
```

👉 Default compares **reference (memory address)**

---

### Example:

```java
String a = new String("hello");
String b = new String("hello");

System.out.println(a == b);      // false (different objects)
System.out.println(a.equals(b)); // true  (same content)
```

---

# 2. What is hashCode()?

👉 Returns an **integer hash value** for an object.

```java
public int hashCode()
```

👉 Used in **hash-based collections** like:

* HashMap
* HashSet

---

# 3. Why hashCode is needed?

👉 To **store and find objects quickly** in collections.

Instead of checking every object:

```
O(n) → slow
```

Java uses hashCode:

```
O(1) → fast
```

---

# 4. Internal Working (Important)

When you put data in HashMap:

```java
map.put(key, value);
```

Steps:

1. Compute hashCode of key
2. Find bucket/index
3. Use equals() to check exact match

---

👉 Retrieval:

```java
map.get(key);
```

1. Compute hashCode
2. Go to bucket
3. Use equals() to match

---

# 5. equals() vs ==

| Operator   | Meaning              |
| ---------- | -------------------- |
| `==`       | reference comparison |
| `equals()` | content comparison   |

---

### Example:

```java
String a = "hi";
String b = "hi";

System.out.println(a == b);      // true (string pool)
System.out.println(a.equals(b)); // true
```

---

# 6. Contract between equals() & hashCode() (VERY IMPORTANT 🔥)

👉 If two objects are equal → **must have same hashCode**

👉 If hashCode is same → objects **may or may not be equal**

---

### Rule:

```
if (a.equals(b)) → a.hashCode() == b.hashCode()
```

---

# 7. Why Override Both?

If you override only equals():

❌ Collections will break

---

### Example:

```java
class Person {
    int id;

    Person(int id) {
        this.id = id;
    }

    public boolean equals(Object o) {
        Person p = (Person) o;
        return this.id == p.id;
    }
}
```

👉 Missing hashCode()

---

### Problem:

```java
Set<Person> set = new HashSet<>();

set.add(new Person(1));
set.add(new Person(1));

System.out.println(set.size()); // 2 ❌ (should be 1)
```

👉 Because hashCode is different

---

# 8. Correct Implementation

Always override **both** 👇

---

### Example:

```java
class Person {
    int id;
    String name;

    Person(int id, String name) {
        this.id = id;
        this.name = name;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (!(o instanceof Person)) return false;

        Person p = (Person) o;
        return id == p.id && name.equals(p.name);
    }

    @Override
    public int hashCode() {
        return Objects.hash(id, name);
    }
}
```

---

# 9. How HashMap Uses It (Deep Understanding)

```
hashCode → bucket
equals → exact object
```

---

### Scenario:

Two objects:

```
obj1.hashCode() == obj2.hashCode()
```

👉 Same bucket

Then:

```
equals() used to differentiate
```

---

# 10. Hash Collision

👉 Different objects can have same hashCode

Example:

```java
"FB".hashCode() == "Ea".hashCode()
```

👉 Called **collision**

Handled using:

* LinkedList (Java 7)
* Balanced Tree (Java 8+)

---

# 11. Java 8 Optimization

If many collisions:

👉 Bucket converts to **Red-Black Tree**

👉 Improves performance:

```
O(n) → O(log n)
```

---

# 12. Best Practices

✔ Always override both
✔ Use immutable fields (final if possible)
✔ Use Objects.hash()
✔ Avoid changing fields used in hashCode

---

# 13. Real Interview Questions

---

### Q1. What happens if hashCode is not overridden?

👉 Objects may go to different buckets → duplicates allowed

---

### Q2. Can two objects have same hashCode?

👉 Yes (collision)

---

### Q3. Can two equal objects have different hashCode?

👉 ❌ No (violates contract)

---

### Q4. Why equals first checks `this == obj`?

👉 Performance optimization

---

### Q5. Why instanceof check?

👉 To avoid ClassCastException

---

### Q6. What if hashCode always returns same value?

```java
public int hashCode() {
    return 1;
}
```

👉 All objects go to same bucket
👉 Performance becomes **O(n)** ❌

---

# 14. Important Edge Cases

---

### Case 1: Mutable fields

```java
map.put(obj, value);
obj.id = 10;
```

👉 Now retrieval fails ❌

---

### Case 2: Null handling

```java
Objects.equals(a, b); // safe
```

---

# 15. Quick Revision

```
equals() → logical equality
hashCode() → bucket location

Rule:
Equal objects must have same hashCode
```

---

# 🔥 Interview Tip

If interviewer asks:

👉 "Explain equals & hashCode"

Answer like:

1. equals() → content comparison
2. hashCode() → bucket index
3. Contract
4. HashMap internal working

👉 This shows **deep understanding**

---

Perfect 👍 this is **classic interview question 🔥**

Let’s make **short + clear + memorable notes**

---

# 🚀 final vs finally vs finalize

---

# 1. final

👉 **Keyword** → used to restrict change

### Used with:

* variable
* method
* class

---

### final variable

👉 value **cannot be changed**

```java
final int x = 10;
x = 20; // ❌ error
```

---

### final method

👉 cannot be overridden

```java
class A {
    final void show() {}
}

class B extends A {
    void show() {} // ❌ error
}
```

---

### final class

👉 cannot be inherited

```java
final class A {}

class B extends A {} // ❌ error
```

---

### Quick Note:

```
final → restriction
```

---

# 2. finally

👉 Block used in **exception handling**

👉 Always executes (almost always)

---

### Example:

```java
try {
    int x = 10 / 0;
} catch (Exception e) {
    System.out.println("Error");
} finally {
    System.out.println("Always runs");
}
```

👉 Output:

```
Error
Always runs
```

---

### Use case:

* Close resources
* DB connection
* File handling

---

### Special case:

```
finally will NOT run if:
System.exit(0)
```

---

### Quick Note:

```
finally → always executes block
```

---

# 3. finalize()

👉 Method called by **Garbage Collector**

👉 Used for **cleanup before object is destroyed**

---

### Example:

```java
class A {
    protected void finalize() {
        System.out.println("Object destroyed");
    }
}
```

---

### Important:

* Not guaranteed to run ❌
* Deprecated in modern Java ❌
* Avoid using ❌

---

### Quick Note:

```
finalize() → GC cleanup (not reliable)
```

---

# 4. Differences (Very Important 🔥)

| Feature   | final        | finally            | finalize() |
| --------- | ------------ | ------------------ | ---------- |
| Type      | keyword      | block              | method     |
| Use       | restriction  | exception handling | GC         |
| Executes  | compile time | runtime            | GC time    |
| Reliable  | Yes          | Yes                | No         |
| Use today | Yes          | Yes                | Avoid      |

---

# 5. Interview Questions

---

### Q1. Difference between final and finally?

👉 final → keyword (restriction)
👉 finally → block (always executes)

---

### Q2. Is finalize() reliable?

👉 ❌ No (GC dependent)

---

### Q3. Can finally block be skipped?

👉 Yes → using `System.exit(0)`

---

### Q4. Why finalize is removed?

👉 Unpredictable + performance issues

---

# 6. Quick Revision (Best for Notes)

```
final → cannot change
finally → always execute
finalize() → GC cleanup (avoid)
```

---




Just say **"next"** 👍

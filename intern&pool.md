# How it Works
**When you create a string:**
Python first checks interned strings → then string literal pool → if not found, creates a new string.
✅ Interned → ✅ Pool → ❌ Create new.

**Purpose** To Avoid Duplicate

**Benefits** Memory Efficiency & Fast performance ⚡
## **Interning in Python**

### **1. What is Interning?**
Interning = Python stores **one copy** of certain strings and **reuses** it → saves memory and speeds up comparisons.
This process is also known as "string caching" or "string sharing

### **2. Which Strings are Interned?**
- **Short strings** (≤ 20 chars)
- **Identifiers** (e.g., `"x"`, `"my_var"`)
- **Manual interning** via `sys.intern()`

### **3. Manual Interning Example:**
```python
import sys

a = sys.intern("hello world!")
b = sys.intern("hello world!")

print(a is b)  # True
```

---

## **String Literal Pool in Python**

### **1. What is the String Literal Pool?**
- A **cache** for **string literals** written directly in code.
- Python **reuses** strings from the pool instead of creating new ones.

### **2. How Does It Work?**
- Works for **explicit literals** (e.g., `"hello"`)
- Not for **dynamically created strings** (e.g., `"hello" + "world"`)

### **3. String Pool Example:**
```python
a = "hello"
b = "hello"
print(a is b)  # True
```

---

## **String Interning vs String Pool**

|                  | String Interning                                  | String Pool                     |
|------------------|---------------------------------------------------|---------------------------------|
| **Scope**        | Any object (mostly strings)                      | Only strings                    |
| **Purpose**      | Optimize memory (avoid duplicates)               | Manage memory for strings       |
| **Implementation** | Hash table or dictionary                       | Block of memory for strings     |
| **Behavior**     | Optional (can be enabled/disabled)               | Always enabled for strings      |

---
**Summary**:
- **Process = Interning**
- **Memory Space = String Literal Pool**

---

## **When Are Strings Not Interned or Pooled?**

### 1. **Long Strings (>20 chars)**

### 2. **Dynamically Created Strings:** Strings created at runtime (e.g., concatenation) are not interned or pooled

```python
a = "hello"
b = "world"
c = a + b  # dynamic
d = "helloworld"  # literal

print("c is d =", c is d)  # False
print(c, " - id(c)", id(c))
print(d, " - id(d)", id(d))

c1 = a + b
print("c is c1 =", c is c1)  # False not in the same room
print(c1, " - id(c1)", id(c1))
print(c,  " - id(c) ", id(c))
print("is content same =", c == c1)  # True but looks & behaves same
```
---


---

### **Interning**
- Python reuses **short strings** (≤20 chars) and **identifiers** to save memory.
- Manual interning = `sys.intern()`.

```python
import sys
a = sys.intern("hello")
b = sys.intern("hello")
print(a is b)  # True
```

---

### **String Literal Pool**
- **String literals** written directly in code are cached.
- Not applied to **dynamic strings**.

```python
a = "hi"
b = "hi"
print(a is b)  # True
```

---

### **Interning vs Pool**
|                | Interning                         | Pool                         |
|----------------|-----------------------------------|-------------------------------|
| Scope          | Any object (mostly strings)       | Only strings                 |
| Purpose        | Avoid duplicates                  | Manage memory                |
| Behavior       | Optional                          | Always on                    |

---

### **When Not Interned/Pooled**
- **Long strings** (>20 chars)
- **Dynamic strings**

```python
# Long string
a = "this is a very long string"
b = "this is a very long string"
print(a is b)  # False

# Dynamic string
a = "hello"
b = "world"
c = a + b
d = "helloworld"
print(c is d)  # False
```

---

**Summary**:  
✅ Process = Interning  
✅ Memory = String Literal Pool

---

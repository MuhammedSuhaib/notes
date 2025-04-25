###### Ue Ctrl+Shift+V to open the markdown preview.

# Python vs TypeScript/JavaScript: A Beginner-Friendly Comparison

## 1. Introduction

- Python and TypeScript/JavaScript are both widely used programming languages.
- Python is known for simplicity and readability.
- TypeScript is a superset of JavaScript with static typing.
- Both have different strengths and use cases.
- Python is a high-level, interpreted language.
- Python and JS/TS are object-centric, which means almost everything is an object, including functions.
- Both fully support OOP
- Both support first-class functions:

  - Can be assigned to variables

  - Can be passed as arguments

  - Can be returned from other functions

---

## 2. Basic Data Types

![Data Types](./public/datatype.png)

| Python 🐍                    | TypeScript/JavaScript 🟦      |
| ---------------------------- | ----------------------------- |
| `x = 10` (int)               | `let x: number = 10;`         |
| `y = 3.14` (float)           | `let y: number = 3.14;`       |
| `name = "Ali"` (str)         | `let name: string = "Ali";`   |
| `is_true = True` (bool)      | `let isTrue: boolean = true;` |
| `x = None` (null equivalent) | `let x: null = null;`         |

---

## 3. Lists vs Arrays

- Python uses **lists**, while TypeScript/JavaScript uses **arrays**.

```python
nums = [1, 2, 3]  # List
```

```typescript
let nums: number[] = [1, 2, 3]; // Array
```

---

## 4. Tuples vs Arrays (Readonly)

- Python has **tuples** (immutable), while TypeScript has **readonly arrays or tuples**.

```python
data = (4, 5, 6)  # Tuple
```

```ts
const data: readonly [number, number, number] = [4, 5, 6];
```

---

## 5. Dictionaries vs Objects/Maps

- Python uses **dict**, while TypeScript/JavaScript uses **objects or Map**.

```python
info = {"name": "Ali", "age": 25}  # Dictionary
```

```ts
const info: { name: string; age: number } = { name: "Ali", age: 25 };
```

---

## 6. Sets (Same in Both , just difference of syntax)

```python
unique = {1, 2, 3}  # Set
```

```ts
const unique = new Set([1, 2, 3]); // Set
```

---

## 7. Bytes & Bytearray vs Buffer

- Python has **bytes & bytearray**, while JavaScript has **Buffer**.

```python
b = b"hello"  # Bytes
ba = bytearray(b)  # Mutable Bytearray
```

```ts
const b = Buffer.from("hello"); // Buffer
```

---

## 8. Key Differences

- **Python lists ≈ JavaScript/TypeScript arrays**
- **Python tuples ≈ TypeScript readonly arrays**
- **Python dict ≈ JavaScript objects/Map**
- **Python has `None`, JavaScript has `null/undefined`**
- **Python uses indentation and colons ":" for blocks, TypeScript uses `{}`**
- Python is **dynamically typed**, while TypeScript is **statically typed**. 🚀

---

## 9. Function vs Definitions

```python
def greet(name):
    return f"Hello, {name}!"
```

```ts
const greet = (name: string): string => `Hello, ${name}!`;
```

---

## 10. Conditions in Python vs JavaScript/TypeScript

```python
if x > 10:
    print("Big")
elif x == 10:
    print("Equal")
else:
    print("Small")
```

```ts
if (x > 10) {
  console.log("Big");
} else if (x === 10) {
  console.log("Equal");
} else {
  console.log("Small");
}
```

---

## 11. Error Handling

```python
raise ValueError("Error Message")
```

```ts
throw new Error("Error Message");
```

---

# Python Class 1 - Concepts Explained

## 1. Printing & Variable Assignment

```python
print("Hello World!!")

user_name = "abc"
print(user_name)

user_name = "xyz"
print(user_name)
```

### Comparison with JavaScript/TypeScript:

```ts
console.log("Hello World!!");

let userName = "abc";
console.log(userName);

userName = "xyz";
console.log(userName);
```

- Python uses ` print()` for output, whereas JavaScript/TypeScript uses `console.log()`.
- Variables in Python are dynamically typed, while TypeScript requires explicit types.

---

## 2 Line continuation

```py
# Use backslash (\) to continue a line.
# Output remains unchanged.
# Example:
print("This is another very long statement that will be split \
across multiple lines to improve readability \
without breaking the string.")

# Alternatively, use "" to split strings without backslashes:
print("This is a very long statement that will be split "
"across multiple lines to improve readability "
"without breaking the string.")

```

### Comparison with JavaScript/TypeScript:

```ts
// Use backslash (\) to continue a line.
// Output remains unchanged.
// Example:
print(
  "This is another very long statement that will be split \
across multiple lines to improve readability \
without breaking the string."
);

// Alternatively, use "" and , to split strings without backslashes:
print(
  "This is a very long statement that will be split ",
  "across multiple lines to improve readability ",
  "without breaking the string."
);
```

---

## 3. String Interpolation

```python
first_name = "Fahad"
last_name = "Khan"
full_name = f"{first_name} {last_name}"
```

### Comparison with JavaScript/TypeScript:

```ts
let firstName = "Fahad";
let lastName = "Khan";
let fullName = `${firstName} ${lastName}`; // Template literals
```

- Python uses `f"{variable}"`, while JavaScript/TypeScript uses **template literals** `${variable}`.

---

- ### String Formatting

```python
greeting = "Hello, {}!".format(first_name)
```

### Comparison with JavaScript/TypeScript:

- Not available in JavaScript/TypeScript

---

- ### Old-Style Formatting

```python
greeting = "Hello, %s!" % first_name
```

### Comparison with JavaScript/TypeScript:

- Not available in JavaScript/TypeScript

---

- ### String Concatenation

```python
greeting = "Hello, " + first_name + "!"
```

### Comparison with JavaScript/TypeScript:

```ts
let greeting = "Hello, " + firstName + "!";
```

- Both Python and JavaScript/TypeScript use the `+` operator for string concatenation.

---

- ### Joining Strings from Arrays

```python
arr = ["Hello, ", "Fahad", "!"]
greeting = "".join(arr)
```

### Comparison with JavaScript/TypeScript:

```ts
let arr = ["Hello, ", "Fahad", "!"];
let greeting = arr.join(""); // Join array elements
```

- In both Python and JavaScript/TypeScript, `.join()` is used to join elements from an iterable (list/array) into a single string.

---

## 4. String Methods

### Convert to Uppercase

```python
print(full_name.upper())
```

```ts
console.log(fullName.toUpperCase());
```

### Convert to Lowercase

```python
print(full_name.lower())
```

```ts
console.log(fullName.toLowerCase());
```

### Trim Whitespace

```python
print(full_name.strip())
```

```ts
console.log(fullName.trim());
```

### Replace Substrings

```python
text = "quick brown fox"
print(text.replace("fox", "dog"))
```

```ts
let text = "quick brown fox";
console.log(text.replace("fox", "dog"));
```

### Title Case (First Letter Capitalized)

```python
print("hello world".title())
```

```ts
// No built-in method, need custom function
console.log("hello world".replace(/\b\w/g, (c) => c.toUpperCase()));
```

### Swap Case (Upper to Lower & Vice Versa)

```python
print("Hello PYTHON".swapcase())
```

- **Not available in JavaScript/TypeScript**

### Check if String is Digit/Alpha/Alphanumeric

```python
print("12345".isdigit())  # True
print("Hello".isalpha())  # True
print("Hello123".isalnum())  # True
```

```ts
console.log(/^[0-9]+$/.test("12345")); // True
console.log(/^[a-zA-Z]+$/.test("Hello")); // True
console.log(/^[a-zA-Z0-9]+$/.test("Hello123")); // True
```

### Find Substring Index

```python
print("quick brown fox".find("fox"))  # Returns index
print("quick brown fox".find("dog"))  # Returns -1 (not found)
```

```ts
console.log("quick brown fox".indexOf("fox"));
// return index
console.log("quick brown fox".indexOf("dog"));
// return -1 if not found
```

### Count Occurrences

```python
print("quick brown fox".count("o")) #2
```

- **Not available in JavaScript/TypeScript (requires regex or loop)**

### String Slicing

```python
name = "Hamza Ahmed Alvi"
print(name[0:5])  # Hamza
print(name[:5])   # Hamza
print(name[2:])   # mza Ahmed Alvi
```

```ts
let name = "Hamza Ahmed Alvi";
console.log(name.substring(0, 5)); // Hamza
console.log(name.substring(2)); // mza Ahmed Alvi
```

- Python uses `string[start:end]`, while JavaScript/TypeScript uses `substring()`.
- The point to note is that in any language, `slice[]` and `range()` never include the `second argument`.
- Use negative indexes to start the slice from the end of the string:

### capitalize()

- Converts only the first character to uppercase.

```python
txt = "hello, and welcome to my world."
print(txt.capitalize())  # Output: "Hello, and welcome to my world."
```

---

### casefold()

- Converts string into lowercase. `.casefold()` is more aggressive than `.lower()` (e.g., it handles "ß" to "ss").

```python
a = "Straße"
b = "strasse"
print(a.lower())   # Output: "straße"
print(a.casefold()) # Output: "strasse"
```

---

### center()

- Centers the string. First parameter: total length, second parameter: padding character.

```python
txt = "banana"
print(txt.center(20))     # Output: "       banana"
print(txt.center(20, '>')) # Output: ">>>>>>>banana>>>>>>>"
```

---

### format()

- Replaces `{}` with values. Supports string interpolation with format specifiers.

```python
txt = "We have {:<8} chickens."
print(txt.format(49)) # Output: "We have 49       chickens."
```

##### Alignment Options:

- `:<` Left aligns.
- `:>` Right aligns.
- `:^` Centers.

##### Sign Handling:

- `:=` Places the sign at the left.
- `:+` Adds a plus sign for positive values.
- `:-` Adds a minus sign only for negative values.
- `:` Adds space before positive numbers.

##### Number Formatting:

- `:,` Comma separator for thousands.
- `:_` Underscore separator for thousands.
- `:b` Binary format.
- `:c` Unicode character.
- `:d` Decimal format.
- `:e` Scientific notation (lowercase).
- `:E` Scientific notation (uppercase).
- `:f` Fixed-point format.
- `:o` Octal format.
- `:x` Hex format (lowercase).
- `:X` Hex format (uppercase).
- `:%` Percentage format.

---

### ljust()

- Left-aligns a string within a specified width, padding with spaces (or a specified character).

```python
text = "Hello"
result = text.ljust(10, '-')
print(result)  # Output: "Hello-----"
```

---

### lstrip()

- Returns a version of the string with leading spaces removed.

```python
txt = "   Hello"
print(txt.lstrip())  # Output: "Hello"
```

---

### maketrans()

- Creates a translation table for string replacement, used with `translate()`.

```python
trans = str.maketrans("abc", "123")
text = "abc abc"
print(text.translate(trans))  # Output: "123 123"
```

##### Advanced Usage:

```python
trans = str.maketrans({"a": "1", "b": "2", "c": "3"})
text = "abc"
print(text.translate(trans))  # Output: "123"
```

---

### splitlines()

- Splits a string at line breaks and returns a list.

```python
txt = "Thank you for the music\nWelcome to the jungle"
print(txt.splitlines())  # Output: ['Thank you for the music', 'Welcome to the jungle']
```

---

### translate()

- Translates a string using a translation table or a dictionary.

```python
trans = str.maketrans("abc", "123")
text = "abc"
print(text.translate(trans))  # Output: "123"
```

### **`encode()`**: Encodes the string.

### **`endswith(suffix)`**: Checks if string ends with the given suffix.

### **`expandtabs(tabsize)`**: Sets tab size.

### **`format_map()`**: Formats specified values in the string.

### **`index(substring)`**: Returns the position of the substring.

### **`join(iterable)`**: Joins elements of an iterable with the string.

### **`partition(separator)`**: Partitions the string into a tuple of three parts.

### **`rfind(substring)`**: Finds the last occurrence of the substring.

### **`rindex(substring)`**: Finds the last occurrence of the substring and returns its index.

### **`rjust(width, char)`**: Right-aligns the string within the specified width, pads with `char`.

### **`rpartition(separator)`**: Partitions the string into three parts from the right.

### **`rsplit()`**: Splits the string at the specified separator, from the right.

### **`rstrip()`**: Removes trailing whitespaces.

### **`split()`**: Splits the string at the specified separator.

### **`startswith(prefix)`**: Checks if the string starts with the specified prefix.

### **`zfill(width)`**: Pads the string with zeros on the left to the specified width.

### **`isascii()`**: Checks if all characters are ASCII.

### **`isdecimal()`**: Checks if all characters are decimals.

### **`isidentifier()`**: Checks if the string is a valid identifier.

### **`islower()`**: Checks if all characters are lowercase.

### **`isnumeric()`**: Checks if all characters are numeric.

### **`isprintable()`**: Checks if all characters are printable.

### **`isspace()`**: Checks if all characters are whitespaces.

### **`istitle()`**: Checks if the string follows title case.

### **`isupper()`**: Checks if all characters are uppercase.

### **`len()`**

```py
a = "Hello, World!"
print(len(a))
```

### **`in/not in`** Check if "free" is present in the following text:
```py
txt = "The best things in life are free!"
print("free" in txt)
```
---

### Docstring (Multiline Comments)

```python
"""
This is a docstring.
Used for documentation.
"""
```

```ts
/*
This is a multiline comment.
Used for documentation.
*/
```

- Python uses `"""Triple Quotes"""`, while JavaScript/TypeScript uses `/* Block Comments */`.

---

## 5. User Input

```python
name = input("Enter your name: ")
```

```ts
import inquirer from "inquirer";
inquirer
  .prompt([{ name: "name", message: "Enter your name:" }])
  .then((answer) => console.log(answer.name));
```

- Python uses `input()`.
- JavaScript/TypeScript typically use `prompt()` (browser) or `inquirer` (Node.js).

## Conclusion

- **Python has `None`, while JavaScript/TypeScript has `null`.**
- **Python has built-in methods like `swapcase()`, `count()`, while JS/TS do not.**
- **Python uses `f"{var}"` for string interpolation, while JS/TS use template literals `${var}`.**
- **Python string slicing uses `[start:end]`, while JS/TS use `substring()`.**
- **Python uses `input()` for user input, whereas JS/TS require `prompt()` or `inquirer`.**

---

## some topics for Future

1. **Python Virtual Machine (PVM)** executes the **bytecode** generated by the Python interpreter.
2. **Interning**: Python stores immutable objects (like strings and small integers) in a pool for reuse.
3. **Immutable objects**: Objects that cannot be changed after creation (e.g., `str`, `tuple`, `int`).
4. **Implicit Type Conversion**: Python automatically converts one data type to another (e.g., `int + float → float`).
5. **Explicit Type Conversion**: Done using functions like `int()`, `float()`, `str()`, etc.
6. **Sequence Data Types**: `list`, `tuple`, and `string`.
7. **Mapping Data Type**: `dict` (stores key-value pairs).
8. **Adding `int` and `float`** results in a `float`.
9. **Casting `float` to `int`** truncates (removes) the decimal part, not rounds it.
10. **MULTIPLE ASSIGMENT**
    x, y, z = 1, 2.5, "Python" # Using type hints while assigning mutiple variables simultaneously cause and error invalid syntax

print( z)
print( x)
print( y) 11. i**del**
del x removes the variable x from memory. After deletion, trying to access the variable x results in a NameError, indicating that the variable no longer exists.
---`

# C++ vs Python summary
## Key differences
|C++|Python|
|-|-|
|Compiled language.|Interpret language.|
|Strong typed.|Not strong typed.|
|Considerable difficult syntax.|Friendly syntax.|
|Use {, } and ; to define a scope.|Use : and indentation to define a scope.|
|Generally faster at runtime.|Slower at runtime due to an interpreter.|
|Manual memory management.|Built-in memory management.|
|Need main method.|Does not need main method.|

## Common utilities
* Python includes common utilities for you by default. For example, I/O methods, a string data type, basic data structures, etc.
* From this point, all C++ snippets in this document are presumably wrapped inside (replacing line #5) this C++ snippet.
### C++
```cpp
#include <iostream>
#include <string>
using namespace std;
int main() {
    ...
}
```
### Python
```python3
```
*This snippet is intentionally left blank.*

## Variable declaration
* Python does not allow an uninitialized variable declaration.
* Python automatically resolves a variable type from an initial value assignment.
* Both C++ and Python use single quote ('') for `char` data and double quotes ("") for `string` data.
* Python use keywords `True` and `False` for boolean data while C++ use `true` and `false`.
### C++
```cpp
int num;
char letter = 'M';
double x = 1.5;
string txt = "Hello";
bool isTrue = true;
```
### Python
```python3
num = None
letter = 'M'
x = 1.5
txt = "Hello"
is_true = True
```

## Operations
* Both C++ and Python have almost identical operators. They behave similarly and use same symbols.
### C++
```cpp
int num = 4 * 2;
num -= 3;
num = num + 2;
bool isOdd = (num % 2) != 0;
```
### Python
```python3
num = 4 * 2
num -= 3
num = num + 2
is_odd = (num % 2) != 0
```

## if-else statement
* C++ use {, } and ; for a scope declaration while Python use : and indentation.
* `else if` keyword in C++ can be translated to `elif` in Python.
* Python does not need parentheses after `if`, `elif` and `else` keywords.

### C++
```cpp
int score = 22;
if (score < 10) {
    cout << "Bad\n";
} else if (score < 20) {
    cout << "Average\n";
} else {
    cout << "Good\n";
}
```
### Python
```python3
score = 22
if score < 10:
    print("Bad")
elif score < 20:
    print("Average")
else:
    print("Good")
```

## switch statement
* C++ use {, } and ; for a scope declaration while Python use : and indentation.
* Python automatically breaks at the end of each switch case.
### C++
```cpp
int status = 404;
switch (status) {
    case 400:
        cout << "Bad request\n";
        break;
    case 404:
        cout << "Not found\n";
        break;
    default:
        cout << "I don’t know\n";
}
```
### Python
```python3
status = 404
match status:
    case 400:
        print("Bad request")
    case 404:
        print("Not found")
    case _:
        print("I don’t know")
```
*Only python 3.10 or higher!*

## while statement
* C++ use {, } and ; for a scope declaration while Python use : and indentation.
* Python does not need parentheses after `while` keyword.

### C++
```cpp
int i = 0;
while (i < 5) {
    cout << i << "\n";
    i += 1;
}
```
### Python
```python3
i = 0
while i < 5:
    print(i)
    i += 1
```

## for statement
* C++ use {, } and ; for a scope declaration while Python use : and indentation.
* Python does not need parentheses after `for` keyword.
* In contrast to C++, Python use `for` statement to iterate over an iterator. It is not just a syntax sugar for `while` statement.

### C++
```cpp
for (int i = 0; i < 5; i++) {
    cout << 5 - i << "\n";
}
```
### Python
```python3
for i in range(5):
    print(5 - i)
```

## break statement
* The `break` statement behaves the same in both C++ and Python.

### C++
```cpp
int i = 0;
while (true) {
    i += 1;
    if (i > 5)
        break;
}
cout << i << "\n";
```
### Python
```python3
i = 0
while True:
    i += 1
    if i > 5:
        break
print(i)
```

## continue statement
* The `continue` statement behaves the same in both C++ and Python.

### C++
```cpp
int i = 0;
for (int i = 0; i < 5; i++) {
    if (i % 2 == 0)
        continue;
    cout << 5 - i << "\n";
}
```
### Python
```python3
for i in range(5):
    if i % 2 == 0:
        continue
    print(5 - i)
```

## Function declaration
* C++ requires a function to be declared before the `main` function while Python allows a function to be declared almost anywhere, as long as it is declared before a call.
* Both languages have the `return` statement which works exactly the same.

### C++
```cpp
...
int addValues(int a, int b, int c) {
    return a + b + c;
}

int main() {
    int result = addValues(3, -4, 9);
    cout << result << "\n";
}
```
### Python
```python3
def add_values(a: int, b: int, c: int) -> int:
    return a + b + c
result = add_values(3, -4, 9)
print(result)
```

## Array
* Surprisingly, `array` data structure is not included in Python by default. It promotes users to use a `list` data structure instead.

### C++
```cpp
int vars[4] = {4, 1, 0, -3};
cout << vars[2] << "\n";
vars[2] = 7;
cout << vars[2] << "\n";
```
### Python
```python3
from array import array
vars = array('i', [4, 1, 0, -3])
print(vars[2])
vars[2] = 7
print(vars[2])
```

## List
* As you can see, it is much cleaner to use a `list` in Python instead of an `array`.
* Unless your program critically concerns about memory and performance, a `list` should not hurt you badly.

### C++
```cpp
#include <list>
...
list<string> choices {"A", "B", "C"};
choices.push_back("D");
for (auto choice : choices) {
    cout << choice << "\n";
}
```
### Python
```python3
choices = ["A", "B", "C"]
choices.append("D")
for choice in choices:
    print(choice)
```

## Dictionary (Map)
* In Python, you can use a `dict` (dictionary) data structure interchangeably with a C++  `map` data structure. 
* It is included to every Python code by default.

### C++
```cpp
#include <map>
...
map<string, int> table {
    {"coffee", 150},
    {"tea", 130},
    {"chocolate", 145}
};
cout << table["tea"] << "\n";
```
### Python
```python3
table = {
    "coffee": 150,
    "tea": 130,
    "chocolate": 145
}
print(table["tea"])
```

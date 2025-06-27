# C++ with `C` in [`One Short`]()

---

## 📚 Table of Contents

1. [Hello World](#hello-world)
2. [Input and Output](#input-and-output)
3. [Variables and Data Types](#variables-and-data-types)
4. [Conditionals and Loops](#conditionals-and-loops)
5. [Functions](#functions)
6. [Arrays and Strings](#arrays-and-strings)
7. [Pointers](#pointers)
8. [Structures and Classes](#structures-and-classes)
9. [Object-Oriented Programming (OOP)](#object-oriented-programming)
   * [Concepts and Theories](#object-oriented-programming)
   * [Full Examples with Explanations](#object-oriented-programming)
10. [Memory Management](#memory-management)
11. [File Handling](#file-handling)
12. [Data Structures and Algorithms (DSA)](#data-structures-and-algorithms)
13. [Summary: C vs C++](#summary)

---

<a name="hello-world"></a>

## 1. Hello World

### C++

```cpp
#include <iostream> // For standard input and output
using namespace std; // Allows use of standard library without std:: prefix

int main() {
    cout << "Hello, World!" << endl; // Prints message followed by a new line
    return 0; // Indicates successful execution
}
```

### C

```c
#include <stdio.h> // For standard I/O functions like printf

int main() {
    printf("Hello, World!\n"); // Prints message with newline
    return 0; // Exit code
}
```

**Difference**:

* C++ uses `cout` from `<iostream>`.
* C uses `printf` from `<stdio.h>`.

---

<a name="input-and-output"></a>

## 2. Input and Output

### C++

```cpp
int a;
cin >> a; // Takes input from user and stores in 'a'
cout << "You entered: " << a << endl; // Prints the value of 'a'
```

### C

```c
int a;
scanf("%d", &a); // Takes integer input and stores in 'a'
printf("You entered: %d\n", a); // Prints the integer value
```

**Difference**: C++ uses stream-based I/O, which is simpler and more readable than C’s format-based I/O.

---

<a name="variables-and-data-types"></a>

## 3. Variables and Data Types

Both C and C++ support:

* `int`, `float`, `char`, `double`, `long`, `short`

C++ supports additional types:

* `bool`, `string` (class)
* `auto` (type inference)

### C++

```cpp
int a = 10; // Integer variable
float b = 3.14f; // Floating-point variable
bool isAlive = true; // Boolean variable
string name = "Alice"; // String variable
```

### C

```c
int a = 10; // Integer
float b = 3.14f; // Float
// No built-in bool or string in C; use 0/1 for bool, char arrays for strings
```

---

<a name="conditionals-and-loops"></a>

## 4. Conditionals and Loops

### If-Else

```cpp
if (a > 0) cout << "Positive";
else cout << "Non-positive";
```

```c
if (a > 0) printf("Positive");
else printf("Non-positive");
```

### Loops

#### For Loop

```cpp
for (int i = 0; i < 5; i++) {
    cout << i << endl;
}
```

```c
for (int i = 0; i < 5; i++) {
    printf("%d\n", i);
}
```

#### While Loop and Do-While: Same in both

---

<a name="functions"></a>

## 5. Functions

### C++

```cpp
int add(int a, int b) {
    return a + b;
}
```

### C

```c
int add(int a, int b) {
    return a + b;
}
```

**No difference** in basic function syntax. C++ supports **function overloading**.

---

<a name="arrays-and-strings"></a>

## 6. Arrays and Strings

### Arrays

```cpp
int arr[5] = {1, 2, 3, 4, 5};
for (int i = 0; i < 5; i++) {
    cout << arr[i] << " "; // Prints elements of the array
}
```

```c
int arr[5] = {1, 2, 3, 4, 5};
for (int i = 0; i < 5; i++) {
    printf("%d ", arr[i]);
}
```

### Strings

```cpp
string name = "Bob";
// cout << name << endl; // Prints the string
cout << name.length(); // Outputs length of the string
```

```c
char name[] = "Bob";
printf("%s", name);
```

**Key Points:**

* C++ has `string` class with rich methods.
* C strings are null-terminated char arrays.

### Multi-dimensional Arrays

```cpp
int matrix[2][3] = {{1, 2, 3}, {4, 5, 6}};
```

```c
int matrix[2][3] = {{1, 2, 3}, {4, 5, 6}};
```

---

<a name="pointers"></a>

## 7. Pointers

### C++

```cpp
int a = 5;
int *p = &a; // Pointer to variable 'a'
cout << *p; // Dereferencing to get value
```

### C

```c
int a = 5;
int *p = &a;
printf("%d", *p); // Prints value using pointer
```

**Same syntax**, but C++ adds **smart pointers**.

---

<a name="structures-and-classes"></a>

## 8. Structures and Classes

### C

```c
struct Employee {
    char name[20];
    int salary;
};
```

### C++

```cpp
class Employee {
public:
    string name;
    int salary;
    Employee(string n, int s) {
        name = n;
        salary = s;
    }
};
```

**C++ classes** support methods, access modifiers (`public`, `private`).

---

<a name="object-oriented-programming"></a>

## 9. Object-Oriented Programming (Only in C++) [Lern more](#oops-more)

### Key Concepts

| Concept       | Description                        |
| ------------- | ---------------------------------- |
| Class         | Blueprint for creating objects     |
| Object        | Instance of a class                |
| Encapsulation | Wrapping data and methods together |
| Inheritance   | One class inherits from another    |
| Polymorphism  | One function, many forms           |
| Abstraction   | Hiding internal details            |

### Example

```cpp
class Animal {
public:
    void sound() {
        cout << "Animal sound";
    }
};

class Dog : public Animal {
public:
    void sound() {
        cout << "Bark";
    }
};

int main() {
    Animal* a;
    Dog d;
    a = &d;
    a->sound();  // Output: Animal sound (without virtual)
}
```

**Note**: Use `virtual` for runtime polymorphism.

```cpp
class Animal {
public:
    virtual void sound() {
        cout << "Animal sound";
    }
};
```

---

<a name="memory-management"></a>

## 10. Memory Management

### C

```c
int* p = (int*) malloc(sizeof(int));
free(p);
```

### C++

```cpp
int* p = new int;
delete p;
```
#### or

```cpp
int *p = new int; // Dynamic memory allocation
*p = 10; // Assign value
cout << *p; // Access value
delete p; // Free memory
```

C++ also supports **smart pointers** like `unique_ptr`, `shared_ptr`.

---

<a name="file-handling"></a>

## 11. File Handling

### C

```c
FILE *f = fopen("file.txt", "r");
char ch = fgetc(f);
fclose(f);
```

### C++

```cpp
#include <fstream>
ifstream file("file.txt");
char ch;
file >> ch;
file.close();
```

#### or

```cpp
#include <fstream>
ofstream file("example.txt"); // Create file
file << "Hello, file!"; // Write to file
file.close(); // Close the file
```

---

<a name="data-structures-and-algorithms"></a>

## 12. Data Structures and Algorithms (DSA)

* Arrays
* Linked List
* Stack & Queue
* Trees
* Searching & Sorting

### Arrays

* Fixed-size containers
* Stored in contiguous memory

### Linked List (C: Manual, C++: Can use STL or manual)

```c
struct Node {
    int data;
    struct Node* next;
};
```

```cpp
class Node {
public:
    int data;
    Node* next;
};
```

### Stack & Queue

* In C++: Use STL `stack`, `queue`

```cpp
#include <stack>
stack<int> s;
s.push(1);
s.pop();
```

* In C: Implement manually with arrays or linked lists.

### Tree

```cpp
class Node {
public:
    int data;
    Node* left;
    Node* right;
};
```

### Sorting Algorithms

* Bubble Sort
* Selection Sort
* Merge Sort

Implement in both C and C++ using arrays.

### Searching

* Linear Search
* Binary Search (requires sorted array)

---

## 13. Summary: C vs C++

| Feature            | C            | C++                              |
| ------------------ | ------------ | -------------------------------- |
| Type               | Procedural   | Object-Oriented + Procedural     |
| Input/Output       | scanf/printf | cin/cout                         |
| String             | Char arrays  | string class                     |
| Functions          | Yes          | Yes + Overloading                |
| Classes/Objects    | No           | Yes                              |
| Templates          | No           | Yes                              |
| Exception Handling | No           | Yes                              |
| STL                | No           | Yes (stack, queue, vector, etc.) |

---

# OOPS <a name="oops-more"></a>

---

## 9. Object-Oriented Programming (Only in C++)

### Key Concepts and Descriptions

| Concept       | Description                        |
| ------------- | ---------------------------------- |
| Class         | Blueprint for creating objects     |
| Object        | Instance of a class                |
| Encapsulation | Wrapping data and methods together |
| Inheritance   | One class inherits from another    |
| Polymorphism  | One function, many forms           |
| Abstraction   | Hiding internal details            |

---

### 1. Class and Object

**Theory**:

* A class is like a template or blueprint.
* An object is a real instance of that class.

**Code:**

```cpp
#include <iostream>
using namespace std;

class Student {
public:
    string name;
    int age;

    void introduce() {
        cout << "Hi, I am " << name << " and I am " << age << " years old." << endl;
    }
};

int main() {
    Student s1;
    s1.name = "Alice";
    s1.age = 20;
    s1.introduce();
    return 0;
}
```

**Explanation**:

* `Student` is the class.
* `s1` is the object.
* We access properties and methods using the object (`s1.name`).

---

### 2. Encapsulation

**Theory**:

* Keeping data safe from outside interference.
* Achieved using `private` and `public` access modifiers.

**Code:**

```cpp
class BankAccount {
private:
    int balance;

public:
    void deposit(int amount) {
        if (amount > 0)
            balance += amount;
    }

    int getBalance() {
        return balance;
    }
};

int main() {
    BankAccount account;
    account.deposit(1000);
    cout << "Balance: " << account.getBalance();
    return 0;
}
```

**Explanation**:

* Data `balance` is private.
* Access is only possible via `public` methods.

---

### 3. Inheritance

**Theory**:

* A child class inherits features from the parent class.

**Code:**

```cpp
class Vehicle {
public:
    void start() {
        cout << "Vehicle starting..." << endl;
    }
};

class Car : public Vehicle {
public:
    void drive() {
        cout << "Driving the car" << endl;
    }
};

int main() {
    Car myCar;
    myCar.start();  // from Vehicle
    myCar.drive();  // from Car
    return 0;
}
```

**Explanation**:

* `Car` inherits `Vehicle`.
* `Car` object can use both `start()` and `drive()`.

---

### 4. Polymorphism

**Theory**:

* One method behaves differently based on the object.
* Achieved using method overloading or virtual functions.

**Code (Runtime Polymorphism):**

```cpp
class Animal {
public:
    virtual void speak() {
        cout << "Animal sound" << endl;
    }
};

class Dog : public Animal {
public:
    void speak() override {
        cout << "Bark" << endl;
    }
};

int main() {
    Animal* a;
    Dog d;
    a = &d;
    a->speak();  // Output: Bark
    return 0;
}
```

**Explanation**:

* The base class `Animal` has a `speak()` function.
* The derived class `Dog` overrides it.
* Using `virtual`, we ensure correct function is called at runtime.

---

### 5. Abstraction

**Theory**:

* Only show essential features; hide internal details.
* Achieved using abstract classes or interfaces.

**Code:**

```cpp
class Shape {
public:
    virtual void draw() = 0;  // Pure virtual function
};

class Circle : public Shape {
public:
    void draw() override {
        cout << "Drawing Circle" << endl;
    }
};

int main() {
    Shape* s = new Circle();
    s->draw();
    return 0;
}
```

**Explanation**:

* `Shape` is an abstract class.
* `Circle` implements the abstract method.
* This hides how `draw()` works internally.

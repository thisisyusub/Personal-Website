---
title: "Cpp notes"
date: 2022-11-07T21:36:36+04:00
draft: false
ShowRssButtonInSectionTermList: false
---
## 0. Compilers for C++

1. Clang (LLVM)
2. GCC

## 1. Diving in

### 1.1. First program in C++

```cpp
#include <iostream>

int main()
{
    std::cout << "Hello World!" << std::endl;
    return 0;
}
```
```cpp
#include <iostream>

int main()
{
    int a{5};
    int b{6};

    std::cout << "a: " << a << std::endl;
    std::cout << "b: " << b << std::endl;
    return 0;
}
```

### 1.2. Comments

> Block comments can’t be nested!

```cpp
#include <iostream>

// one line comment

/*
Multi
line
comment
*/

int main()
{
    std::cout << "Hello World!" << std::endl;
    return 0;
}
```

### 1.3. Errors

- Compile Time Errors
- Runtime Errors
- Warnings

### 1.4. Data input and output

- std::cout - output
- std::cin - input
- std::cerr - error print
- std::clog - log print

```cpp
#include <iostream>

int main()
{
    int age;
    std::string name;
    std::cout << "Enter your age: ";
    std::cin >> age;
    std::cout << "Enter your name: ";
    std::cin >> name;

    std::cout << "You are " << age << " years old." << std::endl;
    std::cout << "Your name is " << name << std::endl;
    std::clog << "It is log message" << std::endl;
    std::cerr << "It is error message" << std::endl;

		// cin >> name >> age is also okay
    return 0;
}
```

> Get whole line as an input in C++
```cpp
#include <iostream>

int main()
{
    int age;
    std::string name;
    std::cout << "Enter your name and age: ";
    std::getline(std::cin, name);
    std::cin >> age;
    std::cout << "Hello " << name << ", you are " << age << " years old." << std::endl;
    return 0;
}
```
---

## 2. Variables and Data Types

### 2.1. Number Systems
- Decimal (10)
- Binary (2)
- Octal (8)
- Hexadecimal (16)


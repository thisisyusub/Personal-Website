---
title: "Cpp notes"
date: 2022-11-07T21:36:36+04:00
draft: false
subscribe: true
cover:
    image: /notes/cpp/cover.png
---
## 0. Compilers for C++

1. Clang (LLVM)
2. GCC

## 1. Diving in

### First program in C++

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

### Comments

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

### Errors

- Compile Time Errors
- Runtime Errors
- Warnings

### Data input and output

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

### Number Systems
- Decimal (10)
- Binary (2)
- Octal (8)
- Hexadecimal (16)

```cpp
#include <iostream>
using namespace std;

int main()
{
    int decimal = 15;
    int octal = 017;
    int hexadecimal = 0x0F;
    int binary = 0b00001111;

    cout << "Decimal: " << decimal << endl;
    cout << "Octal: " << octal << endl;
    cout << "Hexadecimal: " << hexadecimal << endl;
    cout << "Binary: " << binary << endl;

    return 0;
}
```

### Decimal and Integers

```cpp
#include <iostream>
using namespace std;

int main()
{
    /*
    Braced Initialization

    int a {9};
    int b {2.5};
    int c {}; // 0
    */

    /*
    Funtional Initialization

    int a (9);
    int b(2.5);
    */

    /*
    Assignment Initialization

    int a = 9;
    int b = 2.5;
    */

    return 0;
}
```

### SizeOf Operator

```cpp
#include <iostream>
using namespace std;

int main()
{
    // 2 bytes
    cout << sizeof(short) << endl;
    cout << sizeof(short int) << endl;
    cout << sizeof(signed short) << endl;
    cout << sizeof(signed short int) << endl;
    cout << sizeof(unsigned short int) << endl;

    // 4 bytes
    cout << sizeof(int) << endl;
    cout << sizeof(signed) << endl;
    cout << sizeof(signed int) << endl;
    cout << sizeof(unsigned int) << endl;

    // 4 or 8 bytes
    cout << sizeof(long) << endl;
    cout << sizeof(long int) << endl;
    cout << sizeof(signed long) << endl;
    cout << sizeof(signed long int) << endl;
    cout << sizeof(unsigned long int) << endl;

    // 8 bytes
    cout << sizeof(long long) << endl;
    cout << sizeof(long long int) << endl;
    cout << sizeof(signed long long) << endl;
    cout << sizeof(signed long long int) << endl;
    cout << sizeof(unsigned long long int) << endl;
    return 0;
}
```
> Modifiers like `signed` and `unsigned` can be only applied to integer types.

### Fractional numbers (Floating types)

- float - 4 bytes - 7 precision
- double - 8 bytes - 15 precision
- long double - 12 bytes - precision > double

```cpp
#include <iostream>
#include <iomanip>    
using namespace std;

int main()
{
   float a {1.123456789101234567890f};
   double b {1.123456789101234567890};
   long double c {1.123456789101234567890L};

    cout << setprecision(20) << a << endl;
    cout << setprecision(20) << b << endl;
    cout << setprecision(20) << c << endl;

    std::cout << std::setprecision(20) << b;
    cout << "Size of float: " << sizeof(float) << endl;
    cout << "Size of double: " << sizeof(double) << endl;
    cout << "Size of long double: " << sizeof(long double) << endl;

   return 0;
}
```

> 0/0 = NaN, num / 0 = +/- infinity

### Booleans (1 byte - 8 bits)

- true (1)
- false (0)

```cpp
#include <iostream>
using namespace std;

int main()
{
   bool isAuthenticated {true};

   if (isAuthenticated) {
       cout << "User is authenticated" << endl;
   }
   else {
      cout << "User is not authenticated" << endl; 
   }
      
      cout << ": " << isAuthenticated  << endl; 

   return 0;
}
```

### Characters and Texts (1 byte)

```cpp
#include <iostream>
using namespace std;

int main()
{
   char value  {65};
   cout << value << endl; // A
   cout << static_cast<int>(value) << endl; // 65

   return 0;
}
```

### Auto

auto keyword: The auto keyword specifies that the type of the variable that is being declared will be automatically deducted from its initializer. In the case of functions, if their return type is auto then that will be evaluated by return type expression at runtime. Good use of auto is to avoid long initializations when creating iterators for containers. 

> Note: The variable declared with auto keyword should be initialized at the time of its declaration only or else there will be a compile-time error. 

```cpp
#include <iostream>
using namespace std;

int main()
{
   auto var1 {123};
   auto var2 {123u}; // unsigned
   auto var3 {123ul}; // unsigned long
   auto var4 {123ll}; // long long

   cout << "var1 size: " << sizeof(var1)  << endl;
   cout << "var2 size: " << sizeof(var2)  << endl;
   cout << "var3 size: " << sizeof(var3)  << endl;
   cout << "var4 size: " << sizeof(var4)  << endl;

   return 0;
}
```
---

## 3. Operations on Data


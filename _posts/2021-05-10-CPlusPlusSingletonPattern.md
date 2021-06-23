---
title: "C++: Singleton Pattern"
date: 2021-05-10 19:41:00 +0800
categories: [C++, Example]
tags: [c++,example,singleton]     # TAG names should always be lowercase
---

## Requirement
- Only instantiated once
- Clients need to access the same object

## Solution
Create a static member that is a pointer to the current class, restrict the use of constructors to create the class by making them private, and provide a public static member function that clients can use to access the single, static instance.

## Input
```c++
#include <iostream>
#include <stdio.h>

class SingletonExample
{
public:
    static SingletonExample& getInstance()
    {
        static SingletonExample sInstance;
        return sInstance;
    }

    SingletonExample() {}
};

int main() 
{
    SingletonExample& Singleton1 = SingletonExample::getInstance();
    SingletonExample& Singleton2 = SingletonExample::getInstance();
    std::cout << "Singleton1 addr: " << &Singleton1 << std::endl;
    std::cout << "Singleton2 addr: " << &Singleton2 << std::endl;

    std::cin.get();
    return 0;
}
```

## Output:
```c++
Singleton1 addr: 0015C140
Singleton2 addr: 0015C140
```

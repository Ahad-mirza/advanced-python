# Interfaces in Python

## 📑 Table of Contents
- [Introduction](#Introduction)
- [Why Use Interfaces?](#why-use-interfaces)
- [Defining Interfaces in Python](#defining-interfaces-in-python)
- [Abstract Base Classes (ABCs)](#abstract-base-classes-abcs)
- [Example: Implementing an Interface](#example-implementing-an-interface)
- [Key Takeaways](#key-takeaways)
- [References](#references)

---

## 📌 Introduction
An **interface** in Python defines a contract for classes without implementing the actual logic. Python does not have built-in interfaces like Java or C#, but similar functionality can be achieved using **Abstract Base Classes (ABCs)** from the `abc` module.

## ❓ Why Use Interfaces?
✅ Enforce a structure across multiple classes
✅ Improve code maintainability and readability
✅ Enable polymorphism by ensuring common method signatures
✅ Facilitate scalable and modular development

## 🏗️ Defining Interfaces in Python
Python uses **Abstract Base Classes (ABCs)** to define interfaces. These classes contain abstract methods that must be implemented by derived classes.

## 🔍 Abstract Base Classes (ABCs)
To create an interface in Python, follow these steps:
1. Import `ABC` and `abstractmethod` from the `abc` module.
2. Define an abstract class that inherits from `ABC`.
3. Use the `@abstractmethod` decorator to declare abstract methods.

```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def make_sound(self):
        pass
```

## 🛠️ Example: Implementing an Interface
```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def make_sound(self):
        pass

class Dog(Animal):
    def make_sound(self):
        return "Bark"

class Cat(Animal):
    def make_sound(self):
        return "Meow"

# Instantiate objects
dog = Dog()
cat = Cat()
print(dog.make_sound())  # Output: Bark
print(cat.make_sound())  # Output: Meow
```

## 📌 Key Takeaways
✔ Python does not have built-in interfaces but uses Abstract Base Classes (ABCs) for similar functionality.
✔ The `abc` module allows defining abstract classes and methods.
✔ Classes that inherit from an ABC must implement all abstract methods.
✔ Interfaces help in enforcing method signatures and promoting clean code.

## 📚 References
- [Python Official Documentation - ABCs](https://docs.python.org/3/library/abc.html)
- [PEP 3119 - Introducing Abstract Base Classes](https://peps.python.org/pep-3119/)


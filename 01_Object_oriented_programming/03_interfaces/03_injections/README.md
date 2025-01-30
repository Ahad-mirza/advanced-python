# 🚀 Dependency Injection with Interfaces 🚀

## 📑 Table of Contents
- [📌 Introduction](#introduction)
- [🛠️ Types of Dependency Injection](#types-of-dependency-injection)
- [🛠️ How Dependency Injection Solves Tight Coupling](#how-dependency-injection-solves-tight-coupling)
- [📌 Benefits of Using Dependency Injection](#benefits-of-using-dependency-injection)
- [🛠️ Example: Implementing Dependency Injection with Interfaces](#example-implementing-dependency-injection-with-interfaces)
- [📌 Key Takeaways](#key-takeaways)
- [📚 References](#references)

---

## 📌 Introduction
Tightly coupled code makes modifications difficult and reduces maintainability. A better approach is to use **interfaces** along with **Dependency Injection (DI)**, which allows flexible and modular design by enforcing contracts between components and injecting dependencies dynamically.

## 🛠️ Types of Dependency Injection
Dependency Injection can be implemented in different ways:

1. **Constructor Injection** – Dependencies are provided via a class constructor.
2. **Method Injection** – Dependencies are passed as parameters to methods.
3. **Property Injection (Setter Injection)** – Dependencies are assigned via properties after object creation.
4. **Interface Injection** – A dependency provides its implementation through an interface that the dependent class must implement.

## 🛠️ How Dependency Injection Solves Tight Coupling
By using Dependency Injection (DI), we ensure that components receive their dependencies from external sources instead of creating them internally. This makes it easy to swap out different implementations without modifying the core logic.

## 📌 Benefits of Using Dependency Injection
- **Flexibility** – Easily switch implementations without altering dependent code.
- **Maintainability** – Code changes are localized, making updates simpler.
- **Loose Coupling** – Components communicate through well-defined contracts.
- **Enhanced Readability** – Clear separation of concerns and responsibilities.
- **Better Testability** – Dependencies can be mocked or replaced easily during testing.

## 🛠️ Example: Implementing Dependency Injection with Interfaces
### 🚨 Tightly Coupled Code (Before Using Dependency Injection)
```python
class Engine:
    def start(self):
        print("Engine started")

class Car:
    def __init__(self):
        self.engine = Engine()  # Direct dependency
    
    def drive(self):
        self.engine.start()
        print("Car is moving")
```
### ✅ Loosely Coupled Code (Using Dependency Injection)
```python
from abc import ABC, abstractmethod

class Engine(ABC):
    @abstractmethod
    def start(self):
        pass

class PetrolEngine(Engine):
    def start(self):
        print("Petrol engine started")

class ElectricEngine(Engine):
    def start(self):
        print("Electric engine started")

class Car:
    def __init__(self, engine: Engine):
        self.engine = engine  # Dependency Injection
    
    def drive(self):
        self.engine.start()
        print("Car is moving")

# Using different engine implementations
petrol_car = Car(PetrolEngine())
electric_car = Car(ElectricEngine())

petrol_car.drive()  # Output: Petrol engine started \n Car is moving
electric_car.drive()  # Output: Electric engine started \n Car is moving
```

### 🔥 Why is this better?
- The `Car` class no longer directly depends on a specific engine type.
- We can easily switch from `PetrolEngine` to `ElectricEngine` without modifying `Car`.
- Promotes **dependency injection** and **open-closed principle** (OCP).
- Improves testability by allowing mock implementations.

## 📌 Key Takeaways
- Interfaces help reduce tight coupling by promoting abstraction.
- Dependency Injection allows for flexible and scalable code.
- Using interfaces improves maintainability and testability.
- Abstract Base Classes (ABCs) in Python help define interfaces.
- Injecting dependencies makes unit testing easier and more effective.
- Different types of DI include **Constructor, Method, Property, and Interface Injection**.



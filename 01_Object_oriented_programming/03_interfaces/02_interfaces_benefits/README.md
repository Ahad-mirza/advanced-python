# 🚀 Solving Tight Coupling with Interfaces 🚀

## 📑 Table of Contents
- [📌 Introduction](#introduction)
- [🔍 What is an Interface?](#what-is-an-interface)
- [⚠️ Why Use Interfaces?](#why-use-interfaces)
- [🛠️ How Interfaces Solve Tight Coupling](#how-interfaces-solve-tight-coupling)
- [📌 Benefits of Using Interfaces](#benefits-of-using-interfaces)
- [🛠️ Example: Implementing Interfaces to Avoid Tight Coupling](#example-implementing-interfaces-to-avoid-tight-coupling)
- [📌 Key Takeaways](#key-takeaways)


---

## 📌 Introduction
Tightly coupled code makes modifications difficult and reduces maintainability. A better approach is to use **interfaces**, which allow flexible and modular design by enforcing contracts between components.

## 🔍 What is an Interface?
An **interface** is a blueprint that defines method signatures without implementing them. In Python, interfaces are often created using **Abstract Base Classes (ABCs)** from the `abc` module.

## ⚠️ Why Use Interfaces?
- **Reduces Tight Coupling** – Classes depend on abstractions, not concrete implementations.
- **Improves Code Reusability** – Components can be easily reused in different contexts.
- **Enhances Testability** – Mock objects can be used for testing.
- **Encourages Scalability** – New implementations can be added without modifying existing code.

## 🛠️ How Interfaces Solve Tight Coupling
By using interfaces, we ensure that components depend on abstractions rather than concrete classes. This makes it easy to swap out different implementations without modifying the core logic.

## 📌 Benefits of Using Interfaces
- **Flexibility** – Easily switch implementations without altering dependent code.
- **Maintainability** – Code changes are localized, making updates simpler.
- **Loose Coupling** – Components communicate through well-defined contracts.
- **Enhanced Readability** – Clear separation of concerns and responsibilities.

## 🛠️ Example: Implementing Interfaces to Avoid Tight Coupling
### 🚨 Tightly Coupled Code (Before Using Interfaces)
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
### ✅ Loosely Coupled Code (Using Interfaces)
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

## 📌 Key Takeaways
- Interfaces help reduce tight coupling by promoting abstraction.
- Dependency Injection allows for flexible and scalable code.
- Using interfaces improves maintainability and testability.
- Abstract Base Classes (ABCs) in Python help define interfaces.

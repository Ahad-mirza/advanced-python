# 🔄 Inheritance

Inheritance is the mechanism by which a class (child) can acquire properties and behaviors from another class (parent). It promotes code reusability and establishes a hierarchical relationship between classes.

## 📌 Table of Contents
- [🔹 Key Concepts](#-key-concepts)
- [🛠 Example](#-example)
- [📝 Code Explanation](#-code-explanation)

---

## 🔹 Key Concepts
- **Parent and Child Classes**: The child class inherits attributes and methods from the parent class.
- **Method Overriding**: The child class can modify or extend the functionality of the parent class.
- **Code Reusability**: Reduces redundancy by reusing existing logic from the parent class.

---

## 🛠 Example
```python
class Animal:
    def __init__(self, name):
        self.name = name
    
    def speak(self):
        return "Some sound"

class Dog(Animal):
    def speak(self):
        return "Bark"

class Cat(Animal):
    def speak(self):
        return "Meow"

# Usage
animal = Animal("Generic Animal")
dog = Dog("Buddy")
cat = Cat("Whiskers")

print(animal.speak())  # Output: Some sound
print(dog.speak())     # Output: Bark
print(cat.speak())     # Output: Meow
```

---

## 📝 Code Explanation
### 📌 Parent Class (`Animal`):
- `class Animal:` → Defines a base class `Animal`.
- `def __init__(self, name):` → Initializes the `name` attribute.
- `def speak(self):` → A generic method returning "Some sound".

### 📌 Child Classes (`Dog` and `Cat`):
- `class Dog(Animal):` → Inherits from `Animal`.
- `def speak(self):` → Overrides `speak()` to return "Bark".
- `class Cat(Animal):` → Inherits from `Animal`.
- `def speak(self):` → Overrides `speak()` to return "Meow".

### 📌 Usage:
- `animal = Animal("Generic Animal")` → Creates an instance of `Animal`.
- `dog = Dog("Buddy")` → Creates an instance of `Dog`.
- `cat = Cat("Whiskers")` → Creates an instance of `Cat`.
- `print(animal.speak())` → Calls `speak()` on `Animal` (Output: "Some sound").
- `print(dog.speak())` → Calls overridden `speak()` on `Dog` (Output: "Bark").
- `print(cat.speak())` → Calls overridden `speak()` on `Cat` (Output: "Meow").

### 🚨 Why Inheritance?
- **Eliminates Code Duplication**: The `speak()` method is defined in `Animal`, but specialized in subclasses.
- **Enhances Maintainability**: Changes in the parent class automatically reflect in child classes.
- **Promotes Hierarchical Design**: Enables logical structuring of related objects.

---

## 🤝 Contribution
Feel free to contribute by adding examples, explanations, or improvements.

## 📜 License
This repository is open-source and available for learning purposes.

---

Happy Coding! 🚀

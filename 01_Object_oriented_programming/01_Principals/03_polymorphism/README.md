# 🔄 Polymorphism

Polymorphism allows objects of different classes to be treated as objects of a common superclass. It enables a single interface to represent different underlying forms (data types). This is useful in scenarios where different classes have methods with the same name but potentially different behaviors.

## 📌 Table of Contents
- [🔹 Key Concepts](#-key-concepts)
- [🛠 Example 1](#-example-1)
- [🛠 Example 2](#-example-2)
- [📝 Code Explanation](#-code-explanation)

---

## 🔹 Key Concepts
- **Method Overloading**: Multiple methods with the same name but different signatures.
- **Method Overriding**: A subclass can provide a specific implementation of a method that is already defined in its superclass.
- **Dynamic Method Resolution**: The method that gets executed is determined at runtime, not at compile-time.

---

## 🛠 Example 1
```python
class Animal:
    def speak(self):
        return "Animal sound"

class Dog(Animal):
    def speak(self):
        return "Bark"

class Cat(Animal):
    def speak(self):
        return "Meow"

# Usage
def make_animal_speak(animal):
    print(animal.speak())

animal = Animal()
dog = Dog()
cat = Cat()

make_animal_speak(animal)  # Output: Animal sound
make_animal_speak(dog)     # Output: Bark
make_animal_speak(cat)     # Output: Meow
```

---
## 🛠 Example 2
```python
Copy
Edit
class Shape:
    def area(self):
        pass  # To be implemented by subclasses

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * (self.radius ** 2)

class Rectangle(Shape):
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        return self.length * self.width

class Square(Rectangle):
    def __init__(self, side):
        super().__init__(side, side)

# Usage
def print_area(shape):
    print(f"The area is: {shape.area()}")

circle = Circle(5)
rectangle = Rectangle(4, 6)
square = Square(4)

print_area(circle)       # Output: The area is: 78.5
print_area(rectangle)    # Output: The area is: 24
print_area(square)       # Output: The area is: 16
```

---
## 📝 Code Explanation

### 📌 Parent Class (`Shape`):
- `class Shape:` → Defines an abstract base class `Shape` with a method `area()`, which is intended to be overridden in the subclasses.
- `def area(self):` → The base `area()` method does nothing and serves as a placeholder.

### 📌 Child Classes (`Circle`, `Rectangle`, `Square`):
- `class Circle(Shape):` → Inherits from `Shape` and implements the `area()` method to calculate the area of a circle.
- `class Rectangle(Shape):` → Inherits from `Shape` and implements the `area()` method to calculate the area of a rectangle.
- `class Square(Rectangle):` → Inherits from `Rectangle`, reusing the `area()` method by passing the same side length for both dimensions.

### 📌 Usage:
- `circle = Circle(5)` → Creates an instance of `Circle` with a radius of 5.
- `rectangle = Rectangle(4, 6)` → Creates an instance of `Rectangle` with a length of 4 and width of 6.
- `square = Square(4)` → Creates an instance of `Square` with side length 4.
- `print_area(circle)` → Calls `area()` on `Circle` (Output: "The area is: 78.5").
- `print_area(rectangle)` → Calls `area()` on `Rectangle` (Output: "The area is: 24").
- `print_area(square)` → Calls `area()` on `Square` (Output: "The area is: 16").

### 🚨 Why Polymorphism?
- **Flexibility**: Allows for using the same method name with different implementations, such as `area()` for different shapes.
- **Extensibility**: New subclasses (like `Circle`, `Rectangle`, `Square`) can be added without modifying existing code.
- **Code Reusability**: Reduces code duplication by defining common behavior in a superclass, allowing for specialized behavior in subclasses.

---

## 🤝 Contribution
Feel free to contribute by adding examples, explanations, or improvements.

## 📜 License
This repository is open-source and available for learning purposes.

---

Happy Coding! 🚀


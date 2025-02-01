
# 🚀 Method Injection in Dependency Injection

## 📚 What is Method Injection?

Method Injection is a pattern in **Dependency Injection** (DI) where dependencies are provided to a class via its methods. Unlike constructor injection, the dependencies are passed when a method is called, rather than at object creation. This is useful when you don't always need the dependency or when it is used only within certain methods.

### 🔑 Key Benefits:
- **Flexibility**: Dependencies can be injected only when needed.
- **Loose coupling**: The class is less tightly bound to specific dependencies.
- **No need for constructor parameters**: You don't need to pass dependencies when creating the object.

---

## 🔧 How Method Injection Works

In **method injection**, the required dependencies are passed into a method at runtime when it's called, rather than being passed via the constructor. 

Here's the basic flow:
1. The class declares a method that accepts the required dependencies as parameters.
2. When the method is called, the dependencies are provided.

---

## 🛠 Example in Code

### 🚗 Simple Example (Java)

```java
class Engine {
    public void start() {
        System.out.println("Engine started!");
    }
}

class Car {
    private Engine engine;

    public void drive(Engine engine) {
        this.engine = engine;
        engine.start();
        System.out.println("Car is driving!");
    }
}

public class Main {
    public static void main(String[] args) {
        // Method Injection
        Engine engine = new Engine();
        Car car = new Car();
        car.drive(engine);
    }
}
```

### 🐍 Python Example

```python
class Engine:
    def start(self):
        print("Engine started!")

class Car:
    def drive(self, engine: Engine):
        engine.start()
        print("Car is driving!")

# Method Injection
engine = Engine()
car = Car()
car.drive(engine)
```

---

## 📍 Points to Remember

1. **Constructor vs. Method Injection**: Method injection is more flexible but less explicit than constructor injection. It is used when dependencies are needed only for specific methods.
2. **Optional Dependencies**: Dependencies provided via methods can be optional and may not be required for all methods of the class.
3. **Testability**: Like constructor injection, method injection also improves testability by making dependencies explicit and mockable.

---

## 💡 When to Use Method Injection?
- When dependencies are **optional** or needed **only for specific methods**.
- When you want to inject dependencies **dynamically**.
- For scenarios where you don’t want to provide dependencies through the constructor.

---

## ⚡ Summary

Method injection offers flexibility by allowing dependencies to be injected only when needed, making it less rigid than constructor injection. It provides a cleaner way to handle optional dependencies or situations where not all methods need access to the same dependencies.

---

Happy Coding! 😎👨‍💻

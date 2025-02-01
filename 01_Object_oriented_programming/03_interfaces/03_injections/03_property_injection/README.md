# 🚀 Property (Setter) Injection in Python

## 📋 Table of Contents
1. 🔑 Introduction
2. 🗝️ Key Concepts
3. ⚙️ How It Works
4. 🧩 Example in Python
5. ✅ Advantages
6. ⚠️ Disadvantages
7. 🤔 When to Use
8. 📝 Conclusion

## 🔑 Introduction
Property Injection, also known as Setter Injection, is a type of **Dependency Injection (DI)** where dependencies are provided to a class through public properties or setter methods **after** the object has been created. This approach enhances flexibility and allows changing dependencies without modifying the constructor.

## 🗝️ Key Concepts
- **Dependency Injection (DI):** A design pattern that helps manage dependencies and improve code maintainability.
- **Property Injection:** Dependencies are injected via setter methods or properties after the object is instantiated.

## ⚙️ How It Works
1. Create an object without dependencies.
2. Inject dependencies using setter methods or properties.

## 🧩 Example in Python
```python
# Service class
class Service:
    def __init__(self, service_name=""):
        self.service_name = service_name

    def serve(self):
        print(f"🚀 Service: {self.service_name}")

# Client class with Property Injection
class Client:
    def __init__(self):
        self._service = None

    # Property Injection using a setter
    def set_service(self, service):
        self._service = service

    def start(self):
        if self._service:
            self._service.serve()
        else:
            print("⚠️ No service has been injected!")

# Usage
client = Client()
service = Service("Property Injection Example")

# Injecting the service after object creation
client.set_service(service)
client.start()
```

## ✅ Advantages
- **🎯 Flexibility:** Dependencies can be modified at runtime.
- **🔍 Clear Separation:** Reduces constructor complexity.
- **🧪 Testability:** Easy to mock or stub dependencies for unit tests.

## ⚠️ Disadvantages
- **🚩 Risk of Null References:** If a dependency isn’t set, it may cause runtime errors.
- **📉 Reduced Readability:** It may be unclear which dependencies are essential.

## 🤔 When to Use
- When dependencies are **optional**.
- When you need to **change dependencies** after object creation.
- When managing **configurable services** or plugins.

## 📝 Conclusion
Property Injection is a powerful technique in Dependency Injection patterns. It enhances flexibility and simplifies testing, especially when dealing with optional or changing dependencies. However, it requires careful handling to avoid runtime issues and maintain clean, readable code.

Happy Coding! 🚀


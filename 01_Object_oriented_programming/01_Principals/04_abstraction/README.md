# 🔄 Encapsulation

Encapsulation is one of the four fundamental Object-Oriented Programming (OOP) concepts. It refers to the bundling of data (attributes) and methods (functions) that operate on the data into a single unit, known as a class. It also involves restricting access to certain details of the object to protect its internal state and ensure that it can only be modified in well-defined ways.

## 📌 Table of Contents
- [🔹 Key Concepts](#-key-concepts)
- [🛠 Example](#-example)
- [📝 Code Explanation](#-code-explanation)

---

## 🔹 Key Concepts
- **Private Attributes and Methods**: In Python, attributes and methods prefixed with double underscores (`__`) are considered private, which means they are not accessible from outside the class.
- **Data Hiding**: Encapsulation allows data to be hidden and ensures that the internal state of an object cannot be directly accessed or modified from outside the class.
- **Getter and Setter Methods**: These are public methods that allow controlled access to the private attributes of a class.

---

## 🛠 Example
```python
class UserAuthentication:
    def authenticate(self, username, password):
        user = self.__find_user(username)
        if user is None:
            return "User not found."
        return self.__verify_password(user, password)

    def __find_user(self, username):
        # Simulate finding a user from a database
        users = {"alice": "password123", "bob": "securepass"}
        # Return a dictionary with username and password
        return {"username": username, "password": users.get(username)} if username in users else None

    def __verify_password(self, user, password):
        # Simulate password verification
        if user["password"] == password:
            return f"Welcome, {user['username']}!"
        return "Invalid password."

# Create a UserAuthentication object
auth_system = UserAuthentication()

# Try to authenticate with correct username and password
print(auth_system.authenticate("alice", "password123"))  # Output: Welcome, alice!

# Try to authenticate with an incorrect password
print(auth_system.authenticate("bob", "securepass"))  # Output: Invalid password.

# Try to authenticate with a non-existent username
print(auth_system.authenticate("charlie", "password"))  # Output: User not found.
```

---
## 📝 Code Explanation

### 📌 Class (`UserAuthentication`):
- `class UserAuthentication:` → Defines the class that handles user authentication.
- `def authenticate(self, username, password):` → Public method to authenticate a user by verifying their username and password.
- `def __find_user(self, username):` → Private method to simulate finding a user in a database (accessed only within the class).
- `def __verify_password(self, user, password):` → Private method to verify if the password matches the stored password for the user.

### 📌 Usage:
- `auth_system = UserAuthentication()` → Creates an instance of `UserAuthentication`.
- `auth_system.authenticate("alice", "password123")` → Calls `authenticate()` to check if the username and password are correct (Output: "Welcome, alice!").
- `auth_system.authenticate("bob", "securepass")` → Calls `authenticate()` but provides an incorrect password (Output: "Invalid password.").
- `auth_system.authenticate("charlie", "password")` → Calls `authenticate()` with a non-existent username (Output: "User not found.").

### 🚨 Why Encapsulation?
- **Data Protection**: By making methods like `__find_user` and `__verify_password` private, the internal details of the user authentication process are hidden from outside access.
- **Controlled Access**: External code can only interact with the class through the public `authenticate()` method, ensuring proper flow and validation.
- **Flexibility**: The implementation details of how users are found and passwords are verified can be changed without affecting the code that uses the class.

---

## 🤝 Contribution
Feel free to contribute by adding examples, explanations, or improvements.

## 📜 License
This repository is open-source and available for learning purposes.

---

Happy Coding! 🚀


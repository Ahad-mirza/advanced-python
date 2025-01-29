# 🔒 Encapsulation

Encapsulation is the practice of bundling data (variables) and methods (functions) within a class while restricting direct access to some components to maintain control and security.

## 📌 Table of Contents
- [🔹 Key Concepts](#-key-concepts)
- [🔹 Getter and Setter Methods](#-getter-and-setter-methods)
- [🛠 Example](#-example)
- [📝 Code Explanation](#-code-explanation)


---

## 🔹 Key Concepts
- **Private and Protected Members**: Use access modifiers (e.g., `_protected`, `__private`) to restrict access.
- **Getter and Setter Methods**: Provide controlled access to private attributes.
- **Data Hiding**: Prevents unintended interference and ensures integrity.

---
### 🔹 Getter and Setter Methods

Getter and Setter methods are used to access and modify the private attributes of a class. They are a fundamental part of **Encapsulation**, as they provide controlled access to the internal state of an object.

#### **Getter Method**
- A **Getter** method is used to retrieve the value of a private attribute. It allows read-only access to the internal data of the object.
- The getter method is typically named using the prefix `get_` followed by the attribute name.

#### **Setter Method**
- A **Setter** method is used to modify the value of a private attribute. It allows write-only access to the internal data of the object, ensuring that the data can only be changed in a controlled way.
- The setter method is typically named using the prefix `set_` followed by the attribute name.

#### **Why Use Getter and Setter Methods?**
- **Encapsulation**: These methods help in hiding the internal implementation of a class. The internal state of an object is not directly exposed to external code, which helps protect the data from unintended modification.
- **Data Validation**: Setters allow for validation before modifying an attribute. For example, you can ensure that only valid data is assigned to the attributes.
- **Maintainability**: By using getter and setter methods, you can modify the internal implementation of the class without affecting the external code that interacts with it.

---

### **In Summary:**
- **Getter Methods**: Retrieve the value of private attributes.
- **Setter Methods**: Modify the value of private attributes in a controlled manner.
- They provide controlled access to private data, which helps maintain the integrity and security of the object's state.

---
## 🛠 Example
```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance  # Private attribute

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount

    def get_balance(self):
        return self.__balance

account = BankAccount(1000)
account.deposit(500)
print(account.get_balance())  # Output: 1500
```

---

## 📝 Code Explanation
### 📌 Class Definition:
- `class BankAccount:` → Defines a class named `BankAccount` representing a bank account.

### 📌 Constructor (`__init__` Method):
- `def __init__(self, balance):` → The constructor initializes the account balance.
- `self.__balance = balance` → `__balance` is a **private attribute**, meaning it cannot be accessed directly from outside the class.

### 📌 Deposit Method:
- `def deposit(self, amount):` → This method allows adding money to the account.
- `if amount > 0:` → Ensures only positive amounts can be deposited.
- `self.__balance += amount` → Adds the deposited amount to the balance.

### 📌 Getter Method:
- `def get_balance(self):` → Provides controlled access to the private balance.
- `return self.__balance` → Returns the balance value.

### 📌 Usage:
- `account = BankAccount(1000)` → Creates an account with an initial balance of 1000.
- `account.deposit(500)` → Deposits 500 into the account.
- `print(account.get_balance())` → Prints the updated balance (`1500`).

### 🚨 Why Encapsulation?
- **Protects Data**: The balance cannot be modified directly, ensuring security.
- **Prevents Invalid Changes**: Only valid deposits are allowed.
- **Provides Controlled Access**: The `get_balance` method ensures safe data retrieval.

---



## 🤝 Contribution
Feel free to contribute by adding examples, explanations, or improvements.

## 📜 License
This repository is open-source and available for learning purposes.

---

Happy Coding! 🚀



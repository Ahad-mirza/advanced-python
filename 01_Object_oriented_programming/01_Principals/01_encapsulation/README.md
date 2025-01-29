# 🔒 Encapsulation

Encapsulation is the practice of bundling data (variables) and methods (functions) within a class while restricting direct access to some components to maintain control and security.

## 📌 Table of Contents
- [🔹 Key Concepts](#-key-concepts)
- [🛠 Example](#-example)
- [📝 Code Explanation](#-code-explanation)


---

## 🔹 Key Concepts
- **Private and Protected Members**: Use access modifiers (e.g., `_protected`, `__private`) to restrict access.
- **Getter and Setter Methods**: Provide controlled access to private attributes.
- **Data Hiding**: Prevents unintended interference and ensures integrity.

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



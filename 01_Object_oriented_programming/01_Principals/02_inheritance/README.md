# 🔄 Inheritance in Python

Inheritance is a fundamental concept in object-oriented programming that allows a class (child class) to inherit properties and methods from another class (parent class). This promotes code reuse and establishes a relationship between classes, reducing redundancy.

## 📌 Table of Contents
- [🔹 Key Concepts](#-key-concepts)
- [🛠 Example](#-example)
- [📝 Code Explanation](#-code-explanation)
- [🔑 Key Points Summary](#-key-points-summary)

---

## 🔹 Key Concepts
- **Parent and Child Classes**: The child class inherits attributes and methods from the parent class, allowing for the reuse of code.
- **Method Overriding**: The child class can modify or extend the functionality of methods from the parent class.
- **Encapsulation**: By using private attributes (e.g., `_balance`), inheritance can provide better control over data access and modification.
- **Code Reusability**: Inheritance reduces redundancy by reusing existing logic from the parent class and adding specific functionality in child classes.

---

## 🛠 Example

```python
# Base class
class BankAccount:
    def __init__(self):
        self._balance = 0

    # Getter and Setter for 'balance'
    def set_balance(self, balance):
        if balance >= 0:
            self._balance = balance
        else:
            print("Invalid balance")

    def get_balance(self):
        return self._balance

    def deposit(self, amount):
        if amount > 0:
            self._balance += amount
        else:
            print("Deposit amount must be positive")

    def withdraw(self, amount):
        if 0 < amount <= self._balance:
            self._balance -= amount
        else:
            print("Insufficient funds or invalid amount")

# Derived class
class SavingsAccount(BankAccount):
    def __init__(self):
        super().__init__()
        self._interest_rate = 0.03  # Default interest rate of 3%

    # Getter and Setter for 'interest_rate'
    def get_interest_rate(self):
        return self._interest_rate

    def set_interest_rate(self, rate):
        if 0 <= rate <= 1:
            self._interest_rate = rate
        else:
            print("Invalid interest rate")

    def calculate_interest(self):
        return self.get_balance() * self.get_interest_rate()

# Usage
savings = SavingsAccount()
savings.set_balance(1000)
savings.set_interest_rate(0.05)  # 5% interest rate

print(f"Balance: ${savings.get_balance()}")  # Output: Balance: $1000
print(f"Interest Rate: {savings.get_interest_rate() * 100}%")  # Output: Interest Rate: 5%
print(f"Interest: ${savings.calculate_interest()}")  # Output: Interest: $50.0
savings.deposit(200)
print(f"New Balance after deposit: ${savings.get_balance()}")  # Output: New Balance after deposit: $1200
```

---
## 📝 Code Explanation

### 📌 Parent Class (BankAccount):
- `class BankAccount:` → Defines a base class `BankAccount` for general banking functionality.
- `def __init__(self):` → Initializes the balance attribute with a default value of 0.
- `set_balance(self, balance):` → Sets the balance to a positive value, ensuring valid input.
- `get_balance(self):` → Returns the current balance.
- `deposit(self, amount):` → Increases the balance by the specified amount if positive.
- `withdraw(self, amount):` → Decreases the balance by the specified amount if sufficient funds exist.

### 📌 Child Class (SavingsAccount):
- `class SavingsAccount(BankAccount):` → Inherits from `BankAccount`, adding specific features like interest rate and interest calculation.
- `def __init__(self):` → Initializes the `SavingsAccount`, calling the parent class constructor and setting a default interest rate.
- `get_interest_rate(self):` → Returns the interest rate for the savings account.
- `set_interest_rate(self, rate):` → Sets a valid interest rate (between 0 and 1).
- `calculate_interest(self):` → Calculates interest based on the current balance and interest rate.

### 📌 Usage:
- `savings = SavingsAccount()` → Creates an instance of `SavingsAccount`.
- `savings.set_balance(1000)` → Sets the balance to $1000.
- `savings.set_interest_rate(0.05)` → Sets the interest rate to 5%.
- `print(f"Balance: ${savings.get_balance()}")` → Prints the balance ($1000).
- `print(f"Interest Rate: {savings.get_interest_rate() * 100}%")` → Prints the interest rate (5%).
- `print(f"Interest: ${savings.calculate_interest()}")` → Calculates and prints the interest ($50).
- `savings.deposit(200)` → Deposits $200 into the account.
- `print(f"New Balance after deposit: ${savings.get_balance()}")` → Prints the updated balance ($1200).

## 🔑 Key Points Summary
- Inheritance allows the child class to inherit attributes and methods from the parent class.
- **Method Overriding**: Child classes can override parent methods to provide specialized functionality (e.g., interest calculation).
- **Encapsulation**: Private attributes (`_balance`, `_interest_rate`) are used to manage data access.
- **Code Reusability**: The `BankAccount` class provides reusable methods for managing account balances, which are extended in the `SavingsAccount` class.
- **Improved Maintainability**: Changes in the parent class automatically affect the child class, reducing redundancy.

---

## 🤝 Contribution
Feel free to contribute by adding examples, explanations, or improvements.

## 📜 License
This repository is open-source and available for learning purposes.

---

Happy Coding! 🚀

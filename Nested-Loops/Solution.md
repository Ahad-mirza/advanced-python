# Python Problem Solutions 🐍

## 1. Check Numbers Are Even or Odd 🟢🔴

### Problem:
- You need to create a program that asks the user to input a number and checks if it is even or odd. 
- The program should allow the user to quit by entering the word "Stop".
- If the input is invalid, an error message should be displayed.

### Solution:

```python
while True:
    number = input("Enter a number to check it's odd or even (enter 'Stop' to quit): ")
    
    if number.lower() == "stop":
        print("You have quit the program 'Goodbye'")
        break
    else:
        try:
            number = int(number)
            if number % 2 == 0:
                print("You have entered an even number")
            else:
                print("You have entered an odd number")
        except ValueError:
            print("You have entered an invalid number")
2. Sum of Two Numbers ➕
Problem:
Create a program that asks the user whether they want to calculate the sum of two numbers.
If yes, ask the user to input two numbers and return their sum.
If the input is invalid or not a number, show an error message.
Allow the user to exit by typing "no".
Solution:
python
Copy code
while True:
    choice = input("Do you want to get the sum of two numbers (yes/no): ")
    if choice.lower() == "no":
        print("Goodbye!")
        break
    elif choice.lower() == "yes":
        print("Let's go") 
        number_1 = input("Enter 1st number: ")
        number_2 = input("Enter 2nd number: ")
        try:
            print("Let's get the sum of these numbers")
            number_1 = int(number_1)
            number_2 = int(number_2)
            print(f"{number_1} + {number_2} = {number_1 + number_2}")
        except ValueError:
            print("Please enter a valid number")    
    else:
        print("You entered an invalid input. Enter (yes/no)")        
3. Multiplication Table Generator ✖️
Problem:
Create a program that asks the user to input a number and generates its multiplication table from 1 to 10.
The user should be able to quit the program by typing "exit".
If the input is invalid, an error message should be displayed.
Solution:
python
Copy code
while True:
    number = input("Enter a number to generate its multiplication table \nor type 'exit' to stop this: ")
    try:
        if number.lower() == "exit":
            print("Goodbye")
            break
        else:   
            number = int(number)
            print(f"Let's print the table for {number}")
            for i in range(1, 11):
                print(f"{number} X {i} = {number * i}")    
    except ValueError:
        print("Enter a valid number")
4. Countdown Timer ⏳
Problem:
Create a program that asks the user to input a number to start a countdown.
The program should count down from the input number to zero.
If the user types "stop", the countdown should stop, and the program should exit.
Solution:
python
Copy code
while True:
    number = input("Enter a number to start the countdown (Type 'stop' to quit): ")
    
    if number.lower() == "stop":
        print("Goodbye! 👋")
        break
    else:
        number = int(number)
        print("Countdown:")
        for i in range(number, -1, -1):
            print(i)
5. Simple Calculator ➗✖️➕
Problem:
Create a simple calculator program that asks the user to enter two numbers and perform a chosen operation (+, -, *, /).
The program should handle invalid inputs gracefully by showing an error message.
The program should allow the user to exit by typing "no" when asked if they want to calculate again.
Solution:
python
Copy code
choice = input("Do you want to calculate with two numbers (yes/no): ").lower()
while True:
    if choice == "no":
        print("Goodbye!")
        break
    elif choice == "yes":
        print("Let's calculate the numbers")
        number_1 = input("Enter 1st number: ")
        symbol = input("Enter (+, -, *, /): ")
        number_2 = input("Enter 2nd number: ")
        try:
            number_1 = float(number_1)
            number_2 = float(number_2)
            if symbol == '*':
                result = number_1 * number_2
            elif symbol == '+':
                result = number_1 + number_2
            elif symbol == '-':
                result = number_1 - number_2 
            elif symbol == '/':
                result = number_1 / number_2       
            print(f"{number_1} {symbol} {number_2} = {result}")
        except ValueError:
            print("Enter a valid number")
            continue
    else:
        print("Enter 'yes' or 'no'")
End of Problems 🎉

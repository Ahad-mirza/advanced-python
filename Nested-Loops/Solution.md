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
            print("You have entered an invalid number") # Python Problem Solutions 🐍

## 2. Sum of two numbers ➕

### Problem:
- Create a program that asks the user whether they want to calculate the sum of two numbers.
- If yes, ask the user to input two numbers and return their sum.
- If the input is invalid or not a number, show an error message.
- Allow the user to exit by typing "no".

### Solution:

```python
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

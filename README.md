1) Write a python code to verify if three side (line) lengths provided by user can make a triangle:
def is_triangle(a, b, c):
    if a + b > c and a + c > b and b + c > a:
        return True
    else:
        return False

a = input("Please provide a: ")
b = input("Please provide b: ")
c = input("Please provide b: ")

if is_triangle(a, b, c):
    print("Can form a triangle")
else:
    print("Can't form a triangle")


    2) Create a robust and user-friendly system for validating pin-codes entered by users.
Develop a Pin-Code Validator code to ensure pin security and adherence to specific criteria:

·       Pin-codes consist only of numbers and are either 4 or 6 digits in length.

·       Enforce a rule preventing consecutive numbers to repeat in the pin-code sequence.

·       Ask for confirmation to check if two entered pin-codes match, indicating successful validation.

def is_valid_pin(pin):
    
    if pin.isdigit() and (len(pin) == 4 or len(pin) == 6):
      
        for i in range(len(pin) - 1):
            if pin[i] == pin[i + 1]:
                return False
        return True
    else:
        return False

def validate_pin():
    while True:
        pin1 = input("Enter your pin-code (4 or 6 digits in length, no consecutive numbers repeat): ")
        if is_valid_pin(pin1):
            confirm_pin = input("Confirm your pin-code: ")
            if pin1 == confirm_pin:
                print("Pin-code correct.")
                break
            else:
                print("Pin-codes do not match. Please try again.")
        else:
            print("Incorrect pin-code. Please enter a correct pin-code.")


validate_pin()
            
3) Create a Python application that displays a random tip from a collection of tips stored in a text file.


import random

def get_random_tip(tips_file):
    with open(tips_file, 'r') as file:
        tips = file.readlines()
    return random.choice(tips).strip()

def main():
    tips_file = "'C:\\tips.txt'"
    random_tip = get_random_tip(tips_file)
    print("Random Tip:")
    print(random_tip)

if __name__ == "__main__":
    main()

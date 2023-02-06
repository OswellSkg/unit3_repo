# Task

Create a Python class for a Bank Office that follows the UML diagram below and passes the test file test_quiz35.py
<img width="551" alt="Screen Shot 2023-02-05 at 21 20 38" src="https://user-images.githubusercontent.com/112055140/216818331-00a44e83-7257-45db-9b68-9c231cc0d017.png">


# Program
```.py
#2023-01-13 Quiz 035
import random
class Account:
    def __init__(self):
        self.balance = 0
        self.holder_name = ""
        self.holder_email = ""
        number1 = random.randint(100,999)
        number2 = random.randint(100,999)
        number3 = random.randint(0,9)
        self.number = [number1,number2,number3]

    def get_account_no(self):
        return f"{self.number[0]}-{self.number[1]}-{self.number[2]}"

    def set_holder_name(self,name):
        if not isinstance(name, str):
            raise ValueError("Name must be in letters")
        self.holder_name = name
        temp = f"Holder's name set to {self.holder_name}"
        return temp

    def set_holder_email(self,email):
        self.holder_email = email
        temp = f"Holder's email set to {self.holder_email}"
        return temp

    def get_balance(self):
        return self.balance

    def deposit(self,amount:int):
        self.balance += amount
        temp = f"New balance: {self.balance} USD"
        return temp
```

# Proof
![Screen Shot 2023-02-06 at 20 39 49](https://user-images.githubusercontent.com/112055140/216965301-b233beab-f139-4f5e-996f-d634680680ac.png)
 

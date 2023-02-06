# Task

An Accounting form needs a software package to calculate compound interest. Draw the UML diagram.

# Program
```.py
class CompoundInterest:
    def __init__(self,principal:str,rate:int,number_of_years:int):
        self.principal = principal
        self.rate = rate
        self.number_of_years = number_of_years

    def calculate(self):
        compound_interest = self.principal*(1+self.rate)**self.number_of_years
        return f"[CompoundInterest class]{self.principal}*(1+{self.rate})**{self.number_of_years} = {compound_interest}"

a = CompoundInterest(10,0.2,3)
print(a.calculate())

class AccountingProgram:
    def __init__(self):
        self.data = CompoundInterest(Principal=0,rate=0,year=0)

    def compound_interest_calculator(self):
        compound_interest = self.principal * (1 + self.rate) ** self.number_of_years
        return compound_interest
```

# UML Diagram
![IMG_4381](https://user-images.githubusercontent.com/112055140/216822109-c4926d5e-0600-4fb2-aeda-a3693273b87e.jpg)

# Proof
![Screen Shot 2023-02-06 at 20 54 43](https://user-images.githubusercontent.com/112055140/216965683-67d9fa39-2aa5-4628-ae3f-e96d64658a8f.png)

# Task

Create a new Python function called to_roman(num) that takes a single integer as input. It returns a string representing the Roman numeral equivalent of the input number.
Conditions: The function should only work for integers below 100, if the input is greater than 100, raise a ValueError with a message indicating that the input must be less than or equal to 100.

## Program

### Code:
```.py
def to_roman(input:int)->str:
    if input <= 100:
        roman_output = ""
        if input == 100:
            roman_output = "C"
            input = 0
        if input >= 90:
            roman_output += "XC"
            input -= 90
        if input >= 50:
            roman_output += "L"
            input -= 50
        if input >= 40:
            roman_output += "XL"
            input -= 40
        if input >= 10:
            roman_output += "X" * (input // 10)
            input %= 10
        if input >= 9:
            roman_output += "IX"
            input -= 9
        if input >= 5:
            roman_output += "V"
            input -= 5
        if input >= 4:
            roman_output += "IV"
            input -= 4
        if input >= 1:
            roman_output += "I" * input
        return roman_output
    else:
        raise ValueError("Error: Input must not be over 100")
```

### Proof: 
Input:1,5,10,11,50,51,70,71,100 | Output: I,V,X,XI,L,LI,LXX,LXXI,C
<img width="1047" alt="Screen Shot 2023-01-19 at 22 17 54" src="https://user-images.githubusercontent.com/112055140/213452909-28d9e261-f04d-483d-8428-bc1946c55287.png">

Input:101 | Output: Error: "Input must not be over 100"
<img width="1047" alt="Screen Shot 2023-01-19 at 22 17 54" src="https://user-images.githubusercontent.com/112055140/213453062-6adb07de-cf0b-4ba4-ac1d-e57a15372ccf.png">

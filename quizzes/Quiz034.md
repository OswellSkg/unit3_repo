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

### Proof
![Screen Shot 2023-02-06 at 20 45 29](https://user-images.githubusercontent.com/112055140/216965160-9b26c639-2156-4be3-bedf-98a4b95e64b8.png)


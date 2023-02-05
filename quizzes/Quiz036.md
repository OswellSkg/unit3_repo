# Task

SL: ① Create the classes described below ② UML diagram.

There is a Person class with two attributes, name and age, and two methods get_name() and get_age(). 
The attributes are initialized in the constructor method __init__(), and the methods are used to retrieve the values of the attributes. 
There is another class called Student which inherits from the Person class. It has a unique attribute grade and method get_grade().

# Program

```.py
import pytest

class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def get_name(self):
        if not isinstance(self.name, str):
            raise ValueError("Name must be in letters")
        return self.name

    def get_age(self):
        if not isinstance(self.age, int):
            raise ValueError("Age must be in integers")
        return self.age


class Student(Person):
    def __init__(self,name,age,grade):
        super().__init__(name,age)
        self.name = name
        self.age = age
        self.grade = grade
    def get_grade(self):
        return self.grade
```

# UML Diagram

![IMG_4380](https://user-images.githubusercontent.com/112055140/216819273-1ca7f495-fdc5-43d3-9ff0-765c5c907028.jpg)

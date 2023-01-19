# Task
Help a business man find a major city in Japan and the distance in-between.

## Program
### Code:
```.py
import random

class coordinate:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __repr__(self)->str:
        return f"[Coordinate Object] x:{self.x}, y:{self.y}"

class city:
    def __init__(self,name:str, location:coordinate):
        self.name = name
        self.location = location

    def __repr__(self)->str:
        return f"[City Object] City {self.name} is located at {self.location}"

    def distance(self, cityB):
        # if isinstance(cityB, city):
        xa, ya = self.location.x, self.location.y
        xb, yb = cityB.location.x, cityB.location.y
        # else:
        #     raise TypeError("Input should be an object of the class city")
        d = ((xa-xb)**2 + (ya-yb)**2 )**(1/2)
        return round(d,2)

class country:
    def __init__(self, name:str):
        self.name = name
        self.cities = []

    def add_city(self, new_city:city):
        self.cities.append(new_city)

    def __repr__(self):
        return f"[Country object] Country {self.name} with {len(self.cities)} cities"



point1 = coordinate(x=5, y=5)
print(point1)
tokyo = city(name="tokyo", location=point1)
kyoto= city(name="kyoto", location=coordinate(x=10, y=10))
Japan = country(name="Japan")


for name in ["Tokyo", "Yokohama", "Osaka", "Nagoya", "Sapporo", "Kobe", "Kyoto", "Fukuoka", "Kawasaki", "Saitama"]:
    rand_loc = coordinate(x=random.randint(0,100), y=random.randint(0,100))
    ct = city(name=name, location=rand_loc)
    Japan.add_city(ct)

#Homework
for city_no in range(0,9):
    print(f"Distance from {Japan.cities[0].name} to {Japan.cities[city_no].name} is {Japan.cities[0].distance(Japan.cities[city_no])}")
```

### Proof: 
Input: 

for city_no in range(0,9):
    print(f"Distance from {Japan.cities[0].name} to {Japan.cities[city_no].name} is {Japan.cities[0].distance(Japan.cities[city_no])}")

Output: 

Distance from Tokyo to Tokyo is 0.0
Distance from Tokyo to Yokohama is 72.11
Distance from Tokyo to Osaka is 49.01
Distance from Tokyo to Nagoya is 52.63
Distance from Tokyo to Sapporo is 91.22
Distance from Tokyo to Kobe is 93.41
Distance from Tokyo to Kyoto is 66.04
Distance from Tokyo to Fukuoka is 45.34
Distance from Tokyo to Kawasaki is 72.2

<img width="1047" alt="Screen Shot 2023-01-19 at 22 30 47" src="https://user-images.githubusercontent.com/112055140/213455371-065cf98f-dd83-4e7b-b0b1-9d54b1923f69.png">

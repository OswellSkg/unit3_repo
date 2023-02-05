# Task
Create a program that creates the SalemanMap using your OOP code.

# Program

```.py
import random
import matplotlib.pyplot as plt

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


for city_no in range(0,9):
    plt.scatter(Japan.cities[city_no].location.x, Japan.cities[city_no].location.y, marker="o", s=100)
    plt.text(Japan.cities[city_no].location.x+0.5, Japan.cities[city_no].location.y+1,Japan.cities[city_no].name)

# total_distance = 0
#
# for i in range(0,len(Japan.cities)-1):
#     departure_city = Japan.cities[i]
#     arrival_city = Japan.cities[i+1]
#     x = [departure_city.location.x, arrival_city.location.x]
#     y = [departure_city.location.y, arrival_city.location.y]
#     plt.plot(x,y,color="pink")
#     print(f"Connecting city {departure_city.name} to {arrival_city.name} | Distance:{departure_city.distance(arrival_city)}km")
#     total_distance += departure_city.distance(arrival_city)
#
# print(f"The total distance for this solution of the salesman's problem is {total_distance}.")

plt.title("Coordinates of Major cities in Tokyo")
plt.xlabel("Latitude(m)")
plt.ylabel("longitude(m)")
plt.show()
```

# Proof: 
![Screen Shot 2023-02-05 at 22 13 21](https://user-images.githubusercontent.com/112055140/216821002-fecee4f9-afec-496d-9951-6584b05ed7d2.png)

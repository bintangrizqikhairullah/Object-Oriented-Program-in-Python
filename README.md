# Object-Oriented-Program-in-Python

Object oriented program (OOP) is one of programming paradigms that can be used to approach or solving problem in python. It has advantage in term of reusability, data hiding and readability of the code than other programming paradigms. OOP is a type of program that oriented or focused around an object. In this article, we will inspect further the basics of OOP and its application.
To create an OOP, first we define a class that act as a blueprint of an object then we can assign it to an object, the class contains attributes and method that encapsulates the behavior of an object.
Syntax:

class car:
    attribute
    color="red"
    type="SUV"
    method
    def driving(self):
        print("This car is driving")
create an object mobil_sedan
mobil=car()
access atribute
print(mobil_sedan.color)
use the method of the class
mobil.driving()
output:

red
This car is driving

In the syntax above, we created a class called car which have two attributes which is ‘color’ and ‘type’, and a method ‘driving()’ to print the information about the car . The attribute can be analogized as the characteristic of an object for example, the color of a cat, the height of someone while the method can be analogized as the action of an object for example, a cat walks and a bird flies. Usually, attribute of an object is initialized by using the method __init__, the syntax to use __init__ is shown below:
Syntax:
class car:
    #innit fuction
    def __init__(self,color,type):
        self.color=color
        self.type=type
    def driving(self):
        print("This car is driving")

#create two object
mobil_sedan=car("hitam","sedan")
mobil_suv=car("putih","sedan")

#check the object
print(mobil_sedan.color)
print(mobil_suv.color)
output:
hitam
putih
The__init_ methods works as a constructor which is tasked to assign values to the data member of the class when an object of the class is created. __init__ is an example of Magic methods or Dunder method in python. The characteristics of magic method is their name always begins and ends with double underscore (__). Besides __init__, there are myriads of magic method that can be used to develop OOP, we are going to discuss some of them below:
1. __dict__ 	
This method returns a dictionary containing attributes and its value of an object.
Syntax:
mobil_sedan.__dict__
Output:
{'color': 'hitam', 'type': 'sedan'}
2.__len__ 
This method returns the length of a value.
Syntax:
mobil_sedan.color.__len__()
Output
5
3.__add__
This methods adds two object and returns a new object as a resultant.
Syntax:
class car:
    #innit fuction
    def __init__(self,color):
        self.color=color
    #add function
    def __add__(self,car2):
        return car(self.color+car2.color)

mobil_sedan=car("hitam")
mobile_suv=car("merah")
#create a new object 
mobil_gabung=mobil_sedan+mobil_suv
print(mobil_gabung.color)
Output:
hitamputih
The example above are only a tiny friction of dunder methods that can be used in developing OOP, other method that not described above can be checked in this link https://docs.python.org/3/reference/datamodel.html 
There are several principles that works in OOP which is 
•	encapsulation 
•	inheritance 
•	polymorphism, 
we are going to dive into these principles further

1.Encapsulations
Encapsulation is a method to make a variable or attribute  in OOP becomes hidden by turning it into a hidden attribute to prevent it from being changed accidentally. 
Syntax:
class racing_car():
    def __init__(self):
        print("The racing car is created")
    type="supercar"
    __price=1000

    def price(self):
        print(f"this car's price is {self.__price}")
        
lamborghini=racing_car()
lamborghini.__price
Output:
The racing car is created
---------------------------------------------------------------------------
AttributeError                            Traceback (most recent call last)
Cell In[18], line 11
      8         print(f"this car's price is {self.__price}")
     10 lamborghini=racing_car()
---> 11 lamborghini.__price

AttributeError: 'racing_car' object has no attribute '__price'

In the example above, the car class has private attribute “__price”, the private attribute of a class can be created by using double underscore at the start of the attribute’s name. The private attribute cannot be called outside of the class and will caused an error if called, the only way to call it is by creating a method that uses the private attribute. Private attribute can only be used inside the class itself.
Syntax:
class racing_car():
    def __init__(self):
        print("The racing car is created")
    type="supercar"
    __price=1000

    def price(self):
        print(f"this car's price is {self.__price}")
        
lamborghini=racing_car()
lamborghini.price()
Output:
The racing car is created
this car's price is 1000
2.Inheritance
Inheritance in OOP allows us to define a class that inherits all the method and properties from another class. Parent class is the class that being inherited and child class is the one who inherits it
#Parent class
class car:
    def __init__(self):
        print("car created")
    def driving(self):
        print("this car is driving")
    def stop(self):
        print("this car is stopping")
        
#children class
class suv(car):
    def __init__(self):
        super().__init__()
        print("suv created")
    def driving(self):
        print("this suv is driving")
    def drift(self):
        print("this suv is drifting")

car_suv=suv()
car_suv.stop()
car_suv.driving()
car_suv.drift()

Output:
car created
suv created
this car is stopping
this suv is driving
this suv is drifting
In this example we create two classes, the car class is the parent class and the suv class is the children class. The suv class inherits the method from the car class, it is shown that the suv can use the stop()
3.Polymophism
Polymorphism in OOP means that function with same name can be used in various object
Syntax:
class racing_car:
    def driving(self):
        print("this car driving")

class bus:
    def driving(self):
        print("this bus is driving")

object_car=racing_car()
object__bus=bus()

for i in [object__bus,object_car]:
    i.driving()
Output:
this bus is driving
this car driving
From the sytax above, it can be seen that the class racing_car and bus have function with the same name. It is also shown that when we create a loop to iterates through the list of objects, the method “driving()” can be called without concerning which class the object is


CONCLUSION
OOP in python is very useful because of it’s readability and reusability. The use of OOP is still relevant and frequent until this day.

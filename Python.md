--object oriented design[https://realpython.com/python3-object-oriented-programming/]


```py

print("Hello world")

class Dog:
    species = "Canis familiaris"

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __str__(self):
        return f"{self.name} is {self.age} years old"

    def speak(self, sound):
        return f"{self.name} barks {sound}"
        
class JackRussellTerrier(Dog):
    def speak(self, sound="Arf"):
        ##return f"{self.name} says {sound}"
        return super().speak(sound)
class Dachshund(Dog):
    pass

class Bulldog(Dog):
    pass

miles = JackRussellTerrier("Miles", 4)
buddy = Dachshund("Buddy", 9)
jack = Bulldog("Jack", 3)
jim = Bulldog("Jim", 5)



miles = JackRussellTerrier("Miles", 4)

print(miles.speak())
print(miles.speak("gaurav"))

'''

output
```py
Hello world
Miles barks Arf
Miles barks gaurav


```
1. [https://realpython.com/python-classes/#special-methods-and-protocols]
2. super() function[https://realpython.com/python-super/]
3. decorators [https://realpython.com/primer-on-python-decorators/]
4. default arguments [https://www.geeksforgeeks.org/default-arguments-in-python/]

```py
Example 1:

def do_twice(func):
    print("do_twice")
    def wrapper_do_twice(*args, **kwargs):
        func(*args, **kwargs)
        print("ha")
        #return func(*args, **kwargs)
    print("ha1")
    return wrapper_do_twice


@do_twice
def return_greeting(name):
    print("Creating greeting")
    return f"Hi {name}"
    
print(return_greeting("Adam"))    

output:
do_twice
ha1
Creating greeting
ha
None

Example 2:
def do_twice(func):
    print("do_twice")
    def wrapper_do_twice(*args, **kwargs):
        func(*args, **kwargs)
        print("ha")
        return func(*args, **kwargs)
    print("ha1")
    return wrapper_do_twice


@do_twice
def return_greeting(name):
    print("Creating greeting")
    return f"Hi {name}"
    
return_greeting("Adam")


ouput:
do_twice
ha1
Creating greeting
ha
Creating greeting
>

example 3:

def do_twice(func):
    print("do_twice")
    def wrapper_do_twice(*args, **kwargs):
        func(*args, **kwargs)
        print("ha")
        return func(*args, **kwargs)
    print("ha1")
    return wrapper_do_twice


@do_twice
def return_greeting(name):
    print("Creating greeting")
    return f"Hi {name}"
    
print(return_greeting("Adam"))


ouutput:
do_twice
ha1
Creating greeting
ha
Creating greeting
Hi Adam
```


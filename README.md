# oopweek-5
**Create a class representing anything you like (a Smartphone, Book, or even a Superhero!).
Add attributes and methods to bring the class to life!
Use constructors to initialize each object with unique values.
Add an inheritance layer to explore polymorphism or encapsulation.**
# Base class: Hero
class Hero:
    def __init__(self, name, power, weakness):
        self.name = name  # Public attribute
        self.__power = power  # Private attribute (encapsulation)
        self.__weakness = weakness  # Private attribute (encapsulation)
    
    # Public method to interact with private attributes
    def get_power(self):
        return self.__power
    
    def set_power(self, power):
        if power != "":
            self.__power = power
    
    def get_weakness(self):
        return self.__weakness
    
    def set_weakness(self, weakness):
        if weakness != "":
            self.__weakness = weakness
    
    # Method to describe the hero
    def describe(self):
        return f"{self.name} has the power of {self.__power} but is weak to {self.__weakness}."

# Subclass: Superhero, inheriting from Hero
class Superhero(Hero):
    def __init__(self, name, power, weakness, secret_identity):
        super().__init__(name, power, weakness)  # Calling the constructor of the parent class
        self.secret_identity = secret_identity  # Additional attribute for superheroes

    # Overriding the describe method to add more details (Polymorphism)
    def describe(self):
        basic_info = super().describe()  # Get description from parent class
        return f"{basic_info} Their secret identity is {self.secret_identity}."

    # Additional method specific to Superhero
    def use_power(self):
        print(f"{self.name} is using their {self.get_power()}!")

# Create Hero and Superhero objects
hero = Hero("Normal Man", "Strength", "Kryptonite")
superhero = Superhero("SuperMan", "Super Strength", "Kryptonite", "Clark Kent")

# Test: Display descriptions
print(hero.describe())  # Using the base Hero class
print(superhero.describe())  # Using the Superhero class (Polymorphism)
superhero.use_power()  # Superhero specific action

****Activity 2: Polymorphism Challenge! 🎭

Create a program that includes animals or vehicles with the same action (like move()). However, make each class define move() differently (for example, Car.move() prints "Driving" 🚗, while Plane.move() prints "Flying" ✈️).**

# Base class: Animal
class Animal:
    def __init__(self, name):
        self.name = name

    def move(self):
        # Default behavior for Animal (could be overridden in subclasses)
        print(f"{self.name} is moving.")

# Subclass: Dog (inherits from Animal)
class Dog(Animal):
    def __init__(self, name):
        super().__init__(name)

    def move(self):
        print(f"{self.name} is running! 🐕")

# Subclass: Fish (inherits from Animal)
class Fish(Animal):
    def __init__(self, name):
        super().__init__(name)

    def move(self):
        print(f"{self.name} is swimming! 🐟")

# Base class: Vehicle
class Vehicle:
    def __init__(self, make):
        self.make = make

    def move(self):
        # Default behavior for Vehicle (could be overridden in subclasses)
        print(f"{self.make} is moving.")

# Subclass: Car (inherits from Vehicle)
class Car(Vehicle):
    def __init__(self, make):
        super().__init__(make)

    def move(self):
        print(f"{self.make} is driving 🚗")

# Subclass: Plane (inherits from Vehicle)
class Plane(Vehicle):
    def __init__(self, make):
        super().__init__(make)

    def move(self):
        print(f"{self.make} is flying ✈️")

# Creating objects
dog = Dog("Buddy")
fish = Fish("Goldie")
car = Car("Toyota")
plane = Plane("Boeing")

# Demonstrating polymorphism
animals = [dog, fish]
vehicles = [car, plane]

# Call move() method on each animal and vehicle
for animal in animals:
    animal.move()  # Each animal has its own version of move()

for vehicle in vehicles:
    vehicle.move()  # Each vehicle has its own version of move()

**

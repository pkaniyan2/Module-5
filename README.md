
# # Constructors in Python: Welcome Message with Student Name

## 🎯 Aim
To write a Python program that creates a **Student** class with a **default constructor** and a method to display a welcome message along with the student’s name provided by the user.

## 🧠 Algorithm
1. **Get user input**: Accept the student's name from the user.
2. **Define the class**: Create a class `Student` with a default constructor (`__init__`).
3. **Default Constructor**: In the constructor, assign the user input (student name) to an instance variable `self.a`.
4. **Display Message**: Define a method `show` that prints "This is non-parameterized constructor" and a welcome message with the student’s name.
5. **Execute the Program**: Instantiate the `Student` class and call the `show` method.

## 🧾 Program
```
# Get user input
name = input("Enter student name: ")

# Define the class
class Student:
    # Default constructor
    def __init__(self):
        self.a = name   # assign input to instance variable

    # Method to display message
    def show(self):
        print("This is non-parameterized constructor")
        print("Welcome", self.a)

# Create object
s = Student()

# Call method
s.show()
```


## Output
<img width="691" height="359" alt="image" src="https://github.com/user-attachments/assets/1df0ce4c-939a-471f-96aa-3d7ef7a90fef" />

## Result
The program was executed successfully. A Student class with a default (non-parameterized) constructor was created, and it correctly displayed a welcome message using the user-provided name.



# Destructor in Python

This project demonstrates how to implement a **destructor** in Python using a simple class.

## 🚀 Overview

The program defines a class `Demo` with:

- A **constructor** `__init__` that initializes an instance variable and prints a message.
- A **destructor** `__del__` that prints a message when the object is destroyed.

## 🧠 Algorithm

1. Define a class named `Demo`.
2. Inside the class, define the `__init__` method:
   - Initialize an instance variable `status` with the value `"Alive"`.
   - Print the value of `status`.
3. Define the `__del__` method:
   - Print a message indicating the object is being destroyed.
4. Outside the class:
   - Create an instance of the `Demo` class.
   - Delete the object using the `del` keyword.
## Program
```
class Demo:
    def __init__(self):
        print("Alive")
    def __del__(self):
        print("The object no longer exists")
obj=Demo()
del obj
```
## 🧪 Output
<img width="702" height="186" alt="image" src="https://github.com/user-attachments/assets/b7a5e967-76ac-4928-9641-fa6e12a5d2b8" />

## Result
This project demonstrates how to implement a destructor in Python using a simple class is executed sucessfully.



# Hierarchical Inheritance in Python

This Python project demonstrates **Hierarchical Inheritance** using a base class `Details` and two derived classes `Employee` and `Patient`. The program collects and displays details for both employees and patients.

## 🎯 Aim

To write a Python program that uses **Hierarchical Inheritance** to input and display **Employee** and **Patient** details.

## 📘 Description

- **Base Class:** `Details`
  - Stores common attributes: `name`, `age`
  - Provides methods: `getName()`, `getAge()`

- **Derived Class 1:** `Employee`
  - Inherits from `Details`
  - Adds: `employee_id`, `department`
  - Method: `getEmployeeDetails()`

- **Derived Class 2:** `Patient`
  - Inherits from `Details`
  - Adds: `patient_id`, `disease`
  - Method: `getPatientDetails()`

## 🧠 Algorithm

1. Create base class `Details` with common attributes.
2. Create `Employee` class extending `Details`, adding employee-specific data.
3. Create `Patient` class extending `Details`, adding patient-specific data.
4. Get user input for employee and patient data.
5. Display collected information using class methods.

## Program
```

class Details:
    def __init__(self):
        self.__id="<No Id>"
        self.__name="<No Name>"
        self.__gender="<No Gender>"
    def setData(self,id,name,gender):
        self.__id=id
        self.__name=name
        self.__gender=gender
    def showData(self):
        print("Id: ",self.__id)
        print("Name: ", self.__name)
        print("Gender: ", self.__gender)

class Employee(Details): #Inheritance
    def __init__(self):
        self.__company="<No Company>"
        self.__dept="<No Dept>"
    def setEmployee(self,id,name,gender,comp,dept):
        self.setData(id,name,gender)
        self.__company=comp
        self.__dept=dept
    def showEmployee(self):
        self.showData()
        print("Hospital: ", self.__company)
        print("Department: ", self.__dept)

class Patient(Details): #Inheritance
    def __init__(self):
        self.__hospital="<No Hospital>"
        self.__dept="<No Dept>"
    def setEmployee(self,id,name,gender,hos,dept):
        self.setData(id,name,gender)
        self.__hospital=hos
        self.__dept=dept
    def showEmployee(self):
        self.showData()
        print("Hospital: ", self.__hospital)
        print("Department: ", self.__dept)

id=int(input())
name=input()
gender=input()
comp=input()
dept=input()
id1=int(input())
nam=input()
gen=input()
hosp=input()
dep=input()

print("Doctor Object")
e=Employee()
e.setEmployee(id,name,gender,comp,dept)
e.showEmployee()
print("\nPatient Object")
d = Patient()
d.setEmployee(id1, nam, gen, hosp, dep)
d.showEmployee()
```
## Sample Output
<img width="1257" height="529" alt="image" src="https://github.com/user-attachments/assets/6f82e046-33a6-4796-85f9-9d67258da104" />

## Result
Thus the program that uses Hierarchical Inheritance to input and display Employee and Patient details hase been executed successfully.



# Multilevel Inheritance Example in Python

This Python project demonstrates the concept of **Multilevel Inheritance** to collect and display the **name**, **age**, and **location** of a person.

## 🎯 Aim

To write a Python program that uses multilevel inheritance to get and display a person’s name, age, and location.

## 🧠 Algorithm

1. **Parent Class**  
   - `__init__(name)` initializes the `name` attribute.  
   - `getName()` returns the `name`.

2. **Child Class (inherits Parent)**  
   - `__init__(name, age)` initializes `name` using `super()` and adds `age`.  
   - `getAge()` returns the `age`.

3. **Grandchild Class (inherits Child)**  
   - `__init__(name, age, location)` initializes `name` and `age` using `super()` and adds `location`.  
   - `getLocation()` returns the `location`.

4. **Input & Output**  
   - Take user input for name, age, and location.  
   - Create an instance of `Grandchild`.  
   - Print all details using class methods.

## Program
```
class Parent:
   def __init__(self,name):
     self.name = name
   def getName(self):
     return self.name

class Child(Parent):
   def __init__(self,name,age):
     Parent.__init__(self,name)
     self.age = age
   def getAge(self):
     return self.age

class Grandchild(Child):
   def __init__(self,name,age,location):
     Child.__init__(self,name,age)
     self.location=location
   def getLocation(self):
     return self.location

name=input()
age=int(input())
loc=input()
gc = Grandchild(name,age,loc)
print(gc.getName(), gc.getAge(), gc.getLocation())
```

## Sample Output
<img width="1255" height="244" alt="image" src="https://github.com/user-attachments/assets/aca06801-6852-4740-bb94-90232269792e" />
## Result
Thus the program that uses multilevel inheritance to get and display a person’s name, age, and location executed successfully.



# Arithmetic Operations Using Multiple Inheritance in Python

This Python program demonstrates **multiple inheritance** by performing basic arithmetic operations — Addition, Subtraction, and Division — using three classes.

## 🎯 Aim

To write a Python program to calculate **Add, Sub & Division** using **Multiple Inheritance**.

## 🧠 Algorithm

1. **Define `Calculation1` class**
   - Contains `Summation(a, b)` method to return the sum of two numbers.
2. **Define `Calculation2` class**
   - Contains `Subtraction(a, b)` method to return the difference of two numbers.
3. **Define `Derived` class**
   - Inherits from both `Calculation1` and `Calculation2`.
   - Contains `Division(a, b)` method to return the division result.
4. **Input**
   - Prompt the user to enter two numbers.
5. **Process**
   - Create an object of the `Derived` class.
   - Call `Summation`, `Subtraction`, and `Division` methods.
6. **Output**
   - Display the results of the three operations.

## 💻 Program 
```
class Calculation1:
    def Summation(self, a, b):
        return a + b

class Calculation2:
    def Subtraction(self, a, b):
        return a - b

class Derived(Calculation1, Calculation2):
    def Division(self, a, b):
        if b != 0:
            return a / b
        else:
            return "Error: Division by zero"

a = int(input())
b = int(input())
obj = Derived()

print(obj.Summation(a, b))
print(obj.Subtraction(a, b))
print(obj.Division(a, b))
```
## Output Example
<img width="1259" height="246" alt="image" src="https://github.com/user-attachments/assets/aa933a69-80d6-4671-a8fe-cf3ffc1b936a" />

## Result
Thus the program demonstrates multiple inheritance by performing basic arithmetic operations — Addition, Subtraction, and Division — using three classes has been executed successfully

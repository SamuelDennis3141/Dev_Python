```
import sys

# sets the user name
def name():
    first_name = input("What is your first name? ").lower().capitalize()
    last_name = input("What is your last name ").lower().capitalize()
    return first_name, last_name


# sets the age and verifies an integer is entered
def age_check():
    try:
        age = int(input("What is your age? "))
    except ValueError:
        print("That was not a type")
        age = age_check()
    return age


# asks the user for their address, verifying it is the correct length
def address_chk():
    address = input("What is your postcode? ")
    if 6 <= len(address) <= 7:
        pass
    else:
        print("That was not a valid address")
        address = address_chk()
    return address


# asks the user for their salary, converting to a float
def salary_chk():
    salary = float(input("What is your salary? "))
    return salary


# ensures that the individual is on the devops team
def course_chk():
    course = input("What is your course? ")
    if course.upper() == "DEVOPS":
        return course
    else:
        print("You are on the wrong course! Goodbye! ")
        sys.exit()


# complies all of the information and returns the desired result
def information():
    f_n, l_n = name()
    address = address_chk()
    salary = salary_chk()
    course = course_chk()
    age = age_check()
    print(f"Welcome {f_n} {l_n}. \n\nYour age is {age}, postcode is {address}, course is {course}, salary is {salary}."
          f"\n\nThe type of the address variable is {type(address)} \n"
f"The type of the salary is {type(salary)} \nThe type of the course is {type(course)})")


information()
sys.exit()  # system exit
```

# Test Driven Development

![image](https://user-images.githubusercontent.com/112982429/188755235-591b67ec-ed79-4515-ada0-7bfa370f5676.png)

### What is it?

 Test Driven Development (TDD) is a software development practice that focuses on creating unit
 test cases before developing the actual code. It is an iterative approach (AGILE) that combines
 programming, the creation of unit tests, and refactoring.

Tiny mistakes have big impacts so using a TDD approach can help prevent these errors at the source.

TDD allows us to express intent in the form of a test
1) Create the tests
2) Test the test by running and seeing it fail
   (Now we know it is testing something useful)
3) Create the minimum code to meet the needs of the test. Run it and see it pass.
4) Stable state or passing state, (refactor test and code for quality and generality)
5) Repeat

- Red, Green, Refractor

Unit testing is about testing
TDD is about design

### Benefits of TDD
- it works
- easy to read
- testable
- easy to change
- simple
- efficient


### Attributes of TDD
- Modular (broken down into smaller pieces)
- Loosely coupled (pieces are not tightly bound together)
- Cohesive (the pieces are closely related are physically close together)
- Separation of Concerns (each piece is focused on achieving one outcome)
- Information Hiding (deal with another part of the code without worrying about what is going on)

### How to use Pytest

- pip install pytest
- call `pytest "filename"` in terminal

### Example
#### Test file
```python
import unittest
import pytest
from calc import SimpleCalc


class Caltests(unittest.TestCase):
    calc_obj = SimpleCalc()

    def test_add(self):
        self.assertEqual(self.calc_obj.add(2,2), 4)

    def test_add_float(self):
        self.assertEqual(self.calc_obj.add(2.2, 4.6), 6.8)

    def test_multiply(self):
        self.assertEqual(self.calc_obj.multiply(4,3), 12)

    def test_multiply_float(self):
        self.assertEqual(self.calc_obj.multiply(5,3.5), 17.5)

    def test_divide(self):
        self.assertEqual(self.calc_obj.divide(8,4), 2)

    def test_divide_float(self):
        self.assertEqual(self.calc_obj.divide(10,2.5), 4)

    def test_divide_zero(self):
        self.assertEqual(self.calc_obj.divide(8,0), "division by zero is not allowed")

    def test_subtract(self):
        self.assertEqual(self.calc_obj.subtract(3,4), -1)

    def test_percentage(self):
        self.assertEqual(self.calc_obj.percentage(1,10), "10.0%")

    def test_percentage_neg(self):
        self.assertEqual(self.calc_obj.percentage(-5,15), "-33.3%")

    def test_percentage_zero(self):
        self.assertEqual(self.calc_obj.percentage(10,0), "division by zero is not allowed")

    def test_dob(self):
        self.assertEqual(self.calc_obj.dob(31,10), "31/10")

    def test_dob_outofrange(self):
        self.assertEqual(self.calc_obj.dob(-1,10), "Date is out of bounds")

    def test_dob_feb_31(self):
        self.assertEqual(self.calc_obj.dob(31,2), "Date is out of bounds")

    def test_cm_to_m(self):
        self.assertEqual(self.calc_obj.cm_m(100), 1.00)


```
#### Function file
```python
class SimpleCalc:

    def add(self, value1, value2):
        return value1 + value2

    def subtract(self, value1, value2):
        return value1 - value2

    def multiply(self, value1, value2):
        return value1 * value2

    def divide(self, value1, value2):
        if value2 == 0:
            return "division by zero is not allowed"
        return value1/value2

    def dob(self, day, month):
        days = {
            "1":31,
            "2":28,
            "3":31,
            "4":30,
            "5":31,
            "6":30,
            "7":31,
            "8":31,
            "9":30,
            "10":31,
            "11":30,
            "12":31
        }
        for i in days.keys():
            if i == str(month):
                if 1 <= day <= days[i]:
                    return f"{day}/{month}"
        else:
            return "Date is out of bounds"


    def percentage(self, value1, value2):
        if value2 == 0:
            return f"division by zero is not allowed"
        return f"{round(100 * value1 / value2,1)}%"

    def cm_m(self,centi):
        return round(centi/100, 2)


```

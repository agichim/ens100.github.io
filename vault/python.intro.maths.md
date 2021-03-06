---
id: fc96c616-e616-40cd-9afd-8592452ccbdf
title: Maths
desc: ''
updated: 1600794386238
created: 1600794386238
stub: false
---

## Operators - just like in normal maths although with a couple of nuances.

| Operator | Description	 | Example |
|----|----|----|----|
| +	| Addition	| 5+2 returns 7 |
| -	| Subtraction	| 5-2 returns 3 |
| *	| Multiplication	| 5*2 returns 10 |
| /	| Division	| 5/2 returns 2.5 |
| %	| Modulus	| 5%2 returns 1 |
| **	| Power	| 5**2 5 to the power of 2, returns 25 |
| //	| Floor Division | 5//2 returns 2 |

### Nuances:
- % finds the remainder of the calculation - for example `11 % 3 = 2`
- // is the same a a regular division but it rounds the number down - for example `11 // 3 = 3`
- Exercise - to divide various numbers can use the following
```python
def divide(num,den):
    remainder = num % den
    floor = num // den
    print(num, 'divided by', den, 'equals',
          floor,'with a remainder of', remainder)

def main():
    divide(4,2)
    divide(10,3)

main()
```
## Assignment Operators

- This allows you to change the assignment `a =`through math, for example:

| Operator	| Description	| Example | Same As|
|----|----|----|----|
| =	| Basic assignment	| a = 2 |
| +=	| addition and assignment	| a+=2 | a = a + 2 |
| -=	| subtraction and assignment	| a-=2 | a = a - 2 |
| *=	| multiplication and assignment	| a*=2 | a = a * 2 |
| /=	| division and assignment	| a/=2 | a = a / 2 |
| %=	| modulus and assignment	| a%=2 | a = a % 2 |
| **=	| exponent and assignment	| a**=2 | a = a**2 |
| //=	| floor division and assignment	| a//=2 | a = a // 2 |

- Order of operations is:
  - **
  - *, /, //, %
  - +, -
Like normal maths and can use parentheses to change the order of operations.

## Bulit-in Functions
### int(x)
  - When converting floats (decimals) `int(x)` will strip everything after the decimal. In essence rounding down for positive numbers and down for negatives.As example:
  - `int(5)` integer already - returns `5`
  - `int('5')` string - returns `5`
  - `int(5.9)`  float - returns `5`
  - `int(-5.9)` float - returns `-5`
  - `int('5.4')` string - returns `ValueError: invalid literal`

### eval(str)
  - Evaluates a string as a Python expression where you can do calculations to numbers wrapped in a string.
  - Both `int()` and `eval()` can be used to convert strings to numbers but `int()` has the advantage of being able to deal with leading 0 eg. 0100
### float(x)
  - Converts numbers into a float. For example
  -  `int(5)` integer - returns `5.0`

### abs(x)
  - returns the absolute value so -5 would become 5
### min() and max()
  - identical to Excel - returns the min or the max vlaue from the arguments
### pow(x,y[,z])
  - `pow(4,2)`is the same as doing `4**2`
  - If the z argument is present, pow(x,y,z) is functionally equivalent to (but supposedly more efficient than) x**y % z. `pow(4,2,3)` is the same as `4**2 % 3` but maybe quicker to write
### round(number[, n])
  - returns a rounded number to the n digit after the decimal
  - Same as Excel
### sum(iter[, start])
- Sum() function takes an iterable (e.g., a list) and adds up all of its elements.
- Again, same as excel.

## Math Module
This is built into Python and provides a number of additional math functions. Import into python by using `import math`. Some of the functions include:
- math.ceil(x) - `math.ceil(5.4)` = 6
- math.floor(x) - `math.floor(5.6)` = 5
- math.trunc(x) - `math.trunc(5.6)` = 5
- math.fabs(x) - `math.fabs(-5)` = 5.0
- math.factorial(x) - `math.factorial(3)` = 6
- math.fmod(x,y) - `math.fmod(5,2)` =1.0
- math.pow(x,y) - `math.pow(5,2)` = 25.0
- math.sqrt(x) - `math.sqrt(25)` = 5.0

### The math library offers many additional functions, including:
- Logarithmic functions (e.g., `math.log(x)`)
- Trigonometric functions (e.g., `math.sin(x)`)
- Angular conversion functions (e.g., `math.degrees(x)`)
- Hyperbolic functions (e.g., `math.sinh(x)`)
Full list and help - https://docs.python.org/3/library/math.html.

## Random Module

Import into python by using `import random`.  Some of the things it can do
- random.random() - `random.random()`
- random.randint(a,b) - `random.randint(1,10)`
- random.randrange(b) - `random.randrange(10)` = one of 0 through 9
- random.randrange(a,b) - `random.randrange(1,10)` = one of 1 through 9
- random.randrange(a,b,step) - `random.randrange(1,10,2)` = one of 1,3,5,7,9
- random.uniform(a,b) - `random.uniform(1,10)`
- random.choice(seq) - Sequences are covered later in the course.
- random.shuffle(seq) - Sequences are covered later in the course.

### Seeding
- `random.seed(a)` is used to initialize the random number generator. The value of a will determine how random numbers are selected
Full list and help - https://docs.python.org/3/library/random.html.

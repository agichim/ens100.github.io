---
id: 45f6ddb3-7cf1-4d0c-a9d7-0c2c9b95bee3
title: Getting Started
desc: ''
updated: 1599672750079
created: 1599672750079
stub: false
---

# Getting started

In Python there are literals such as "Hello" - this simply tell Python not to interpret anything but should just take it as it _literally_ is.

To add comments to code we use the # - this renders that line as moot. 

There are the following type of Data Types:

## Data Types

Use `type()` to find out

|----|----|----|----|
|----|----|----|----|
Data Type |	Abbreviation | Explanation
boolean |bool |	A True or False value.| 1==1
integer |int |	A whole number. | 3
float	| float	| A decimal. | 3.1
string	| str	| A sequence of Unicode* characters. | "pizza"
list	| list	| An ordered sequence of values. Like an array in other languages. | ['1' , '2', '3']
tuple	| tuple	| A list of fixed length. | ('1' , '2', '3')
dictionary |	dict	| An unordered grouping of key-value pairs.
set	| set	| An unordered grouping of values. | {'1' , '2', '3'}

## Variables

Variables in Python are untyped and do not need to be declared  simply assign a value to a variable and Python determines the type by the value assigned.

Variable names are case sensitive, meaning that `firstname` is different from `FirstName`. Variable names are written in lowercase and separated by underscores (e.g., home_address). Variable names must begin with a letter or an underscore and may contain only letters, digits, and underscores (although avoid for the time being).

Cannot use the following names as variable names as they have a special meaning:

* and
* as
* assert
* break
* class
* continue
* def
* del
* elif
* else
* except
* False
* finally
* for
* from
* global
* if
* import
* in
* is
* lambda
* None
* nonlocal
* not
* or
* pass
* raise
* return
* True
* try
* while
* with
* yield

### How to use Variables

1. Variable name.
2. Assignment operator.
3. Value assigned (This could be any data type)

![](/assets/images/2020-09-09-19-17-35.png)

As an example:
```Python
greeting = "Hello, world!"
print(greeting)
```

### Simultaneous Assignment

Assign several values at once, :
`smart_1, cute_1, funny_1, quiet_1 = "John","Paul","Ringo","George"`

Code Example:
```Python
#Switch b and a. Attempt 1. The Wrong Way.
a=5
b=10
a=b
b=a
print("ATTEMPT 1. The Wrong Way.")
print(a)
print(b)

#Switch b and a. Attempt 2. A Way that Works.
a=5
b=10
temp=a
a=b
b=temp
print("ATTEMPT 2. A Way that Works.")
print(a)
print(b)

#Switch b and a. Attempt 3. The Python Way.
a=5
b=10
a,b = b,a
print("ATTEMPT 3. The Python Way.")
print(a)
print(b)
```

### Constants

This is a variable in that it is an identifier that holds a value, but, unlike variables, constants are not variable, they are constant. 

Python doesn't really have constants, but as a convention, variables that are meant to act like constants (their values are not meant to be changed) are written in all **capital letters**. For example:

- PI = 3.141592653589793
- RED = "FF0000" #RGB value of red

### Deleting Variables

Variables can be deleted using the `del` statement:

```Python
a = 1
print(a) #prints 1
del a
print(a) #NameError: name 'a' is not defined
```
---
id: 0de9089e-707b-4dfb-98c5-3a7852f30499
title: Functions and Modules
desc: ''
updated: 1600794976505
created: 1600794976505
stub: false
---

# Functions and Modules

Local and global variables are important. Local overrides global unless you use the global overwriter. Will look first for local and then global, unless you use the function `global`

## Function Parameters
- this is adding something to the function like so `main(adding)`
- if wanting to set a default value we can do like so `main(name=default)`

## return
- we can use return sum when wanting to return the values of say a sum.
-  keyword used to return a value from a function

## import
- If have a function. Or , a module with a whole bunch of functions they you want to make available to other modules so you (and others ) could use, we can use the `import `keyword.
- When you import a module into another module, the code in the imported module will run. This might be undesirable. It's possible (and common) to wrap the call to the main() function (or any other code) in a condition so that it will only run if the module is executed directly (i.e., is not imported into another module)
- Can also use a more specific import `from module_name import function1, function2` this will only import the specific functions that have been imported.
- When you use this second approach, it is not necessary to prefix the module name when calling the function. However, it's possible to have naming conflicts, so be careful.
- Another option, which is helpful for modules with long names, is to create an alias for a module, so that you do not have to type its full name
```python
import add_nums_with_return as anwr
sum = anwr.add_nums(1,2,3,4,5)
```
- Files with a .pyc extension are compiled Python files. They are automatically created in a __pycache__ folder the first time a file is imported. These files are created so that modules you import don't have to be compiled every time they run. You can just leave those files alone. They will automatically be created/updated each time you import a module that is new or has been changed

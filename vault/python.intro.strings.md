---
id: fe90515e-2ec0-4c1d-aa6f-6547916da621
title: Strings
desc: ''
updated: 1601052971831
created: 1601052971831
---
# Strings with Python

## Escaping Characters

### New Lines

If for example have the sentence "The soldier asked, "Are you suggesting coconuts migrate?"" this this will return an error in Python due to the first " closing the argument

To fix this we need to use an escape character `\` before and after the quote - so for example:
`"The soldier said, \"You've got two empty halves of a coconut and you're bangin' 'em together.\""`

### Special Characters:

`\'`	Single quote
`\"`	Double quote
`\\`	Backslash
`\n`	Linefeed
`\t`	Horizontal tab

### Triple Quote

You can use triple quotes when you have a string of text with multiple line break, like a poem. By wrapping the text in triple """ it will print the text with the breaks.

## Indexing

Process of finding a specific element within a sequence of elements through the element's position. This is done by using the `phrase[]` argument.

If we consider the string from left to right, the first character (the left-most) is at position 0. If we consider the string from right to left, the first character (the right-most) is at position -1. 

```python
phrase = "Monty Python"

first_letter = phrase[0]
#[M]onty Python
print(first_letter)

last_letter = phrase[-1]
#Monty Pytho[n]
print(last_letter)

fifth_letter = phrase[4]
#Mont[y] Python
print(fifth_letter)

third_letter_from_end = phrase[-3]
#Monty Pyt[h]on
print(third_letter_from_end)
```

## Slicing Strings

To get a sequence of characters from a string (i.e., a substring)

`substring = original_string[first_pos:last_pos]`

This returns a slice that starts with the character at first_pos and includes all the characters up to but not including the character at last_pos.

- If first_pos is left out, then it is assumed to be 0. So "hello"[:3] would return `hel`.

- If last_pos is left out, then it is assumed to be the length of the string, or in other words, one more than the last position of the string. So "hello"[3:] would return `lo`

```python
phrase = "Monty Python"

first_5_letters = phrase[0:5]
#[Monty] Python
print(first_5_letters)

letters_2_thru_4 = phrase[1:4]
#M[ont]y Python
print(letters_2_thru_4)

letter_5_to_end = phrase[4:]
#Mont[y Python]
print(letter_5_to_end)

last_3_letters = phrase[-3:]
#Monty Pyt[hon]
print(last_3_letters)

first_3_letters = phrase[:3]
#[Mon]ty Python
print(first_3_letters)

three_letters_before_last = phrase[-4:-1]
#Monty Py[tho]n
print(three_letters_before_last)

copy_of_string = phrase[:]
#[Monty Python]
print(copy_of_string)
```





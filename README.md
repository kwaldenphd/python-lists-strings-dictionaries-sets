# Combined Lists and Strings, Dictionaries and Sets Python lab

# Lists and Strings in Python

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

## Lab Objectives
- Practice utilizing lists and strings in the Python programming language
  * For strings, this includes creation, length and access, basic list operations, and basic method arguments
  * For lists, this includes creation, access, iteration, nesting, searching, concatenating, growing, deleting, sorting, and reversing
- Understand and articulate the differences between lists and strings
- Use Python methods and functions to work with strings and numbers
- - Define dictionaries in the Python programming language
- Practice utilizing dictionaries and sets in the Python programming language
  * For dictionaries, this includes basic syntax, ordering, adding key-value pairs, updating, lists, and iteration
  * For sets, this includes basic syntax, adding and removing, and testing for membership
- Use Python methods and functions to work with dictionaries and sets

## Acknowledgements

Elements of this lab procedure were adapted from materials developed by [Dr. Peter Bui](http://www3.nd.edu/~pbui/) for the [CSE 10101 "Elements of Computing I" course](https://www3.nd.edu/~pbui/teaching/cdt.30010.fa16/).
- [Reading 05: Lists, Strings](https://www3.nd.edu/~pbui/teaching/cdt.30010.fa16/reading05.html)
- [Notebook 05: Lists, Strings](https://www3.nd.edu/~pbui/teaching/cdt.30010.fa16/notebook05.html)
- [Reading 06: Dictionaries, Sets](https://www3.nd.edu/~pbui/teaching/cdt.30010.fa16/reading06.html)

Elements of this lab procedure were adapted from materials developed by [Dr. Janet Davis](https://cs.whitman.edu/~davisj/) for the the [CSC 105 "The Digital Age" course](https://www.cs.grinnell.edu/~davisjan/csc/105/2012S/). 
- [Laboratory: Programming in Python](http://www.cs.grinnell.edu/~davisjan/csc/105/labs/python1.html)

Elements of this lab procedure were adapted from materials developed by [Dr. Corey Pennycuff](https://www3.nd.edu/~cpennycu/) for the [CSE 10101 Elements of Computing (Fall 2019)](https://www3.nd.edu/~cpennycu/2019/fa-CSE10101-CDT30010.html).

Elements of this lab procedure were adapted from materials developed by [Lindsay K. Mattock](http://lindsaymattock.net/) for the the [SLIS 5020 Computing Foundations course](http://lindsaymattock.net/computingfoundations.html). 

# Table of Contents
- [Python Syntax: Methods and Functions](#python-syntax-methods-and-functions)
- [Variables](#variables)
- [Strings](#strings)
  * [Title Methods](#title-methods)
  * [Concatenation](#concatenation)
  * [Combining Variable Types](#combining-variable-types)
  * [String Length and Access](#string-length-and-access)
  * [Other String Operations](#other-string-operations)
    * [Length](#length)
    * [Properties](#properties)
    * [Sort](#sort)
    * [Max and Min](#max-and-min)
    * [`in` operator](#in-operator)
    * [Search](#search)
- [Lists](#lists)
  * [Lists With Numbers](#lists-with-numbers)
    * [List Length and Access](#list-length-and-access)
    * [Modifying Lists](#modifying-lists)
      * [Growing Lists](#growing-lists)
      * [A Quick Detour Into `range()`](#a-quick-detour-into-range)
      * [Deleting Items From Lists](#deleting-items-from-lists)
    * [Empty Lists](#empty-lists)
    * [Nesting and Sub-Lists](#nesting-and-sublists)
    * [Other List Operations](#other-list-operations)
      * [Lists and the `in` Operator](#lists-and-the-in-operator)
      * [List Concatenation](#list-concatenation)
      * [Copying](#copying)
      * [Sorting](#sorting)
        * [Reverse](#reverse)
      * [Utility Functions](#utility-functions)
    * [Looking Ahead](#looking-ahead)
    * [Lab Notebook Questions on Lists With Numbers](#lab-notebook-questions-on-lists-with-numbers)
  * [Lists With Strings](#lists-with-strings)
    * [List Functions and String Elements](#list-functions-and-string-elements)
      * [`Len`](#len)
      * [`Sort`](#sort)
      * [`Reverse`](#reverse)
    * [Lab Notebook Questions on Lists With Strings](#lab-notebook-questions-on-lists-with-strings)
- [Dictionaries](#dictionaries)
  * [Creating a Dictionary](#creating-a-dictionary)
  * [Interacting With a Dictionary](#interacting-with-a-dictionary)
  * [Iteration and Dictionaries](#iteration-and-dictionaries)
  * [Dictionary Lab Notebook Question](#dictionary-lab-notebook-question)
- [Sets](#sets)
  * [Creating Sets](#creating-sets)
  * [Testing For Membership](#testing-for-membership)
  * [Adding and Removing Items](#adding-and-removing-items)
  * [Set Lab Notebook Question](#set-lab-notebook-question)
- [Additional Lab Notebook Questions](#additional-lab-notebook-questions)
- [How to submit this lab (and show your work)](#how-to-submit-this-lab-and-show-your-work)
- [Lab Notebook Questions](#lab-notebook-questions)
  
# Python Syntax: Methods and Functions

1. Python has some specific terminology used to describe elements of code.

2. Syntax: Programming languages have their own syntax, which are a set of rules that determine how programs (commands, lines of code) are written and interpreted. The language syntax includes both elements of the code visible to human readers as well as elements of the code executed by the machine.

3. Function: We have a whole lab coming up on functions. For now, we can think of functions as a group of statements that perform a specific task. Python includes built-in functions like `print()`, `dict()`, `input()`, `int()`, and `len()`, but also allows you to create your own functions. Data, parameters, or arguments can be passed into a function, and a function can also return data.

4. Parameters and arguments can be used interchangeably in Python.

5. Method: In Python, a method is something that is applied to an object. That object could be a variable, string, number, or other type of data. A method is a function that is available for objects based on their type. For example `append()`, `extend()`, `sort()`, and `reverse()` are all methods that can be used with `list` object types. `capitalize()`, `upper()`, `lower()`, and `title()` are all methods that can be used with `string` object types.

6. Function vs. Method: Functions are generic, while a method is called on an object. A method is associated with an object (and can access/interact with the data or information that is part of that object). Functions do not alter the state of an object, while a method can alter an object state.

# Variables

7. We worked with variables in our first Python lab. A variable is a placeholder for a piece of information. You can think of it as a basket or container. 

8. Python has a few rules for variables:
- Variable names can only include letter, numbers, or underscores, but cannot start with a number.
- Spaces are not permitted.
- The names of Python methods and functions are reserved, meaning that they cannot be used as variable names. So, `print` cannot be used as a variable name.
- As a rule, variable names should be short and descriptive.

<blockquote>Q1: In your own words, explain the difference between <code>print(hello)</code> and <code>print(“hello”)</code>.</blockquote>

# Strings

9. What are strings? 

10. A string is a sequence of characters. 

11. Although we can have list of characters, often times we want to access and manipulate the sequence as an aggregate set of text rather than individual letters. 

12. Strings are identified by the <code>“ ”</code> or alternatively by <code>‘ ’</code>.

```Python
# example that creates a new string variable
first_name = 'Katherine'

# check variable type
type(first_name)

# view value of first_name variable
first_name
```

```Python
# example that converts integer to string
str(10)

# example that converts float to string
str(15.0)

# example that converts boolean to string
str(True)
```

13. Because certain operations on strings are so common, Python includes a variety of built-in methods that you can apply to a string object:

## Title Methods

14. Let's look at an example that uses different title methods.

```Python
# example using my name
name = "katherine walden"
```

15. Next, we’ll use the `print` function with the method `title`. Python functions and methods always end with a `()`. Methods define an additional action that can be applied to the data.
```Python
# example using my name, printed in title case
name = "katherine walden"
print(name.title())
```

16. Your program should output your data with a leading capital letter.

17. We can also change the case using the `upper()` method and `lower()` method: `print(name.upper())` outputs your string with all capital letters, while `print(name.lower())` outputs your string in all lower case.

- `Katherine Walden`
- `KATHERINE WALDEN`
- `katherine walden`

18. Try adding two additional `print()` functions calling the `name` variable with each of these methods.  

<blockquote>Q2: Describe the syntax of the three print statements generated in steps 14-18 in your own words. What is this code doing? Define the function and method for each example.</blockquote>

## Concatenation

19. Let’s modify our code a bit and create two new variables `first_name` for your first name and `last_name` for your last name. We can then combine these two string variables (called concatenation) in a third variable called `full_name`.

20. If we want our first and last name to be separated by a space, we need to tell Python to add one in by including the `“ “`, otherwise, each string will be printed back-to-back.
```Python
first_name = "katherine"
last_name = "walden"
full_name = first_name + " " + last name

print(full_name)
```

21. We can then use the `print()` function as we did before to output `full_name` in title case.
```Python
first_name = "katherine"
last_name = "walden"
full_name = first_name + " " + last name

print("Hello, " + full_name.title() + "!")
```

22. We could combine strings and variables in the same `print()` function to output a full sentence to the screen.

23. We could also assign this whole sentence to a variable and return the same output.

```Python
first_name = "katherine"
last_name = "walden"
full_name = first_name + " " + last name

sentence="Hello, " + full_name.title() + "!"

print(sentence)
```

<blockquote>Q3: Explain how each of these two programs (steps 20-23) work in your own words.</blockquote>

### Combining Variable Types

24. Python works with integers (whole numbers) and floats (any number with a decimal point). Python uses the basic mathematic symbols to perform functions: `+` (add), `-` (subtract), `*` (multiply), `/` (divide). 

25. Try this program:
```Python
print(2+3)
print(2-3)
print(2*3)
print(2/3)
```
<blockquote>Q4: Why does <code>print(2//3)</code> return 0? How would you modify your code to return the decimal number? Why?</blockquote>

26. Hint: Try `print(2.0//3.0)` using the floating point integers (numbers with decimal points).

27. Let’s write a new program with an integer variable and a string variable. Feel free to modify course number and department if taking this as something other than CSE 10101.
```Python
course_name="Elements of Computing I"
course_number = 10101

print("Welcome to " + course_name.title() + " CSE:" + course_number)
```

28. When you run the program, you will receive an error.

<p align="center"><a href="https://github.com/kwaldenphd/Python/blob/master/images/Image_8.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Python/blob/master/images/Image_8.png?raw=true" /></a></p>

29. The `type` error is telling us that we cannot use these two different variable types in the same function. 

30. When we want numbers to be read as characters rather than numeric digits, we have to use the string method `str()` to convert the integer into a string of characters.
```Python
print("Welcome to " + course_name.title() + " CSE:" + str(course_number))
```
<blockquote>Q5: Explain concatenation in your own words. Why must we convert numbers to strings in the program above? Refer to this example and the previous example.</blockquote>

<blockquote>Q6: Write a program that converts integer, float, or boolean values to a string, using the <code>str</code> function.</code></blockquote>

## String Length and Access

31. We can get the length or size of a string by using the `len` function.

```Python
len(first_name)
```

32. We can also extract (or isolate) individual characters within a string. To do so, we need a way to specify which character we mean. 

33. This is done by giving each position in the string an `index number` or `index operator`, which is determined by simply counting off (starting at 0) from left to right. 

34. We then use the index number as a subscript into the string. 

```Python
# access first character in string
first_name[0]

# access last character in string
first_name[-1]
```

35. In Python there is no notion of a character type as there is in languages such as Java or C. So when we check the type for a character in a string, we get back another string.

```Python
type(first_name[0])
```

36. Another example: let's say we have a variable `color` that includes the string `"turquoise"`.

37. Then...
- `color[0]` holds the letter `t`
- `color[1]` holds the letter `u`
- `color[2]` holds the letter `r`
- etc

<blockquote>Q7: Write a program that prompts the user to enter a 6-letter word, and then prints the first, third, and fifth letters of that word.</blockquote>
 
38. A sample output for your program might look like this:
```
Please enter a 6-letter word: joyful
The first, third, and fifth letters are: j y u
```

39. NOTE: Strings in Python are immutable, which means that you cannot change the elements of a string once it is set.

40. The following program will result in a `TypeError`.

```Python
first_name[0] = 'k'
```

41. So what do you do when you want to update a string? You simply construct a new one!

```Python
first_name = 'k' + first_name[1:]
first_name
```

## Other String Operations

42. Since a string is a sequence of characters, there are a few other operations that work on strings.

### Length

43. We've already seen the `len` function in action, but to refresh:

```Python
len(first_name)
```

### Properties

44. We can check the properties of characters in a string.
- `.isalpha()` checks if all string values are letters
- `.isalnum()` checks if string includes only letters and numbers
- `.isdigit()` checks if all string values are numbers
- `.islower()` checks if all string includes any lower-case characters
- `.isspace()` checks if the string includes any whitespace characters
- `.istitle()` checks if the string includes any title-case characters
- `.isupper()` checks if the string includes any upper-case characters

45. To see these string property methods in action in Python syntax:

```Python
# checks if all string values are letters
'abc123'.isalpha()

# checks if string values are letters and numbers
'abc123'.isalnum()

# checks if all string values are numbers
'abc123'.isdigit()

# checks if string includes any lower-case characters
'abc123'.islower()

# checks if string includes any whitespace characters
'abc123'.isspace()

# checks if string includes any title-case characters
'abc123'.istitle()

# checks if string includes any upper-case characters
'abc123'.isupper()
```

46. These commands return Boolean `True` or `False` values.

### Sort

47. We can sort characters in a string alphabetically.

```Python
# sort alphabetically
sorted(first_name)
```

48. These commands output the characters in the string in alphabetical order.

### Max and Min

49. We can also get the maximum or minimum value in the string. 

50. For strings that are sequences of characters, the minimum value is the character that appears first in the English-language alphabet, and the maximum is the character that appears last in the English-language alphabet.

```Python
# get max string letter
max(first_name)

# get min string letter
min(first_name)
```

### `in` Operator

51. We can also use the `in` operator to check if a character or substring (combination of characters) is present in another string.

```Python
# checks is 'a' is in 'abcd' string
'a' in 'abcd'

# checks if 'e' is in 'abcd' string
'e' in 'abcd'

# checks if 'bc' is in 'abcd' string
'bc' in 'abcd'
```

52. Each of these `in` operator examples returns a Boolean value, `True` or `False`.

### Search

53. We can also instruct the computer to search for a given character within a string.

54. There are a few different search methods we can use with strings:
 - `.startswith()` checks if the string starts with a character or substring
 - `.endswith()` checks if the string ends with a character or substring
 - `.find()` locates the index position for a specific character or substring
 - `.index()` also locates the index position for a specific character or substring
 
55. NOTE: The `.find()` method returns `-1` if the character or substring is not found. The `.index()` method will throw an error if the character or substring is not found.
 
56. To see these methods in action using Python syntax:
 
```Python
# checks if string starts with 'the' substring
'the boy who blocked his own shot'.startswith('the')

# checks if string ends with 'shot' substring
the boy who blocked his own shot'.endswith('shot')

# locates index position for 'who' substring
# note .find() outputs the index position for the first character in the substring
'the boy who blocked his own shot'.find('who') 

# checks if 'who' substring is located at index position 10
# note -1 return means the substring was not located at that position
'the boy who blocked his own shot'.find('who', 10)

# locates index position for 'who' substring
'the boy who blocked his own shot'.index('who') 

# checks if 'who' substring is located at index position 10
# unlike .find(), .index() will return a ValueError if the substring is located at that position
'the boy who blocked his own shot'.index('who', 10)
```

57. Let's look at another example.

58. Say we have a variable `color` holds the string `"turquoise"`. 

59. We can retrieve the index of the letter `q` (which is 3) as follows:
```python
color = "turquoise"
index_number = color.index("q")
print ("The index number for the letter q within the word " + color + " is " + index_number)
```

<blockquote>Q8: Modify the program to have it search for other characters in the string. Does it always return the index number you expect? What index is returned if you ask for the index of the letter u (i.e., what happens when the desired character appears more than once in the string)?</blockquote>

# Lists

60. Python allows us to store information in a few different ways. 

61. In this lab, we're focusing on lists, which are an ordered collection of items.

62. The individual values in a list are called elements or items. 

63. Lists have a type and are also considered values themselves.

## Lists With Numbers

```Python
# create a list containing 4 numbers
[0, 1, 2, 3]

# assign that list to a variable
numbers = [0, 1, 2, 3]

# check types of numbers variable
type(numbers)
```

64. Although this is rare, list elements do not need to be the same type.

```Python
[0, 1.0, 'a']
```

### List Length and Access

65. We can use the `len` function to get the length of a list.

```Python
len(numbers)
```

66. We can also use the index operator and index position to access and manipulate elements in a list.

```Python
# access first item in a list
numbers[0]

# access last item in a list
numbers[-1]
```

```Python
# modify first item in a list
numbers[0] = 'zero'
numbers
```

67. A few other notes on index operators:

68. Indeces can be any integer expression.

69. A few examples:

```Python
# `numbers[0+1]` is the same as `numbers[1]`
numbers[0+1]
numbers[1]

# index position stored as a variable
index = 1
numbers[index]
numbers[1]

# index position as a multiplication product
numbers[index * 2]
numbers[2]
```

70. An invalid index will yield an IndexError.

```Python
numbers[1000]
```

71. And as covered with strings, a negative index will start at the end of the list and count right to left.

```Python
# access last item in list
numbers[-1]

# access next to last item in list
numbers[-2]
```

### Modifying Lists

72. While strings are immutable, items in a list can be modified.

73. An example we've seen before that modifies a single list item.

```Python
# modify first item in a list
numbers[0] = 'zero'
numbers
```

#### Growing Lists

74. We can also grow an existing list using the `.append()` or `.extend()` methods.

```Python
# add integer 4 to end of numbers list
numbers.append(4)
numbers

# add [5,6,7] to end of numbers list
numbers.extend(range(5, 8))
numbers
```

75. To unpack what happened in that last bit of code- the `range()` function returns a sequence of numbers.

76. The default `range()` function starts at `0`, but in this example we start at `5`. The default `range()` function moves by increments of `1` and stops before a specified number. In our example, `range()` stops before 8.

#### A Quick Detour Into `range()`

77. The core syntax for range: `range(start, stop, step)`

78. You may have expected to see the numbers one to ten printed. This is yet another example of the quirks of working with programming languages.

79. Python starts with the first number and quits when it reaches the last number of your range. Because it stops at 10, it doesn’t include the 10.

80. We can actually create lists using `range()`.

```Python
# in this example we'll wrap the list() function around the range() function to create a list of numbers
numbers = list(range(1,10))
print(numbers)
```

<blockquote>Q9: How would you modify this code to output the full range 1-10?</blockquote>

81. What if we just wanted the odd numbers in this range? 

82. We could add an additional value to the range function to tell the computer to count by two.

83. A example that changes the step interval.

```Python
numbers = list(range(1,11,2))
print(numbers)
```

<blockquote>Q10: How would you rewrite the code to include only the even numbers from 1 to 10?</blockquote>

#### Deleting Items from Lists

85. We can delete items from a list using the `pop()` method or the `del` statement.

```Python
# remove an item at index 0 and return just that item
numbers.pop(0)

# remove an item at index 0
del numbers[0]
```

### Empty Lists

86. A list with no items is called an empty list.

87. We can also use the `list()` argument to create an empty list.

88. Examples in Python syntax:

```Python
# create empty list
[]

# create empty list using list()
list()
```

### Nesting and Sublists

89. Lists can also contain other lists- this is referred to as nested lists or sub-lists.

```Python
# create list with two sub-lists
points = [[0, 1], [2, 3]]
points

# access first item on list, which is a sublist
points[0]

# access first item WITHIN second item on list; 
# core syntax: list_name[list_item_number][sublist_item_number]
points[1][0]
```

### Other List Operations

#### Lists and the `in` Operator

90. Like with strings, we can use the `in` operator to test if a list contains a specific value.

```Python
# checks if 0 is i numbers
0 in numbers

# checks if 5 is in numbers
5 in numbers
```

91. Both of these commands return Boolean `True` or `False` statements.

#### List Concatenation

92. We can concatenate (or join) two lists using the `+` operator.

```Python
[0, 1, 2,] + [3, 4, 5]
```

#### Copying

93. We can copy a list using the `*` (multiplication) operator.

```Python
[0, 1, 2] * 3
```

#### Sorting

94. As with strings, we can sort the items in our list.

95. We have two options when sorting items in a list.

96. Sorting a list **in-place** changes the underlying order of items in the list.

97. Generating a sorted version of a list **does not** change the underlying order of items in the list.

98. Let's look at a few examples using Python syntax.

```Python
# create numbers list
numbers = [2, 4, 1, 3]

# sort list in place to update list order
numbers.sort()

# show updated list
numbers
```

```Python
# generate sorted version of list; DOES NOT change underlying order
sorted(numbers)

# will return original list order
numbers

# assign results of sorted() to new variable
sorted_numbers = sorted(numbers)

# show new variable with sorted list
sorted_numbers
```

##### Reverse

99. We can reverse a list using the `.reverse()` method of the `reversed()` function.

100. As with `.sort()` and `sorted()`, we have the option to reverse in-place or generate a reversed version of the original list.

101. To demonstrate using Python syntax:

```Python
# create list using range()
numbers = range(0, 7)

# reverse list in-place
numbers.reverse()

# show reversed list
numbers
```

#### Utility Functions

102. A few other functions that come in handy when working with lists that contain numbers.
- `sum()` calculates the sum of items in a list
- `max()` identifies the highest value in a list
- `min()` identifies the lowest value in a list
- `random.choice()` selects a list item at random
- `random.shuffle()` shuffles items in a list in-place
- `random.sample()` samples a select number of items from a list

103. Examples for each in Python syntax:

```Python
# compute the sum of a list
sum([0, 1, 2, 3])

# assign list to variable 
list = ([0, 1, 2, 3])

# compute sum of list using variable name
sum(list)
```

```Python
# find max value of list
max([0, 1, 2, 3])

# find max value of list using variable name
max(list)
```

```Python
# find min value of list
min([0, 1, 2, 3])

# find min value using list variable
min(list)
```
To use any of the `random` functions, we would first need to import the `random` module.

```Python
# import random module
import random

# select element at random
random.choice(list)
```

```Python
# shuffle a list in-place
random.shuffle(list)
```

```Python
# sample 2 elements from a list
# core syntax: random.sample(list_name, number_of_elements)
random.sample(list, 2)
```

### Looking Ahead

104. In the next lab, we'll talk all about conditional statements.

105. But for now, let's take a step back and think about how Python interacts with or treats the items in our list.

106. For example, when we're using the `in` operator, how does Python test for membership (i.e. see if the value we're looking for is located in the list)?

107. Python accomplishes this via **iteration**, which involves iterating over each item in the list. 

108. So Python starts at the first item in the list (index position `0`), and goes through each item on the list (left to right) until it reaches the end of the list.

109. Again, we will have a whole lab on conditional statements, but a few quick examples for now just to illustrate the concept of iteration.

110. We can use a **`for` loop** to iterate over the items in a list.

```Python
for number in numbers:
 print(number)
```

111. We can iterate over just the indeces in the list.

```Python
for i in range(len(numbers)):
 print(number[i])
```

112. We can retrieve the item and the index position using the `enumerate()` function.

```Python
for i, number in enumerate(numbers):
 print(i, number)
```

113. Again, more to come on conditional statements and loops.

### Lab Notebook Questions on Lists with Numbers

Q11: Create the list numbers with the following values: `[[0, 1], [2, 3], [4, 5]]`.
- What is the second element?
- How would you change 4 to 'four'?
- How would you change 1 to 'one'?
- How would you print out each sub-list (one sub-list per line)?
- How would you print out each number (one number per line)?

Q12: Create your own list of numbers. Include your list code as part of this question answer. What is the length of your list? What is the number position for each of the items in your list? How would you return the value of the first item? How would you return the value of the last item?

Q13: Using the same list from the previous question, write a program that includes the following steps or components:
- Adds a new item to your list
- Deletes an item from your list
- Sorts your list in-place
- Generates a sorted version of your list
- Reverses your list in-place
- Determines the `min` and `max` values for your list
- Selects a list element at random
- Shuffles your list

## Lists With Strings

114. Now let's put lists and strings together.

115. In the previous section of the lab, we focused on lists consisting of numbers.

116. Lists can also contain characters, or in this case, strings.

117. Write a list of a few of your favorite things.
```Python
cookies = ['chocolate chip', 'snickerdoodle', 'peanut butter', 'sugar']
```

118. We can print this list with a print function `print(cookies)`, but Python returns a representation of the list, just as we entered it.
`['chocolate chip', 'snickerdoodle', 'peanut butter', 'sugar']`

119. This isn’t particularly useful by itself; however, we can use the position of each item (the `index`) to perform different functions.

120. Add a `print()` function calling a specific item on your list.
```Python
print(cookies[0].title())
```

121. This command returns the first item on my list. This is the item in the `0` position on my list.
```Python
Chocolate Chip
```

122. Items in a list are indexed with a number, **beginning with 0 NOT 1.**

123. A `print` function that outputs the last item on my list of four items would look like this.
```Python
cookies = ['chocolate chip', 'snickerdoodle', 'peanut butter', 'sugar']
print(cookies[3].title())
```

124. We can also work backwards (left-to-right) on our list using negative numbers. For example, to call the last item on the list we could also use the index position `-1`.
```Python
cookies = ['chocolate chip', 'snickerdoodle', 'peanut butter', 'sugar']
print(cookies[-1].title())
```

125. To return the second to last item, we could use `-2`. For the third to last `-3`, etc.

126. We can concatenate our list items in strings.
```Python
cookies = ['chocolate chip', 'snickerdoodle', 'peanut butter', 'sugar']
print("My favorite cookie to bake is " + cookies[1].title() + ".")
```

127. Which outputs `My favorite cookie to bake is snickerdoodle.`

128. We can also change the items in a list. 

129. Maybe I have a friend who is allergic to peanut butter. I can change the `peanut butter` entry.
```Python
cookies = ['chocolate chip', 'snickerdoodle', 'peanut butter', 'sugar']
cookies[2] = 'oatmeal'
print(cookies)
```

130. The `print()` function outputs the modified list.
`['chocolate chip', 'snickerdoodle', 'oatmeal', 'sugar']`

131. We can also add data to our list using the append function.
```Python
cookies = ['chocolate chip', 'snickerdoodle', 'peanut butter', 'sugar']
cookies.append('oatmeal')
print(cookies)
```

132. The `print()` function now returns a list of five items `[chocolate chip, snickerdoodle, peanut butter, sugar, oatmeal]`

133. We can also use `append()` to create new lists.
```Python
my_pets = []
my_pets.append('Christy Mathewson')
my_pets.append('Smoky Jo Wood')
my_pets.append('Sandy Koufax')
print(my_pets)
```

134. In this block of code, we started with an empty list `[]`. Then the next two lines with `append()` add new items to the list.

135. With `append()`, items are added to the end of the list. 

136. The `insert()` function allows us to add items to any position in the list.
```Python
fruit = ['apple', 'pear', 'banana']
fruit.insert(1, 'orange')
print(fruit)
```

137. This block of code adds orange to the second position on the list (index position 1).

138. The output is `['apple', 'orange', 'kiwi', 'banana']`

139. Conversely, the `del` statement allows you to delete items from your list using the index number.

140. The following code will remove `orange` from the list.
```Python
fruit = ['apple', 'orange', 'pear', 'banana']
del fruit[1]
print(fruit)
```

141. We can also delete items by value (instead of position) using `remove()`.
```Python
fruit = ['apple', 'orange', 'pear', 'banana']
fruit.remove('orange')
print(fruit)
```

<blockquote><code>remove</code> only removes the first instance of the value in the list. So, if in the previous example orange appeared on the list a second time, only the first instance would be removed. To remove all instances, you would need to perform a loop (we’ll talk about loops later in the semester).</blockquote>

### List Functions and String Elements

142. Many of the list functions covered in the section of the lab focused on lists with numbers can also work on lists that contain strings.

#### `Len`

143. To find the length of your list, use the `len()` function.
```Python
fruit = ['apple', 'orange', 'pear', 'banana']
length = len(fruit)
print(length)
```

#### `Sort`

144. To alphabetize your list, use the `sort()` method.
```Python
fruit = ['apple', 'orange', 'pear', 'banana']
fruit.sort()
print(fruit)
```

#### `Reverse`

145. To print in reverse order, use `reverse()`.
```Python
fruit = ['apple', 'orange', 'pear', 'banana']
fruit.reverse()
print(fruit)
```

### Lab Notebook Questions on Lists With Strings 

146. To recap: Lists are an ordered collection of items. Lists can be numbers or strings. They are declared with a variable name, but the information is contained within `[ ]` and the individual items are separated by a comma. 

Q14: Create your own list of strings. Include your list code as part of this question answer. What is the length of your list? What is the number position for each of the items in your list? How would you return the value of the first item? How would you return the value of the last item?

Q15: Using the same list from the previous question, write a program that includes the following steps or components:
- Adds a new item to your list
- Deletes an item from your list
- Sorts your list in-place
- Generates a sorted version of your list
- Reverses your list in-place
- Determines the `min` and `max` values for your list
- Selects a list element at random
- Shuffles your list

# Dictionaries

<p align="center"><a href="https://github.com/kwaldenphd/python-dictionaries-sets/blob/master/figures/Dic_1.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/python-dictionaries-sets/blob/master/figures/Dic_1.png?raw=true" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/python-dictionaries-sets/blob/master/figures/Dic_2.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/python-dictionaries-sets/blob/master/figures/Dic_2.png?raw=true" /></a></p>

147. A dictionary is a mapping between a set of indices (keys) and a set of values. 

148. Each key maps to a value. 

149.  The association of a key and a value is called a key-value pair.

## Creating a Dictionary

150. We have two options for creating a dictionary.

151. We can use the `dict()` function or the `{}` syntax.

152. Examples for each:

```Python
# creating empty dictionary using dict()
english_to_french = dict()

# check variable type
type(english_to_french)

# create dictionary this time with key-value pairs
english_to_french = dict(
  'one': 'un',
  'two': 'deux',
  'three': 'trois',
  'four': 'quatre',
  'five': 'cinq'
)
```

```Python
# create empty dictionary using curly brackets {}
english_to_french = {}

# check variable type
type(english_to_french)

# create dictionary this time with key-value pairs
english_to_french = {
  'one': 'un',
  'two': 'deux',
  'three': 'trois',
  'four': 'quatre',
  'five': 'cinq'
}
```

## Interacting With A Dictionary

153. Now that we have a dictionary, we can start to bring in some of the syntax covered in previous labs.

```Python
print(english_to_french)
```

154. Notice that when we print the dictionary, the key-value pairs are **unsorted** and do not appear in the order in which we added them.

155. Due to the nature of the dictionary data structure, we cannot make any assumptions about the order in which items appear in the dictionary.

156. We can use the index operator to read the value for a particular key.

```Python
# access value for 'one' key
english_to_french['one']
```

157. If we try to access the value for a key that does not exist, Python will return a KeyError.

```Python
english_to_french['asdf']
```

158. We can test for membership using  the `in` operator.

```Python
# check for 'asdf' string
'asdf' in english_to_french

# check for 'one' string
'one' in english_to_french

# check for 'un' string
'un' in english_to_french
```

159. Each of these commands returns a Boolean `True` or `False` value.

160. Notice the last command returned `False` because the `in` operator is looking at keys, not values in the dictionary.

161. We can use the `.keys()` method to get a list of all keys in the dictionary.

```Python
print(english_to_french.keys())
```

162. We can use the `.values()` method to get a list of all the values in the dictionary.

```Python
print(english_to_french.values())
```

163. We can also add key-value pairs to our dictionary using the index operator and an assignment statement.

164. To see that in Python syntax:

```Python
english_to_french['six']   = 'six'
english_to_french['seven'] = 'sept'
english_to_french['eight'] = 'huit'
english_to_french['nine']  = 'neuf'
english_to_french['ten']   = 'dix'
print(english_to_french)
```

165. The first part of each line of code creates a new key and assigns the value (the string to the right of the assignment operator, or equals sign) to that key, giving us a new key-value pair.

## Iteration and Dictionaries

166. The previous lab talked about the concept of "iteration," and we're going to see it at work here as well.

167. Say we wanted to iterate by keys through our dictionary.

168. We could use a `for` loop to tell Python "`FOR` each key-value pair in my dictionary...do this thing!"

169. An example that tells Python to print the key for each key-value pair.

```Python
for key in english_to_french.keys():
  print(key)
```

170. We could modify the print statement nested in the for loop to output the key and value.

```Python
for key in english_to_french.keys():
  print(key, english_to_french[key])
```

171. And, we wouldn't actually need to use the `.keys()` method when iterating by keys.

```Python
for key in english_to_french:
  print(key, english_to_french[key])
```

172. We can also iterate by key-value pairs, using the `.items()` method.

```Python
for key, value, in english_to_french.items():
  print(key, value)
```

173. In this example, we told Python to look at the key and value in each key-value pair and print the pair.

## Dictionary Lab Notebook Question

<blockquote>Q16: Create a dictionary on a topic of your choosing. Include at least 7 key-value pairs.
<ol type="a">
 <li>Add new elements to your dictionary.</li>
 <li>Update an element in your dictionary.</li>
 <li>Print a list of all the keys in your dictionary.</li>
 <li>Print a list of all the values in your dictionary.</li>
 </ol>
 </blockquote>

# Sets

174. A set is an unordered collection of unique objects. Sets are primarily used to see if an object or value is in the collection (membership).

<p align="center"><a href="https://github.com/kwaldenphd/python-dictionaries-sets/blob/master/figures/Sets.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/python-dictionaries-sets/blob/master/figures/Sets.png?raw=true" /></a></p>

175. There are many different types of set operations, but this lab is just going to focus on testing for membership.

176. That is, looking to see if a particular value is `in` a set.

177. HINT: We've seen `in` operators before...

## Creating Sets 

178. We can create the set using `set()`

```Python
# create empty set and assign to s variable
s = set()

# check s variable type
type(s)

# create set with values
s = set([0,1,2])

# show set values
s
```

## Testing for Membership

179. Now that we have a set with values, we can test for membership using the `in` operator.

```Python
# create set with values
s = set([0, 1, 2])

# test if 0 is in s
0 in s

# test if 7 is in s
7 in s
```

180. The last two lines of code return Boolean `True` or `False` statements.

## Adding and Removing Items 

181. We can add items to our set using `.add()`.

```Python
# create empty set
s = set()

# add values to set
s.add(0)
s.add(1)
s.add(2)

# show new set with values
s
```

182. We can also remove values from our set using `.remove()`.

```Python
# create set with values
s = set([0, 1, 2])

# remove 1 number value from set
s.remove(1)

# show updated set
s
```

## Set Lab Notebook Question

<blockquote>Q17: Create the set <code>s</code> with the following values: <code>[1, 3, 5, 7, 9]</code>
<ol type="a">
  <li>Test to see if the value <code>11</code> is a member of the set.</li>
  <li>Test to see if the value <code>7</code> is a member of the set.</li>
  <li>Add a value to the set.</li>
  <li>Remove a value from the set.</li>
 </ol>
 </blockquote>

# Additional Lab Notebook Questions

<blockquote>Q18: What is the difference between a <code>list</code> and a <code>string</code>? What are some methods you can perform on a <code>list</code> that you can't do with a <code>string</code> (and vice versa)?</blockquote>

<blockquote>Q19: What is the difference between a <code>list</code> and a <code>dict</code>? When would we prefer one over the other?</blockquote>

# How to submit this lab (and show your work)

147. Moving forward, we'll submit lab notebooks as `.py` files. 

148. One option is to have a `.py` file that you use to run code and test programs while working through the lab. When ready to submit the lab notebook, you add comments and remove extraneous materials.

149. Another option is to have an "official" `.py` file that you are using as a lab notebook (separate from your working/testing file). Use comments in Python to note when you are starting a new question (as well as answering a question).
  * Example: `Lab5_Notebook_Walden.py`

150. What gets submitted as the lab notebook is the `Lab5_Notebook_Walden.py` file.
- When in doubt, use comments
- Be sure you are using comments to note what question you're responding to
 
# Lab Notebook Questions

Q1: In your own words, explain the difference between `print(hello)` and `print(“hello”)`.

Q2: Describe the syntax of the three commands that we just used (steps 10-14) in your own words. What is this code doing? Define the function and method for each example.

Q3: Explain how each of these two programs (steps 15-18) work in your own words.

Q4: Why does `print(2//3)` return `0`? How would you modify your code to return the decimal number? Why?

Q5: Explain concatenation in your own words. Why must we convert numbers to strings in the program above? Refer to this example and the previous example.

Q6: Write a program that converts integer, float, or boolean values to a string, using the `str()` function.

Q7: Write a program that prompts the user to enter a 6-letter word, and then prints the first, third, and fifth letters of that word.

Q8: Modify the program to have it search for other characters in the string. Does it always return the index number you expect? What index is returned if you ask for the index of the letter u (i.e., what happens when the desired character appears more than once in the string)?

Q9: How would you modify this code to output the full range 1-10?

Q10: How would you rewrite the code to include only the even numbers from 1 to 10?

Q11: Create the list `numbers` with the following values: `[[0, 1], [2, 3], [4, 5]]`
<ol type="a">
  <li>What is the second element?</li>
  <li>How would you change 4 to 'four'?</li>
  <li>How would you change 1 to 'one'?</li>
  <li>How would you print out each sub-list (one sub-list per line)?</li>
  <li>How would you print out each number (one number per line)?</li>
 </ol>

Q12: Create your own list of numbers. Include your list code as part of this question answer. What is the length of your list? What is the number position for each of the items in your list? How would you return the value of the first item? How would you return the value of the last item?

Q13: Using the same list from the previous question, write a program that includes the following steps or components:
- Adds a new item to your list
- Deletes an item from your list
- Sorts your list in-place
- Generates a sorted version of your list
- Reverses your list in-place
- Determiens the `min` and `max` values for your list
- Selects a list element at random
- Shuffles your list

Q14: Create your own list of strings. Include your list code as part of this question answer. What is the length of your list? What is the number position for each of the items in your list? How would you return the value of the first item? How would you return the value of the last item?

Q15: Using the same list from the previous question, write a program that includes the following steps or components:
- Adds a new item to your list
- Deletes an item from your list
- Sorts your list in-place
- Generates a sorted version of your list
- Reverses your list in-place
- Determines the `min` and `max` values for your list
- Selects a list element at random
- Shuffles your list

Q16: Create a dictionary on a topic of your choosing. Include at least 7 key-value pairs.
<ol type="a">
 <li>Add new elements to your dictionary.</li>
 <li>Update an element in your dictionary.</li>
 <li>Print a list of all the keys in your dictionary.</li>
 <li>Print a list of all the values in your dictionary.</li>
 </ol>

Q17: Create the set `s` with the following values: `[1, 3, 5, 7, 9]`
<ol type="a">
  <li>Test to see if the value <code>11</code> is a member of the set.</li>
  <li>Test to see if the value <code>7</code> is a member of the set.</li>
  <li>Add a value to the set.</li>
  <li>Remove a value from the set.</li>
 </ol>
  
Q18: What is the difference between a `list` and a `string`? What are some methods you can perform on a `list` that you can't do with a `string` (and vice versa)?

Q19: What is the difference between a `list` and a `dict`? When would we prefer one over the other?

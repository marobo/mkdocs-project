# Python Variables
-----------
Example of assign variable
```
>>> a = 1
>>> b = 2
>>> a = b
>>> a
2
>>> b
2
>>> b = 3
>>> a
2
>>> b
3
>>> b = a
>>> b
2
>>> a
2
>>>
```

**Scope**

A variable defined outside of a function is available inside that function
> variable ne'ebe defini iha funsuan nia liu se bele assesu iha funsaun nia laran

A variable defined inside of a function is NOT available outside of that function
> vabriable ne'ebe define iha funsaun nia lara la bele assesu iha funsaun nia liur


**Mutable or Immutable**

> Mutable means it can be added to.
> Immutable means it cannot be added to

**What types are Mutable?**

- lists
- dictonaries

```
people = {'ano': 1, 'ony': 2}

In [18]: def add_person(my_dict):
    ...:     my_dict.update({'mario':3})
    ...:     return my_dict
    ...:

In [19]: people
Out[19]: {'ano': 1, 'ony': 2}

In [20]: add_person(people)
Out[20]: {'ano': 1, 'mario': 3, 'ony': 2}

In [21]: people
Out[21]: {'ano': 1, 'mario': 3, 'ony': 2}
```

**What types are Immutable**

- tuples
- ints
- strings

```
In [12]: number = 5

In [13]: def plus_one(value):
    ...:     value = value + 1
    ...:     return value
    ...:

In [14]: number
Out[14]: 5

In [15]: plus_one(number)
Out[15]: 6

In [16]: number
Out[16]: 5
``` 

# Python List
--------------
This is how you write the python list in funciton and testing it
```
def hello_world():
    ''' This function returns 'Hello World' '''
    return 'Hello World'
```

Test the function
```
def test_hello_world():
    assert hello_world() == 'Hello World'
```

Add to the List
```
def add_to_list(my_value, my_list):
    '''
    Given a value and a list this function
    returns a list with the value added to it
    '''
    return my_list.append(my_value)
```

Test the function
```
def test_add_to_list():
    my_value = 5
    my_list = [1, 2, 3, 4]
    assert add_to_list(my_value, my_list) == [1, 2, 3, 4, 5]
```

Get Item from a List
```
def get_index_from_list(my_index, my_list):
    '''
    Given an index (integer) and a list this function will
    return the item at that index in the given list.
    If index is not an integer return None
    Remember Python indexes starts at 0
    '''

    if isinstance(my_index, int):
        return my_list[my_index]
```
Test the function
```
def test_get_index_from_list():
    my_list = ['1', 'Baucau', 'Aileu', 5, 'Cars']

    assert get_index_from_list(2, my_list) == 'Aileu'
    assert get_index_from_list('hello', my_list) == None
```

Check list for value
```
def is_in_list(my_value, my_list):
    '''
    Given a value and a list this function checks if the value can be found in the list
    and returns True or False
    '''
    pass
```
Test the function
```
def test_is_in_list():
    my_value = 3
    not_my_value = 4
    my_list = [1, 2, 3]

    assert is_in_list(my_value, my_list) == True
    assert is_in_list(not_my_value, my_list) == False
```

List Length
```
def get_length(my_list):
    '''
    Given a list this function
    returns the number of items in the list
    '''
    pass
```
Test the function
```
def test_get_length():
    my_list = [1, 2, 3]
    assert get_length(my_list) == 3
```

Merge two lists
```
def merge_lists(first_list, second_list):
    '''
    Given two list this function returns a single list which contains the items of the
    first list followed by the items of the second list
    '''
    pass
```

Test the function
```
def test_merge_lists():

    first_list = [1, 2, 3]
    second_list = [4, 5, 6]
    assert merge_lists(first_list, second_list) == [1, 2, 3, 4, 5, 6]
```

Converting a list to string
```
def list_to_string(my_list):
    '''
    Given a list the is funciton returns a string which includes the items of the list
    separated by single spaces
    '''
    pass
```
Test the function
```
def test_list_to_string():
    my_list = ['one', 'two', 'three']
    assert list_to_string(my_list) == "one two three"

```

Count items in list
```
def count_occurrences(my_list):
    '''
    This function will return a dictionary containing
    the number of occurrences of a item in a given list.
    '''
    pass
```

Test the function
```
def test_count_occurrences():
    my_list = ['a', 'a', 'a', 'b', 'b', 'b', 'c', 'c']
    assert count_occurrences(my_list) == {'a': 3, 'b': 3, 'c': 2}
```

Strings and lists
```
def string_to_list(my_string):
    '''
    This function takes a string and returns that string as a list.
    If a the given value is not a string. The function returns None.
    '''
    pass
```

Test the function
```
def test_string_to_list():
    assert string_to_list('hello world') == [
        'h', 'e', 'l', 'l', 'o', ' ', 'w', 'o', 'r', 'l', 'd']
    assert string_to_list(5) == None
    assert string_to_list({'hello': 'world'}) == None
```

# Python Dictionaries
---------------------

### What is a dictionary?
Stores key / value pairs

### How do we make a new dictionary?
Dictionaries use curly brackets `{}`
```
>>> ages = {'Nando': 26, 'Peter': 36, 'Ano': 25}
```

### How do you add a key / value to a dictionary?
```
>>> ages['Niko'] = 25
>>> ages
{'Ano': 25, 'Nando': 26, 'Niko': 25, 'Peter': 36}
```

### How do you changes a value for a given key?
Keys are unique.
```
>>> ages['Ano'] = 26
>>> ages
{'Ano': 26, 'Nando': 26, 'Niko': 25, 'Peter': 36}
```

### How do we get a value for a key?
```
>>> ages.get('Peter')
36
```

Can also have a default value
```
>>> ages.get('Peter', 'Unknown')
36
>>> ages.get('Anders', 'Unknown')
'Unknown'
```

Access the key directly
```
>>> ages['Peter']
36
```

This might cause a KeyError
```
>>> ages['Anders']
KeyError
```

### How do you remove a key?
Use `del` to remove a key / value pair from a dictionary
```
>>> ages = {'Ano': 25, 'Nando': 26, 'Niko': 25, 'Peter': 36}
>>> del ages['Niko']
>>> ages
{'Ano': 25, 'Nando': 26, 'Peter': 36}
```

### How can you find the size of a dictionary?

Use `len()` to get the number of key / value pairs in a dictionary
```
>>> len(ages)
3
```

### How do you check if a value is in a dictionary?
Use `in` to see if a given key is in a dictionary
```
>>> 'Anders' in ages
False
>>> 'Peter' in ages
True
```

### How do we get a list of keys?
Use the `.keys()` method
```
>>> ages.keys()
['Nando', 'Peter']
```

### How do we get a list of values?
Use the `.values()` method
```
>>> ages.values()
[26, 36, 25]
```

### More example about python dictionary with a functions and test 
```
def hello_world():
    ''' This function returns 'Hello World' '''
    return 'Hello World'


def test_hello_world():
    assert hello_world() == 'Hello World'


def add(a, b):
    ''' This function adds two values '''
    return a + b

# Dictionaries

def test_add():
    assert add(1, 1) == 2
    assert add(1, 2) == 3
    assert add(23, 24) == 47


def multiply(a, b):
    ''' This function multiplies two values '''

def test_list_values_in_dict():
    assert list_values_in_dict({'hello': 'world'}) == ['world', ]
    assert list_values_in_dict({'world': 'hello'}) == ['hello', ]
    assert list_values_in_dict({'a': '1', 'b': '2', 'c': '3'}) == ['1', '2', '3', ]


def count_occurrences(my_list):
    ''' This function will return a dictionary containing 
    the number of occurrences of a item in a given list. '''
    from collections import Counter
    return Counter(my_list)


def test_count_occurrences():
    my_list = ['a', 'a', 'a', 'b', 'b', 'b', 'c', 'c']
    assert count_occurrences(my_list) == {'a': 3, 'b': 3, 'c': 2}


def string_to_list(my_string):
    ''' This function takes a string and returns that string as a list.
        If a the given value is not a string. The function returns None.'''


def test_string_to_list():
    assert string_to_list('hello world') == ['h', 'e', 'l', 'l', 'o', ' ', 'w', 'o', 'r', 'l', 'd']
    assert string_to_list(5) == None
    assert string_to_list({'hello': 'world'}) == None

```

# Python Read a File
-------------------

Read a file in python
```
with open('WC_text.txt') as fp:
    print(fp.readlines())
```

Read a file in python and count the lines inside
```
def count_line():
    with open('WC_text.txt') as fp:
        lines = fp.readlines()
    count = 0
    for line in lines:
        count += 1
    return count
count_line()
```

Read a file in python and count the words inside
```
def count_words():
    with open('WC_text.txt', 'r') as fp:
        lines = fp.read()
        word_list = lines.split()
        number_of_words = len(word_list)
    return number_of_words
count_words()
```

Read a file in python and count the charaters inside
```
def count_character():
    with open('WC_text.txt') as fp:
        lines = fp.read()
        word_list = lines.replace(" ", "")
        number_of_words = len(word_list)
    return number_of_words
count_character()
```

Combine the functions above in one function
```
def wc():
    with open('WC_text.txt', 'r') as fp:
        
        # Read a file
        read_file = fp.readlines()
    count_lines = 0
    count_words = 0
    count_character = 0
    for line in read_file:
       
        # Count line
        count_lines += 1
        
        # Count words
        word_list = line.split()
        count_words += len(word_list)
        
        # Count character
        word_character = line.replace(" ", "")
        count_character += len(word_character)
    return f"{count_lines} lines, {count_words} words, {count_character} charaters"
wc()
```

More example about count lines
```
def line_count():
    import os
    import os.path
    while True:
        file_location = input("Which file do you want ot open?")

        if os.path.isfile(file_location) and os.access(file_location, os.R_OK):
            print("Ok")
            break
        else:
            print("This not a file")
    print(file_location + "is a valid file")
    line_count = 0
    emtpy_line_count = 0
    long_count = 0
    with open(file_location) as f:
        for line in f:
            line_count += 1
            if line == '\n':
                emtpy_line_count += 1
            if len(line) > 20:
                long_count += 1

    print(line_count, emtpy_line_count, long_count)
line_count()
```

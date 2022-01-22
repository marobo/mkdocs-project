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

# Python Lists
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
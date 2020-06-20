# Automate-the-Boring-Stuff-With-Python

# 2 FLOW CONTROL
# break: escapes loop
# continue: program execution jumps back to start of loop and reevaluates loop’s condition
# for i in range (x,y): x=start, y-1=end
# for i in range (x,y,z): x=start, y=stop, z=amount variable is increased after each iteration
# sys.exit(): terminate program

# 3 FUNCTIONS
# If there is a global statement for that variable in a function, it is a global variable
# exception handling
def spam(divideBy):
    try:
        return 42 / divideBy
    except ZeroDivisionError:
        print('Error: Invalid argument.')
print(spam(2))
print(spam(0))
print(spam(1))

def spam(divideBy):
    return 42 / divideBy
try:
    print(spam(2))
    print(spam(0))
    print(spam(1))
except ZeroDivisionError:
    print('Error: Invalid argument.')
    
# 4 LISTS
# list: value containing multiple values in an ordered sequence, values inside lists called items (ie: ['hello', 3.1415, True, None, 42])
# get individual values in list with Indexes: variablename[0]
# can have lists of lists (ie: spam = [['cat', 'bat'], [10, 20, 30, 40, 50]]) and index (ie: spam[0][1] will return 'bat')
# negtive index: -1 refers to last index in list
# slice: [x:y], x=index where slice starts, y-1=index where slice ends
  # [:] leavingg out an index on either side of colon evaluates to beginning of list and/or end of list
# len(list) will return the number of values in that list
# can change values of list with listname[x] = newitem
# lists can be concatenated and replicated with + and *
  # + joins two lists, * can be used with a list and interger to replicate list
# remove values from lists: del list[x]
# can do: for i in range(len(listname)) to iterate over the indexes of a list
# in and not in operators
# multiple assignment trick/tuple unpacking: shortcut to assignn multiple variables with the values in a list in one line of code
# instead of range(len(list)), use enumerate(list) which will return 2 values (index of item in list and item in the list)
supplies = ['pens', 'staplers', 'flamethrowers', 'binders']
for index, item in enumerate(supplies):
    print('Index ' + str(index) + ' in supplies is: ' + item)
# random.choice(list) will return return random value in list
# random.shuffle(list) will reorder items in list
# find value in list with list.index(item)
# add value to end of list with: list.append(item)
# add value to any index with: list.insert(x, item), x is index for new value
# remove value from list with: list.remove(item)
# sort values in list with: list.sort() or list.sort(reverse=True)
# to sort values in regular alphabetical order: list.sort(key=str.lower)
# reverse values in list with: list.reverse()
# list value is mutable (can have values added, removerd or changed)
# a string is immutable (can't be changed)
# tuple: uses parantheses, immutable
eggs = ('hello', 42, 0.5)
eggs[0]
eggs[1:3]
len(eggs)
# convert list to tuple: tuple(['cat', 'dog', 5])
# convert tuple to list: list(('cat', 'dog', 5))
# list('hello') returns ['h', 'e', 'l', 'l', 'o']
# to make duplicate cop of a mutable value instead of a copy of a reference use: copy.copy(name) 
# to copy a list containing lists use: copy.deepcopy()

# 5 DICTIONARIES AND STRUCTURING DATA
# dictionary: mutable collection of many values
   # unlike indexes for lists, indexes for dicts can use different data types
   # indexes for dicts are called keys, a key with its associated value is called a key-value pair
   # items in dicts are unordered -> can't be sliced like lists
newdict = {'k1':'v1', 2:'v2'}
newdict['k1'] #this returns 'v1'
newdict[key] = value #adds key-value pair into dict
# to iterate over values in a dict: for v in dict.values()
# to iterate over keyys in a dict: for k in dict.keys()
# to iterate over items in dict: for i in dict.items()
# to assig key and value to seperate variables, use multiple assignment trick: for k,v in dict.items()
# check if something in dict with: 'key' in dict.keys() or 'key' in dict or 'value' in dict.values()
# dict.get('key',x) will check if key exists, and if not will set default value of that key to x
# to set a value in a dict for a certain key if that key doesn't already exist use: dict.setdefault('key','value') -> iff key already exists, nothing will change
# to print cleaner display of items in dict use: pprint.pprint(dict)
# to obtain prettified text as a string value instead of displaying it on screen call: prinnt(pprint.pformat(dict))

# 6 MANIPULATING STRINGS
# escape characters
# raw string: ignores all escape characters and prints any backslash in string, place an r before beginning quotation mark
# multiline stringn with triple quotes instead of /n
# multiline comment with triple quotes
# string interpolation 
    name = 'Al'
    age = 40
    print('My name is %s. I am %s years old.' % (name, age))
# f-strings: instead of %s, expressions placed directly inside braces and f prefix
    name = 'Al'
    age = 40
    print(f'My name is {name}. Next year I will be {age + 1}.')
# upper(), lower(), isupper(), islower(), isalpha(), isalnum(), isdecimal(), isspace() and istitle() methods
# startswith() and endswith() methods return True if string value they're called on begins/ends with string passed to the method
# join() method: used to join a list of strings into a single string value, called on a string, gets passed a list of strings, and returns a string
     ', '.join(['cats', 'rats', 'bats']) -> 'cats, rats, bats'
     ' '.join(['My', 'name', 'is', 'Simon']) -> 'My name is Simon'
# split() method: called on a string value and returns a list of strings, by default split wherever whitespace characters are found, can pass a delimiter string to  split() method to specify a different string to split upon
    'MyABCnameABCisABCSimon'.split('ABC') -> ['My', 'name', 'is', 'Simon']
# passing splt() the argument /n will split multiline string along the newlines and return a list 
# partition(): split string into the text before and after a separator string, returns a tuple of three substrings for the “before,” “separator,” and “after” substring, only splits string in first instance of occurence
    'Hello, world!'.partition('o') -> ('Hell', 'o', ', world!')
    If separator string not found, the first string returned in tuple will be entire string, the other two strings will be empty
# can use  multiple assignment trick to assign the three returned strings to three variables
    before, sep, after = 'Hello, world!'.partition(' ')
    before -> 'Hello,'
    after -> 'world!'
# rjust() and ljust(): return a padded version of the string they are called on, with spaces inserted to justify the text. The first argument to both methods is an integer length for the justified string. An optional second argument to rjust() and ljust() will specify a fill character other than a space character
    'Hello'.rjust(10) -> '     Hello'
    'Hello'.ljust(20, '-') -> 'Hello---------------'
# center() string method: centers the text rather than justifying it to the left or right
    'Hello'.center(20, '=') -> '=======Hello========'
# remove whitespace with strip(), rstrip(), and lstrip(): strip() will return new string without any whitespace at beginning or end, lstrip() and rstrip() methods removes whitespace from left and right ends
# optionally, a string argument will specify which characters on the ends should be stripped, order of characters in the string passed to strip() does not matter: strip('ampS') will do the same thing as strip('Spam')
    spam = 'SpamSpamBaconSpamEggsSpamSpam', spam.strip('ampS') -> 'BaconSpamEggs'
# use ord() to get the code point of a one-character string, and chr() to get the one-character string of an integer code point
# pyperclip.copy and pypercli.paste



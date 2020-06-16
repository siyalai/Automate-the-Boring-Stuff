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

# MANIPULATING STRINGS

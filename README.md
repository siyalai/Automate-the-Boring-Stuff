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
# remove values from lists: del listname[x]
# can do: for i in range(len(listname)) to iterate over the indexes of a list
# in and not in operators
# multiple assignment trick/tuple unpacking: shortcut to assignn multiple variables with the values in a list in one line of code
# instead of range(len(list)), use enumerate(list) instead

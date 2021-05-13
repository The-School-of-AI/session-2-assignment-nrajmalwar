# Session 2 assignment of EPAi3.0
Object Mutability and Interning


## class Something

> This class has a variable called something_new which is an object of the class SomethingNew(). We can reference the SomethingNew() class using an object of Something().

## class SomethingNew

> This class stores an iterable i and a variable which stores the instance of the class Something(). We can reference the Something() class using an object of SomethingNew().

## class add_something

> This class creates an instance an of both Something() and SomethingNew() and stores the object of Something() in a list called collection.

## clear_memory

> This function clears collection list from memory. However, as objects of Something() and SomethingNew() are still in cyclic reference with each other, it does not get completely removed from memory. Hence, we import gc (garbage collector) and use gc.collect() to remove the cyclic references of the objects of these two classes as they cannot be accessed anymore.


## critical_function

> This function creates an empty list called collection. It runs a for loop for 1024 * 128 = 1,31,072 times and calls the function add_something() which creates cyclic references 1,31,072 number of times. Finally, it calls clear_memory() to delete the collection list.

## compare_strings_old

> This function suboptimally tests whether two strings are exactly same or not and if we have a particular character in that string or not. First, it compares it string character by character. Second, it loops over the entire string to search for the character.


## compare_strings_new

> This function tries to optimize the function compare_strings_old(). 
> 
> First, it uses string intern using sys.intern() to assign a reference id for the string input `a = 'a long string that is not intered' * 200`and maintains a table for such a variable. When we pass the variable `b = 'a long string that is not intered' * 200` it recognizes that it is same as a and references b to that same id. For string comparison, we use `if a is b` as we can now compare their ids only instead of their content.
> 
> Second, we use `char_list = set(a)` as it gives us the unique set of characters in the string a. Instead of looping over the entire string, we compare the character with only the unique values of the string a.
> 
## sleep

> sleep() is defined in the time() module. It takes the number of seconds for which the code is required to be stopped as an argument.
> 
## char_list

> In the compare_strings_old(), char_list stores all the characters of the string as a list. We change this to store the unique characters of strings in a in the function compare_strings_new().
> 
## collection

> collection is list storing the objects of the class Something().
> 
## __int__

> __init__ is used to initialize the state of an object. It contains a collection of statements that are executed at the time of creation of the object. We use `self` in order to pass or create the variable associated with the object being instantiated.

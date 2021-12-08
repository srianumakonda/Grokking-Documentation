Binary search
=====

.. _searchproblem:

The search problem
------------

.. Important:: to find element x in a given list i, should i start from the beginning or start near the middle and split each step up and half?

This is exactly what binary search is. It's input is a **sort list of elements** with the output being the **index of where that element is located**. 

Simple (stupid) search is essentially when we go through every single index in the list up until you find the desired element.

*If my number was 99, it could take you 99 guesses to get there!*

The better technique for counting? **Start with 50.** If that number's too low, then you just eliminated 50% of all the numbers!

Your next range is between 50-100. What's the middle of that? 75. **Too high? Then cut again?**

63? No. **57? YES!**

You just guessed the number within 7 steps!

.. Important:: *"Eliminate half the numbers every time with binary search. For any list of n, binary search will take log_n steps to run in the worst case, whereas simple search will take n steps."* 


Code
----------------			

What does that looks like in code?

.. code-block:: python
   :linenos:

   def binary_search(list, item):
       low = 0
       high = len(list)-1
       while low <= high:
            mid = int((low + high)/2)
            guess = list[mid]
            if guess == item:
	        return mid
	        if guess > item:
		    high = mid - 1
	        else:
		    low = mid + 1
       return None

>>> my_list = [1, 3, 5, 7, 9]
>>> print(binary_search(my_list, 3)) 
1
>>> print(binary_search(my_list, -1)) 
None


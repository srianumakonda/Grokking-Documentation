Running time
=====

Whenever the maximum amount of guesses is equal to the size of the list, we generally define this to be **linear time**

.. _code:
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

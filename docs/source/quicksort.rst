Quicksort
=====

Quicksort is generally known as a **sorting algorithm.** It's a lot **faster than selection sort** and is generally used. It uses a recursive algorithm structure for fast + proper sorting.

Here's what the process looks like:

1. Pick an element from the array. **This is generally known as a pivot.**
2. From there, you **bin the smaller + larger elements into 2 separate arrays.**
    a. This overall process is known as **partitioning**
3. You then run this **recursively until you get sorted arrays** and then you can simply **concatenate everything** and you now have your output.


Running times
------------

The average runtime generally for quicksort is **O(n log n)** but the worst case is generally **O(n^2) time.**

Generally remember that when we call something like **O(n)**, it's generally more of like **O(c*n)** where *c* is a constant multiplied by n but we usually don't look at that for large numbers.

But sometimes, **the constant can make the difference.** Quicksort generally has a smaller constant than merge sort. So if both of them are in O(n log n) time, then **quicksort is faster.**

Quicksort is also faster in practice mainly because it actually meets the average case substantially more than the worst case.

.. Important:: **The pivot matters.** You want to have both arrays be as small as they can. **That's why you'd always choose the middle [or a random] number.**

"In this example, there are O(log n) levels (the technical way to say that is, “The height of the call stack is O(log n)”). And each level takes O(n) time. *The entire algorithm will take O(n) * O(log n) = O(n log n) time. This is the best-case scenario."*

Code
------------

.. code-block:: python
   :linenos:

   def quicksort(array):
     if len(array) < 2:
       return array
     else:
       pivot = array[0]
       less = [i for i in array[1:] if i <= pivot]
       greater = [i for i in array[1:] if i > pivot]
     return quicksort(less) + [pivot] + quicksort(greater)

>>> print(quicksort([10, 5, 2, 3]))
[2, 3, 5, 10]

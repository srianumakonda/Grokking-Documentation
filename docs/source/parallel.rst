Parallel algorithms
=====

The main focus with parallel algorithms is to **take advantage of the multiple cores in a computer.**

For example, the best time you can get with a sorting algorithm is generally **O(n log n) time.** You can't generally sort an array in **O(n)** time, **unless you use a parallel algorithm!**

Parallel algorithms are generally super hard to design + get it working. 

.. Important:: *"So if you have two cores in your laptop instead of one, that almost never means your algorithm will magically run twice as fast."*

Why?
 
1. Parallelism management - if you have to sort an array of 1,000 items, how do you divide this task among the two cores? Even if you give each core 500 items to sort and then merge them, merging itself takes time.
2. Load distribution amongst processors - if you have 10 tasks to do, you'd probably give each core 5 tasks. What's the problem? The first core is given the easy tasks whereas the other core gets all the hard tasks. **Now a core stays idle while it could be used to work.**


.. figure:: images/44.png
   :align: center

Let's take a look at examples of parallel algorithms:

MapReduce
------------

A special type of parallel algorithm used is MapReduce that's becoming increasing famous, known as **distributed algorithms**. MapReduce is essentially a popular distributed algorithm to manage workloads amongst hundreds of cores.

The main benefit here is that distributed algorithms allow you to do lots of work while the objective is to speed up the time it takes to do it. 

MapReduce works on 2 main functions: **map** and **reduce:**

The map function basically **applies a function to each item in an array** while distributing the workload on each machine/core. 

The reduce function basically **downsizes a list of items into a singular output.** An example might be...

>>> arr1 = [1, 2, 3, 4, 5]
>>> reduce(lambda x,y: x+y, arr1)
15
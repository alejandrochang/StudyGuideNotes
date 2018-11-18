# ALGORITHMS

## RECURSION

### What is a base case in recursion? Why do we need one? Do we always need one?
A base case is a solution to a given problem to build off. If no base case is given, a stack overflow happens.


### What exactly is a Stack Overflow?
when to many recursive calls are made because no base case was given


### Describe direct and indirect recursion
Direct recursive functions call themselves, indirect functions call another function

### What is tail call recursion? Why is it helpful, if at all?
A recursive function is tail recursive when recursive call is the last thing executed by the function. The tail recursive functions considered better than non tail recursive functions as tail-recursion can be optimized by compiler. The idea used by compilers to optimize tail-recursive functions is simple, since the recursive call is the last statement, there is nothing left to do in the current function, so saving the current function’s stack frame is of no use

### Discuss advantages/disadvantages of recursion
DIS: Recursive program has greater space requirements than iterative program as all functions will remain in stack until base case is reached. It also has greater time requirements because of function calls and return overhead.

ADV: Recursion provides a clean and simple way to write code. Some problems are inherently recursive like tree traversals.

### How is memory allocated during recursive function calls?
A recursive function calls itself, the memory for called function is allocated on top of memory allocated to calling function and different copy of local variables is created for each function call. When the base case is reached, the function returns its value to the function by whom it is called and memory is de-allocated and the process continues.


### What is the difference between Memoization and Tabulation?
Memoization is building a lookup table for recursion form the top up, while tabulation builds from the bottom up. Memoization builds a table as calls are made, while tabulation builds a table before calls are made.


### Why is memoization helpful?
it helps cut time with recursive calls by using a look up table

### Select the correct statement(s) about recursion
Tail recursion requires that you don't use any variables in the last line of the code unless you are passing them as arguments to the recursive call


### Which statement(s) about recursion and iteration is/are correct?
A) Recursion is more suited to functional programming because you can more easily create stateless methods
D) Any recursive problem can be done iteratively

## DYNAMIC PROGRAMMING

### What is an optimal substructure? When might a problem have one?
A given problem has Optimal Substructure Property if optimal solution of the given problem can be obtained by using optimal solutions of its subproblems, such as shortest distance between 2 nodes with a node in between

### Choose the correct statement(s) about Dynamic Programming
A) Tabulation will create a complete record of subsolutions from the Bottom-up

### Choose the correct statement(s) about event bubbling
D) Event delegation is useful when you might be dynamically adding children to a parent and you need to execute an action on the child


## MERGE SORT

### Explain the pseudocode for Merge Sort
Sort a collection by breaking it into halves. Then sort those two halves and then merge them together to form one completely sorted collection.

### What is the runtime of merge sort?
Θ(n·log(n))


## COUNTING SORT

### What are the steps for Counting Sort? What is the time complexity?
1. Take an arrayA and iterate through the elements. 
2. In a new arrayB, store how many times an element occurs in arrayA in the index of arrayB
3. Shift a 0 and pop the last element from arrayB
4. ArrayB has the starting positions of the sorted elements in a new ArrayC


## BUBBLE SORT

### What is the time complexity of Bubble Sort? What are the steps for this algorithm?
O(n^2), iterate over elements and swap if element to the right is less than current element. Repeate over array until sorted


### Describe when it may be ideal to utilize Bubble Sort
finding the greatest or smallest k elements


## RADIX SORT

### What is the time complexity of Radix Sort? What are the steps for this algorithm?
Let there be d digits in input integers. Radix Sort takes O(d*(n+b)) time where b is the base for representing numbers, for example, for decimal system, b is 10.

steps are to sort numbers by the 1's digit, then 10's, then 100's, etc

### What is an ideal use-case for Radix Sort?
Sorting for elements between 1 and n^2


<!-- WEEK 4 -->


## HASH TABLE

### Give a high level overview of how to implement a hash table.
Data is sent through a hashing function. That hash function result is then put matched with an array index that points to a linked list and the data is added to the linked list

### Give a high level overview of how to implement a Linked List.
Nodes are created with values and pointers to other nodes to create a "list"

<!-- WEEK 5 -->

## BINARY SEARCH

### Why is binary search logarithmic time?
It removes half of the elements with every comparison


### If an element is smaller than its right neighbors, explain why there is definitely a peak to the right.
the definition of peak elements say that if all numbers are in an increasing fashion, then the last element is the peak

### Explain how you can still find an element in log time when the array is rotated
If you can find the pivot element, then you can still do log(n) binary search on it

### How does Interpolation Search Work?
In a uniformly distributed collection of integers, you interpolate the searched element between min and max and then access that index. if the number matches, return it. if your number is less than the searched number, recurse over your number to the max and vice versa, repeat

### What is Interpolation Search's expected time complexity, and what is it sworst time complexity? Why?
Expected: log(log(n))
worst: n

### What is the best solution to the Kth smallest/largest problem?
Min Heap and call extract k times

### Compare using a min-heap and a max-heap to sovle kth smallest/largest problem
Build a max heap with only k amount of nodes, then as more nodes are to be added you first compare them to the root and see if the new node is less than the root node

Min Heap and call extract k times

### Explain how finding pairs in an array can be solved in linear time
Initialize diff = inf, right = length-1 and left = 0. 

while l < r:
1. if (a[l] + a[r] - sum < diff), update to new diff and results pair
2. if (a[l] + a[r] > sum), l++
3. else, r--


### What are the steps to detecting a cycle in a graph?
1. for each edge, make a subset of the two nodes
2. If the two nodes are not in the same subset, then union into one subset
3. if they are in the same subset, then a cycle is found


### What is the Floyd-Warchall algorithm good for?
The problem is to find shortest distances between every pair of vertices in a given edge weighted directed Graph

### How does Floyd-Warchall work?
1. Set up a VxV array "dist" and fill in the spaces with 0, Inf, or direct edge weights
2. Iterate through every i-j pair in table with another k value. K if used for intermediate nodes to pass through
3. fill in the array with a new value:
```js
        if ( dist[i][k] != INF && 
            dist[k][j] != INF && 
            dist[i][k] + dist[k][j] < dist[i][j]
            )
        dist[i][j] = dist[i][k] + dist[k][j];
 ```


### Explain Kruskal's Minimum Spanning Tree algorithm. What algorithm does this remind you of? What's the difference?
A spanning tree is a way to connect all nodes in a connected undirected graph with minimal edge weights. It's like finding a cycle in a graph, but you want to connect all nodes and not just look for cycles


### What is the time complexity of inserting into a sorted singly-linked LL? How can you do it in one pass only
O(n), iterate from the head to the tail and find the node that is larger than the node you want to insert and insert your node before that node

### What do you have to do to delete a node from a list?
Find the target node and then remove its pointers to other nodes and the pointers to the target node

### How may we compare two strings using a Linked List?
1. iterate over both lists while there is a Node for each list and that each of those nodes' values are equal. 
2. Set Node1 to Node1.next and Node2 to Node2.next. 
3. If Node1 and Node2 exist, check to see if the letters mismatch. Return 1 if Node1 > Node2 or -1 if Node1 < Node2
4. If Node1 && !Node2, return 1. If !Node1 && Node2, return -1 (node2 or node1 reached end, respectively)
5. OTherwise, return 0 (both lists have reached their end)

### Explain how you handle numbers of different sizes when summing two Linked Lists
1. Calculate difference of sizes of two linked lists. Let the difference be diff
2. Move diff nodes ahead in the bigger linked list. 
3. Calculate sum of the carry (calculated in previous step) with the remaining left sub-list of larger list. Nodes of this sum are added at the beginning of sum list obtained previous step.

### Explain how the carry operation works in the handling summing Linked Lists of different sizes
If a sum goes over ten, make a new node of the 1's place then backtrack and add 1 to the Node.head's place

### When creating an alternating linked list, what do you do?
The idea is to run a loop while there are available positions in first loop and insert nodes of second list by changing pointers. 

### What is the best method for getting the union and intersection of two lists?
Union (list1, list2)
Initialize the result list as NULL and create an empty hash table. Traverse both lists one by one, for each element being visited, look the element in hash table. If the element is not present, then insert the element to result list. If the element is present, then ignore it.

Intersection (list1, list2)
Initialize the result list as NULL and create an empty hash table. Traverse list1. For each element being visited in list1, insert the element in hash table. Traverse list2, for each element being visited in list2, look the element in hash table. If the element is present, then insert the element to result list. If the element is not present, then ignore it.
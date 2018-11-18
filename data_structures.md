# GRAPHS

## 1. How do we define a graph, and where are they commonly used?
Collection of vertices and edges commonly used to define relationship between vertices defined by edges 

## 2. What are the specific attributes that graphs can have, and how do we talk about them?
Weighted, Unweighted, Directed, Undirected


## 3. What are some ways we might store a graph in memory? What space/time complexity problems might we face?
Adjacency Linked Lists



### How do we define a graph mathematically?
G = (V,E)

### What is the difference between directed, undirected, weighted, and unweighted?
Directed: one-way flow
Unidirected: two-way flow
Weighted: Edges have weight
Unweighted: Edges don't have weight

### Give an example of various types of graphs (Weighted Undirected, Unweighted Directed, Unweighted Undirected, etc.)
Wt-Und: Highways
Wt-Dir: Real Life Relationships
Uwt-Und: Facebook
Uwt-Dir: Twitter

### What makes a graph a simple graph? What attributes would make it not simple?
Unweighted, undirected graph containing no graph loops or multiple edges

### What is the maximum number of edges in a directed simple graph? Undirected simple graph? Answer should be in terms of N
E_max = N(N-1), N = number of vertices

### Describe the levels of connectivity a graph can have (strongly connected, weakly connected).
Stongly connected means you can be at any vertex and go to any other vertex


### What are cycles?
When Vertices have multiple paths connecting them 

### What are some naive ways we can store and traverse graphs? Be able to discuss time/space complexity of these approaches, and what issues we may face.
NxN arrays
Adjacency arrays


### Give a high level overview of an Adjacency Matrix
A square matrix that denotes whether an edge exists between two nodes

### If we were only concerned about time complexity, is an Adjacency Matrix efficient? Why/why not?
Yes because to find connections to a single node is O(n) and to find whether an edge exists is O(1)

### If we were only concerned about space complexity, is an Adjacency Matrix efficient? Why/why not?
No because sparsity takes up more space than needed

### Give a high level overview of an Adjacency List
An adjacency list is a 2D array that keeps a graph's vertices and edges data through linked lists


### What benefits do we get from an Adjacency List?
Quicker adding and removal of edge data, accounts for sparsity


### What are the steps for DFS on a graph?
Take first node and add it to a stack, then add one of its connected nodes to the stack and so forth until a node has either connect nodes that have been visited or has no nodes. Go back one node and repeat until all nodes are visited.


### What supporting data structure might you use for BFS and DFS, respectively?
BFS: Queue
DFS: Stack

### What are the steps for BFS on a graph?
1. Take the first node, add it to a queue
2. Add all of the first node's connected nodes and add them to the queue
3. Dequeue the first node and move to the next node
4. Repeat enqueuing of all the next node's connected nodes
5. Repeat dequeue and enqueue until all nodes are visited

### Give an example of a use-case for Topological Sort
Installing file packages with dependencies

### What is a difference between Topological Sort and DFS?
Topological sort prints out vertices in an order where no vertices come before their parent. DFS prints out one node's descendant nodes in succession with no regard to other nodes

### On which types of Graphs can we do a topological sort?


### What data structure do we use to assist with the topological sort algorithm?



### What are the constraints of (any type of) Heap?
all of its nodes are in a specific order and the tree must be complete

### What type of Data Structure might we use to implement a heap?
Priority Queue

### What is the formula for getting the left child of a Heap root node? Right child?
left_i = 2*parent_i+1
right_i = 2*parent_i+2

### What is a Priority Queue?
a Queue where every element/node has a priority associated with it. Items with higher priorities are dequeued before lower priorities and elements with the same priority are deqeueud by age

### What is the time-complexity of Heap Sort?
O(n log(n))

### What are the steps for Heap Sort?
1. Make a max/min heap with an array
2. Swap the last node (A-node) and the root (B-node) in an array
3. Re-heap and repeate for the array but decrement the length by 1


<!-- WEEK 4 -->
## BINARY SEARCH TREE

### What are the constraints of a Binary Search Tree?
the left node of a given node must be less than the given node, and the right node must be greater, and balance trees

### What is the big O lookup time for a value in a binary search tree?
O(log(n))

### How can you find the maximum depth of a BST?
Recursively, pass a node into the function and find the height of the left and right subtree. If a node has no value (the parent has no child node), return 0. Find the max height between the two subtrees and add 1, then go back a level and repeat.

### How can you determine what the Least common ancestor of two nodes is?
recursively, a function takes in a root node and 2 values. if the root node is null, return null. if the root node is equal to either of the values, return he node. otherwise, recursively call the function on node.left with the 2 values and node.right with the 2 values.  if the left and right of a node return values, that node is the ancestor. if the right ad left return null, return null. if a right and left are returned and one of them is null, then return the non-null value.

## AVL TREE

### What is an AVL tree?
A BST that has its left and right children's height differ by no more than 1 and each subtree's left and right children's height differ by no more than 1

### How does an AVL Tree self balance?
Check height values and adjust on inserts while performing necessary rotations
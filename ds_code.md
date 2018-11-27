# Disjoint Set

**Disjoint-set** data structure (also called a union–find data structure or merge–find set) is a data 
structure that tracks a set of elements partitioned into a number of disjoint (non-overlapping) subsets. 
It provides near-constant-time operations (bounded by the inverse Ackermann function) to *add new sets*, 
to *merge existing sets*, and to *determine whether elements are in the same set*. 
In addition to many other uses (see the Applications section), disjoint-sets play a key role in Kruskal's algorithm for finding the minimum spanning tree of a graph.

![disjoint set](https://upload.wikimedia.org/wikipedia/commons/6/67/Dsu_disjoint_sets_init.svg)

*MakeSet* creates 8 singletons.

![disjoint set](https://upload.wikimedia.org/wikipedia/commons/a/ac/Dsu_disjoint_sets_final.svg)

After some operations of *Union*, some sets are grouped together.
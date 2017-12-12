# Weakness of Algorithm

1. Usually don't know how to come up with the brute-force method of DP
2. String DP
3. The speed of DP
4. Handle difficult string pointer
5. Handle difficult string processing      Hot to avoid N^2

### **Tree**

* Morris Traversal Tree
* Suffix Tree 

Application Longest Common Substring [http://www.geeksforgeeks.org/suffix-tree-application-5-longest-common-substring-2/](http://www.geeksforgeeks.org/suffix-tree-application-5-longest-common-substring-2/)

* Prefix Tree

* Segment Tree

* Binary Indexed Tree\(Fenwick Tree\)

A Binary Indexed Tree \(BIT\) is used to store cumulative sums. You have an arraya0, a1, ..., an. You want to be able to retrieve the sum of the firstkelements inO\(logn\)time, and you want to be able to add a quantityqto thei-th element inO\(logn\)time. Note that these two operations can be implemented with a normal array, but the time complexity will beO\(n\)andO\(1\). Tutorial[here](http://community.topcoder.com/tc?module=Static&d1=tutorials&d2=binaryIndexedTrees).

A segment tree \(sometimes called _range tree_\) is a much more flexible data structure, you can use it to store many different things. You have an array a0, a1, ..., an. You want to be able to retrieve the sum \(or the maximum, or the minimum, or the greatest common divisor, or another associative function\) of the elements between the l-th and the r-th in O\(logn\)time, and you want to be able to add \(or to overwrite, or to multiply by...\) a quantity q to the i-th element \(or to _every _element between the l-th and the r-th\) inO\(logn\) time. Tutorial [here](http://community.topcoder.com/tc?module=Static&d1=tutorials&d2=lowestCommonAncestor) and [here](http://www.codeforces.com/blog/entry/3327?locale=en).

* AVL Tree

* B+ Tree

* Red-Black Tree

* Treap

### **Graph**

* Floyd–Warshall

Adjacency Matrix:  [http://www.geeksforgeeks.org/dynamic-programming-set-16-floyd-warshall-algorithm/](http://www.geeksforgeeks.org/dynamic-programming-set-16-floyd-warshall-algorithm/)

[https://cs.stackexchange.com/questions/2942/am-i-right-about-the-differences-between-floyd-warshall-dijkstra-and-bellman-fo](https://cs.stackexchange.com/questions/2942/am-i-right-about-the-differences-between-floyd-warshall-dijkstra-and-bellman-fo)

* Dijkstra 

Adjacency Matrix:  [http://www.geeksforgeeks.org/greedy-algorithms-set-6-dijkstras-shortest-path-algorithm/](http://www.geeksforgeeks.org/greedy-algorithms-set-6-dijkstras-shortest-path-algorithm/)

* Bellman-Ford

Adjacency Matrix:  [http://www.sanfoundry.com/java-program-implement-bellmanford-algorithm/](http://www.sanfoundry.com/java-program-implement-bellmanford-algorithm/)

* Minimum Spanning Tree

\[Prim's\]  Adjacency Matrix: [http://www.geeksforgeeks.org/greedy-algorithms-set-5-prims-minimum-spanning-tree-mst-2/](http://www.geeksforgeeks.org/greedy-algorithms-set-5-prims-minimum-spanning-tree-mst-2/)

\[Kruskal's\]  Adjacency Matrix: [http://www.sanfoundry.com/java-program-find-mst-using-kruskals-algorithm/](http://www.sanfoundry.com/java-program-find-mst-using-kruskals-algorithm/)


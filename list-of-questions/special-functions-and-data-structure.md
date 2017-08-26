# Special Function & Data Structure

### Java: Class, Object and Instance

Object is an instance of class

[https://stackoverflow.com/questions/1215881/the-difference-between-classes-objects-and-instances](https://stackoverflow.com/questions/1215881/the-difference-between-classes-objects-and-instances)

### Java: Initialize an array of objects in Java

Object\[\] obj = new Object\[n\];  //--&gt;  all obj\[ i \] are still null. Need to instantiate them one by one individually.

[https://stackoverflow.com/questions/5889034/how-to-initialize-an-array-of-objects-in-java](https://stackoverflow.com/questions/5889034/how-to-initialize-an-array-of-objects-in-java)

### Heap

Heap can be implemented by **complete binary tree**.

### Square Decomposition

Divide and distribute the responsibilities to subgroups

[http://www.geeksforgeeks.org/sqrt-square-root-decomposition-technique-set-1-introduction/](http://www.geeksforgeeks.org/sqrt-square-root-decomposition-technique-set-1-introduction/)

### Segment Tree

Divide and distribute the responsibilities to subgroups

[https://www.hackerearth.com/practice/notes/segment-trees-for-beginners/](https://www.hackerearth.com/practice/notes/segment-trees-for-beginners/)

leetcode solution sample code

[https://leetcode.com/submissions/detail/112358153/](https://leetcode.com/submissions/detail/112358153/)

### Subsequence vs Subarray/Substring vs Permutation

Subarray/Substring --&gt; Need to be contiguous

Subsequence --&gt; Just need to be in order, don't need to be contiguous

Ex 1234567

subarray/substring --&gt; 3456

subsequence --&gt; 1457

### Prefix Sum

| input nums | 1 | 2 | 3 | 4 | 5 | 6 | ... |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| prefix sums | 1 | 3 | 6 | 10 | 15 | 21 | ... |

### 2 way partition and 3 way partition

2 way moveZeos

3 way sortColors

### Max and Min value of Double

Double.MAX\_VALUE;

-Double.MAX\_VALUE;

### LinkedHashMap

LinkedHashMap&lt;X, Y&gt; map = new LinkedHashMap&lt;&gt;\(int capacity\);

Get the eldest key:

X eldest\_key = map.keySet\(\).iterator\(\).next\(\);

### How to detect cycle in LinkedList

HashMap --&gt; also can get the index which is the start of the cycle

HashSet --&gt; cannot know the index

2 ptr --&gt; can know the index but with some limitations see leetcode [Fraction to Recurring Decimal](https://leetcode.com/problems/fraction-to-recurring-decimal)

### Graph

**Detect Cycle in Directed Graph Algorithm --&gt; DFS\(check if revisited\) or BFS\(toplogical sorting\)**

[https://discuss.leetcode.com/topic/15762/java-dfs-and-bfs-solution](https://discuss.leetcode.com/topic/15762/java-dfs-and-bfs-solution)

**Detect Cycle in Directed Graph Algorithm --&gt; three colors**

[https://www.youtube.com/watch?v=rKQaZuoUR4M](https://www.youtube.com/watch?v=rKQaZuoUR4M&t=110s)

**Detect Cycle in unDirected Graph Algorithm --&gt; Union and check if union two nodes which are already in the same set**

[https://www.youtube.com/watch?v=n\_t0a\_8H8VY](https://www.youtube.com/watch?v=n_t0a_8H8VY)

**Union Find**

[http://algs4.cs.princeton.edu/15uf](http://algs4.cs.princeton.edu/15uf/)

**Connected Graph**

There are two distinct notions of connectivity in a [directed graph](http://mathworld.wolfram.com/DirectedGraph.html). A [directed graph](http://mathworld.wolfram.com/DirectedGraph.html) is [weakly connected](http://mathworld.wolfram.com/WeaklyConnectedDigraph.html) if there is an undirected path between any pair of vertices, and [strongly connected](http://mathworld.wolfram.com/StronglyConnectedDigraph.html) if there is a directed path between every pair of vertices \(Skiena 1990, p. 173\). The following tables summarized the number of weakly and strongly connected digraphs on n=1, 2, ... nodes. The 8 weakly but not strongly connected digraphs on three nodes are illustrated above.

**Euler’s Theorem 1                                                                                  
**If a graph has any vertices of odd degree, then it CANNOT have an EULER CIRCUIT.  
AND  
If a graph is **connected** and every vertex has even degree, then it has AT LEAST ONE EULER CIRCUIT \(usually more\).

**Euler’s Theorem 2                                                                                  
**If a graph has more than 2 vertices of odd degree, then it CANNOT have an EULER PATH.  
AND  
If a graph is **connected** and has exactly 2 vertices of odd degree \(NOTE: or less\), then it has AT LEAST ONE EULER PATH\(or Trail\) \(usually more\). Any such path\(or Trail\) must start at one of the odd-degree vertices and end at the other.

**Euler’s Theorem 3                                                                                  
**The sum of the degrees of all the vertices of a graph is an even number \(exactly twice the number of edges\).  
In every graph, the number of vertices of odd degree must be even.

**Euler Path\(or Trail\)**

An Euler path is a path that uses every edge of a graph exactly once.

**Euler Circuit**

An Euler circuit is a circuit that uses every edge of a graph exactly once.

**Euler Path\(or Trail\) v.s Circuit**

An Euler path starts and ends at **different** vertices.

An Euler circuit starts and ends at the **same** vertex.

### Iterator

`Iterator<Collection> iterator = list.iterator();`

### BackTracking

When using the object as the accumulated tmp, remember to clean it when leaving a route because of the nature of call-by-reference. If use primitive type like int or String, no need to handle that because of the call-by-value property.

When solving backtracking related problems, please try to draw the tree path to find all solutions manually with a simple case at the beginning. It is possible that there might be some re-visted nodes so that time complexity can be reduced by DP.

### Reverse Array

```
for(int i = 0; i < len/2; i++){
//swap
}
```

### Deque

|  | Head | Head | Tail | Tail |
| :--- | :--- | :--- | :--- | :--- |
|  | _Throws exception_ | _Special value_ | _Throws exception_ | _Special value_ |
| **Insert** | [`addFirst(e)`](https://docs.oracle.com/javase/7/docs/api/java/util/Deque.html#addFirst%28E%29) | [`offerFirst(e)`](https://docs.oracle.com/javase/7/docs/api/java/util/Deque.html#offerFirst%28E%29) | [`addLast(e)`](https://docs.oracle.com/javase/7/docs/api/java/util/Deque.html#addLast%28E%29) | [`offerLast(e)`](https://docs.oracle.com/javase/7/docs/api/java/util/Deque.html#offerLast%28E%29) |
| **Remove** | [`removeFirst()`](https://docs.oracle.com/javase/7/docs/api/java/util/Deque.html#removeFirst%28%29) | [`pollFirst()`](https://docs.oracle.com/javase/7/docs/api/java/util/Deque.html#pollFirst%28%29) | [`removeLast()`](https://docs.oracle.com/javase/7/docs/api/java/util/Deque.html#removeLast%28%29) | [`pollLast()`](https://docs.oracle.com/javase/7/docs/api/java/util/Deque.html#pollLast%28%29) |
| **Examine** | [`getFirst()`](https://docs.oracle.com/javase/7/docs/api/java/util/Deque.html#getFirst%28%29) | [`peekFirst()`](https://docs.oracle.com/javase/7/docs/api/java/util/Deque.html#peekFirst%28%29) | [`getLast()`](https://docs.oracle.com/javase/7/docs/api/java/util/Deque.html#getLast%28%29) | [`peekLast()`](https://docs.oracle.com/javase/7/docs/api/java/util/Deque.html#peekLast%28%29) |

### Array &lt;--&gt; List

### \*Only for String or other Object, not for Integer int, Boolean boolean, Character char and other primitive type

array --&gt; list

Arrays.asList\(nums\);

list --&gt; array

num\__list.toArray\(new int\[num\_list.size\(\)_\]\);

### Create List Array

List&lt;Collection&gt;\[\] array = new List\[len\]

### Lookup Data

1.HashMap HashSet

2.**Array** --&gt; all char:  int\[256\]  or  alphabet: int\[26\]     P.S  char is 2 byte in JAVA

### Bit manipulation

1.Get the smallest bit  --&gt;  n & -n

2.Delete the fist rightmost '1'  n&\(n-1\)

3.`>>`is arithmetic shift right,`>>>`is logical shift right. In an arithmetic shift, the sign bit is extended to preserve the sign of the number.

4.if a^b = c  then   a^c = b and  b^c = a

5.~\(1\) is not 0, it is -2

### Primitive type

1. long cannot be dereferenced  but Long can. ==&gt; Because some primitive type is very limited.

2. Integer != int    &lt;int, int&gt; --&gt; error   &lt;Integer, Integer&gt; --&gt; correct

### char &lt;--&gt; int

char --&gt; int:    '8'-'0

int --&gt; char:    \(char\)8+'0'

### List

**LinkedList** \(double linked List\)

add\(int index, E element\)  ---&gt;  \_O\(n/4\) \_average

get\(int index\)  ---&gt; \_O\(n/4\) \_average

**ArrayList  **\(array\)

add\(int index, E element\) ---&gt;  \_O\(n/2\) \_average

get\(int index\)  ---&gt; \_O\(1\) \_average

### **TreeSet**

Floor\(\);

Ceiling\(\);

### StringBuilder

sb.insert\(0, 'c'\)

sb.length\(\);

### String

**Regex Java**

[https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html)

**split**

`"123.".split("\\.") == {"123"}`

`"123".split("\\.") == {"123"}`

`"123.2".split("\\.") == {"123" , "2"}`

**split white space\(one or more\)**

split\("\s+"\)

trim\(\)   --&gt; remove leading and trailing space

**replace**

replace\("str",""\)

**indexOf**

indexOf\("str"\)

### HashMap

[http://www.programcreek.com/2011/07/java-equals-and-hashcode-contract/](http://www.programcreek.com/2011/07/java-equals-and-hashcode-contract/)

The contract between equals\(\) and hashCode\(\) is:

\(1\) If two objects are equal, then they must have the same hash code.

\(2\) If two objects have the same hash code, they may or may not be equal.

The idea behind a Map is to be able to find an object faster than a linear search. Using hashed keys to locate objects is a two-step process. Internally the Map stores objects as an array of arrays. The index for the first array is the hash code of the key. This locates the second array which is searched linearly by using equals\(\) to determine if the object is found.

hashCode\(\)

equals\(\)

### Modulus

Mathematically Speaking, following both are correct:

```
-13 % 64 = -13 (on modulus 64)  
-13 % 64 = 51 (on modulus 64)
```

One of the options had to be chosen by Java language developers and they chose:

**the sign of the result equals the sign of the dividend.**

Says it in Java specs:

[https://docs.oracle.com/javase/specs/jls/se7/html/jls-15.html\#jls-15.17.3](https://docs.oracle.com/javase/specs/jls/se7/html/jls-15.html#jls-15.17.3)

### Comparator by Lambda

1-line: _**expression lambda **_\(in which braces are omitted\)

```
PriorityQueue<Integer> pq = new PriorityQueue<>((o1, o2)->o1-o2);
```

if-else: _**statement lambda** _\(the kind with braces and return\)

```
PriorityQueue<Integer> pq = new PriorityQueue<>((o1, o2)->{
    if(...){
       return o1-o2;
    } else{
       return 0;
    }
});
```

### JAVA 8

map.getOrDefault\(\)


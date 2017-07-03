# Special Function & Data Structure

### Graph

**Euler’s Theorem 1    
**If a graph has any vertices of odd degree, then it CANNOT have an EULER CIRCUIT.  
AND  
If a graph is connected and every vertex has even degree, then it has AT LEAST ONE EULER CIRCUIT \(usually more\).

**Euler’s Theorem 2    
**If a graph has more than 2 vertices of odd degree, then it CANNOT have an EULER PATH.  
AND  
If a graph is connected and has exactly 2 vertices of odd degree, then it has AT LEAST ONE EULER PATH \(usually more\). Any such path must start at one of the odd-degree vertices and end at the other.

**Euler’s Theorem 3    
**The sum of the degrees of all the vertices of a graph is an even number \(exactly twice the number of edges\).  
In every graph, the number of vertices of odd degree must be even.

**Euler Path**

An Euler path is a path that uses every edge of a graph exactly once.

**Euler Circuit**

An Euler circuit is a circuit that uses every edge of a graph exactly once. 

**Euler Path v.s Circuit**

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

### Lookup Data

1.HashMap HashSet

2.**Array** --&gt; all char:  int\[256\]  or  alphabet: int\[26\]

### Bit manipulation

1.Get the smallest bit  --&gt;  n & -n

2.Delete the fist rightmost '1'  n&\(n-1\)

3.`>>`is arithmetic shift right,`>>>`is logical shift right. In an arithmetic shift, the sign bit is extended to preserve the sign of the number.

4.if a^b = c  then   a^c = b and  b^c = a

5.~\(1\) is not 0, it is -2

### Primitive type

1. long cannot be dereferenced  but Long can. ==&gt; Because some primitive type is very limited.

2. Integer != int    &lt;int, int&gt; --&gt; error   &lt;Integer, Integer&gt; --&gt; correct

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

`"123.".split("\\.") == {"123"}`

`"123".split("\\.") == {"123"}`

`"123.2".split("\\.") == {"123" , "2"}`

### HashMap

[http://www.programcreek.com/2011/07/java-equals-and-hashcode-contract/](http://www.programcreek.com/2011/07/java-equals-and-hashcode-contract/)

The contract between equals\(\) and hashCode\(\) is:

\(1\) If two objects are equal, then they must have the same hash code.

\(2\) If two objects have the same hash code, they may or may not be equal.

The idea behind a Map is to be able to find an object faster than a linear search. Using hashed keys to locate objects is a two-step process. Internally the Map stores objects as an array of arrays. The index for the first array is the hash code of the key. This locates the second array which is searched linearly by using equals\(\) to determine if the object is found.

hashCode\(\)

equals\(\)

### Comparator by Lambda

PriorityQueue&lt;Integer&gt; pq = new PriorityQueue&lt;&gt;\(\(o1, o2\)-&gt;o1-o2\);

### JAVA 8

map.getOrDefault\(\)


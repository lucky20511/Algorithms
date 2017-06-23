# Special Function & Data Structure

### Array &lt;--&gt; List

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


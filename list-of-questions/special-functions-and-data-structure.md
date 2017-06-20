# Special Function & Data Structure

### Bit manipulation

1.Get the smallest bit  --&gt;  n & -n

2.Delete the fist rightmost '1'  n&\(n-1\)

3.`>>`is arithmetic shift right,`>>>`is logical shift right. In an arithmetic shift, the sign bit is extended to preserve the sign of the number.

4. 

### Primitive type

* long cannot be dereferenced  but Long can. ==&gt; Because some primitive type is very limited.
* Integer != int    &lt;int, int&gt; --&gt; error   &lt;Integer, Integer&gt; --&gt; correct

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


# Special Function & Data Structure

### **TreeSet**

Floor\(\);

Ceiling\(\);

### StringBuilder

sb.insert\(0, 'c'\)

### HashMap

[http://www.programcreek.com/2011/07/java-equals-and-hashcode-contract/](http://www.programcreek.com/2011/07/java-equals-and-hashcode-contract/)

The contract between equals\(\) and hashCode\(\) is:

\(1\) If two objects are equal, then they must have the same hash code.

\(2\) If two objects have the same hash code, they may or may not be equal.

The idea behind a Map is to be able to find an object faster than a linear search. Using hashed keys to locate objects is a two-step process. Internally the Map stores objects as an array of arrays. The index for the first array is the hash code of the key. This locates the second array which is searched linearly by using equals\(\) to determine if the object is found.

hashCode\(\)

equals\(\)

### Comparator by Lambda

### JAVA 8

map.getOrDefault\(\)




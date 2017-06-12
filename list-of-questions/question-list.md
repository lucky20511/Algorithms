# Good Question List

1. Excel Sheet Column Title  -- Observation of Regularity

2. **\*\*Linked List Cycle II** -- Observation and find the relation of Number

3. Happy Number -- Observation and Take the property of "Cycle"

4. Palindrome Number -- Based on the definition

5. Counting Bits -- Observation of Regularity and Find out the Reused place

6. Single Number II -- bitwise shift about the sign "&gt;&gt;&gt;" and "&gt;&gt;" [http://www.geeksforgeeks.org/bitwise-shift-operators-in-java/](http://www.geeksforgeeks.org/bitwise-shift-operators-in-java/)

7. Max Points on a Line -- When it comes up with fraction, keep it in the lowest term might be the best choice without any distortion, eg. 200000000001/20000000000   and   200000000002/20000000001

8. Ugly Number -- Observation and try not to directly solve the question in a fastest way, try brute force method first.

9. Bulb Switcher -- Math

10. Evaluate Reverse Polish Notation -- Switch can use in String after Java 7

11. Shuffle an Array -- How to copy the array

12. Largest Number -- Comparator of Integer and int array might meet problems,    Hard to get the rule for create the comparator for string

13. K-diff Pairs in an Array -- Write the tree figure for if and else analysis. Need to care about the order of put current number to map

14. Find All Duplicates in an Array -- The limitation of number in array imply it is kind of index. If you want to use a look function table, combining it with original array is a good option. But needs to figure out how.

15. Find the Duplicate Number -- The limitation of number in array imply it is kind of index. There is only one element appear multiple times imply that we only need to find out that number by using the property of cycle.

16. Rotate Array -- Observation

17. First Unique Character in a String --   'a' &gt; 'A'  in ASCII code

18. Gray Code -- Observation the the regular pattern

19. Single Number -- Bit Manipulation on XOR, but that's not enough. Take use of division.

20. Top K Frequent Elements -- After put into the hashMap, we can sorted by \(1\)Sorted the tree by replace the key to the frequency and put to treemap \(2\) put the entry of map into priority queue and override the comparator, and the **BEST method** \(3\)put the hashmap into array in the index of frequency, because the frequency has the range \[1 : nums.length\]

21. Search a 2D Matrix II -- Try to figure out to make search direction "one-way" ==&gt; exactly the same as 3-sum

22. Additive Number -- Observe that only two first element has multiple possible way. The left steps are unique path.

23. Isomorphic Strings -- S want to map to T, T also want to map to S. Why not S and T map a same unique number. So we can easily check if the S and T are 2gether. Here index is that unique and trivial number we can use.

24. Find Peak Element -- If there is some "directional" feature, try to think about Binary Search

25. Trapping Rain Water -- Hint: if leftmost bar is 2 right most bar is 3, every bar in between which is lower than 2 can contains water

26. Trapping Rain Water II -- Same idea as Trapping Rain Water. Start from the lowest edge. How to start the edge in the order of height ? by Priority Queue.

27. Majority Element -- Take use of the property, that element appears more than \[n/2\] times. Means if we do a game of deletion, it will survive at the end.

28. Majority Element II -- Take use of the property. If we play a game of deletion with two number at a time, these two "might" survive at the end. So we also need to check their validity respectively.

29. Gas Station \(Similar with Maximum Subarray\) -- \(1\) If car starts at A and can not reach B. Any station between A and B can not reach B.\(B is the first station that A can not reach. \(2\) If the total number of gas is bigger than the total number of cost. There must be a solution.

30. Set Matrix Zeroes -- First method is using mask with O\(mn\) space. Another is using the hashset, array or other to store the state of each row and col with O\(m+n\). The best solution for space complexity is store the state of each col and row just in the origin table.  However, we need to create a extra variable for first row or first col because of "overlap".

31. Different Ways to Add Parentheses -- Figure out how to group the numbers because the description is not so clear. Then figure out what is the terminating condition and how to handle it.

32. 



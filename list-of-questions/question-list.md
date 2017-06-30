# Good Question List

1. Excel Sheet Column Title  -- Observation of Regularity

2. **\*\*Linked List Cycle II** -- Observation and find the relation of Number.Cycle --&gt; can use  \(1\)slow and fast ptr or \(2\)Map in which value is the position index ,  to detect if there is a cycle and the starting point of cycle. **Please remember how to detect the starting point of cycle by two pointers!!!**

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

20. **Top K Frequent Elements** -- After put into the hashMap, we can sorted by \(1\)Sorted the tree by replace the key to the frequency and put to treemap \(2\) put the entry of map into priority queue and override the comparator, and the **BEST method** \(3\)put the hashmap into array of list in the index of frequency, because the frequency has the range \[1 : nums.length\]

21. Search a 2D Matrix II -- Try to figure out to make search direction "one-way" ==&gt; exactly the same as 3-sum

22. Additive Number -- Observe that only two first element has multiple possible way. The left steps are unique path.

23. Isomorphic Strings -- S want to map to T, T also want to map to S. Why not S and T map a same unique number. So we can easily check if the S and T are together. Here index is that unique and trivial number we can use.

24. Find Peak Element -- If there is some "directional" feature, try to think about Binary Search

25. Trapping Rain Water -- Hint: if leftmost bar is 2 right most bar is 3, every bar in between which is lower than 2 can contains water

26. Trapping Rain Water II -- Same idea as Trapping Rain Water. Start from the lowest edge. How to start the edge in the order of height ? by Priority Queue.

27. Majority Element -- Take use of the property, that element appears more than \[n/2\] times. Means if we do a game of deletion, it will survive at the end.

28. Majority Element II -- Take use of the property. If we play a game of deletion with two number at a time, these two "might" survive at the end. So we also need to check their validity respectively.

29. Gas Station \(Similar with Maximum Subarray\) -- \(1\) If car starts at A and can not reach B. Any station between A and B can not reach B.\(B is the first station that A can not reach. \(2\) If the total number of gas is bigger than the total number of cost. There must be a solution.

30. Set Matrix Zeroes -- First method is using mask with O\(mn\) space. Another is using the hashset, array or other to store the state of each row and col with O\(m+n\). The best solution for space complexity is store the state of each col and row just in the origin table.  However, we need to create a extra variable for first row or first col because of "overlap".

31. Different Ways to Add Parentheses -- Figure out how to group the numbers because the description is not so clear. Then figure out what is the terminating condition and how to handle it.

32. Lexicographical Numbers -- Has \(1\)Recursive and \(2\)Iterative methods. Need to find out the regularity by observation and carefully handle the corner cases like '9'.

33. Missing Ranges -- Need to care about the corner cases like empty array or Integer.MAX\__VALUE & Integer.MIN_\_VALUE

34. Compare Version Numbers -- Need to carefully handle this problem. Need to Know following things:

    1. `"123.".split("\\.") == {"123"}`

    2. `"123".split("\\.") == {"123"}`

    3. `"123.2".split("\\.") == {"123", "2"}`

35. Fraction to Recurring Decimal -- Pretty Hard. Need to take care the value &lt; 0. Don't take the "digit" to evaluate the repeating. Use the reminder of each iteration to evaluate the if the repeating happens. It's hard to use two pointer to solve this question. Although 2 ptr has the ability to find out the start point of repeating, it is not able to know exactly which part is repeating. Therefore, Use the HashMap to record the reminder of each iteration in which key--&gt;reminder   and  value--&gt;index

36. Elimination Game -- Need to Observe to find out \(1\) The last remaining is head \(2\) the rule of updating head

37. Longest Substring Without Repeating Characters -- Using the idea of Sliding window. The concept of sliding window is to reduce the redundant iteration \(e.g if 1~5 is invalid, 1~6, 1~7 and 1~N, N&gt;5 is also invalid\). Keep moving one pointer\(tail\) till the end of array. When the subarray becomes invalid, move another pointer\(head\) till the array is back to valid status. Then update the ret value.

38. Longest Substring with At Least K Repeating Characters -- It's pretty hard to solve this question within N^2 time complexity. Fortunately, there is a "lower case" condition. It's very powerful condition. Therefore, we can know that there is at most 26 unique at least K repeating characters. We now can solve tshis question by solving the sub-problem "Longest Substring with At Least K Repeating Characters and N Unique Characters" and traverse N from 1 to 26.

39. Longest Substring with At Most Two Distinct Characters -- We need to use the concept of Sliding window to reduce the redundancy of each iteration or remove some redundant iterations. There is two methods to keep the record of appearance of previous data: One is Map, another is two pointers. In this case two pointers is enough because there is at most two distinct characters. One pointer p1 is to represent current head. Another pointer p2 is to represent the first element among the latest unique character, e.g "eceeee'c'cc" p2 is at the position of the the 'c'. Then find the proper moment to \(1\)update the p2 \(2\) update the p1 and \(3\) update the return value.

40. Longest Substring with At Most K Distinct Characters -- Same as the case of two distinct characters. However, we can choose the Map to store the appearance record of previous characters.

41. Wiggle Sort -- Firstly, it is easy to come up with a solution by sort and reorder. However, that solution is complicated and with big time complexity. Try to run some easy idea. Then get a very simple idea which is different from the previous complex idea.

42. Number Complement -- Calculate it bit-by-bit by shifting it right and using 1 as mask and add it back by shifting the new bit left. Calculate the bit from small to large, that is right to left. Terminate when the number of shift bit is larger than the number itself.

43. Maximum XOR of Two Numbers in an Array -- Initially, I thought about some method like tree. However, it's not easy to figure out how. With Trie, we can try each numbers in array with trie. The complexity would be only O\(31N\) which is still O\(N\). Or there is another smart method. We can try to find the max value by adding the bit one-by-one from left to right which is from large to small and try to find out if there exist a pair that can make this max happen.

44. Pascal's Triangle II -- To modify the value in-place, we should modify the value from right to left in which we update the value by s\[j\] = s\[j\]+s\[j-1\]  where j = 1~ i-1  in ith layer.

45. Queue Reconstruction by Height -- Firstly come up with a idea that always find the head and update the rest people whose height is shorter than that head. Then keep doing that till the end.  Secondly, need to observe that if your group people with the same height from tall to small, you can find that the index is equal to the position index in which that people should be inserted!!!!!! It's not easy to find out!

46. Reverse Linked List II -- Very important problem which can be solved by using 3 pointers \(dummy exclusive\). Need to think about this problem often and compare with Reverse Linked List.

47. Flatten Binary Tree to Linked List -- **Super hard!!!!!!!!!!!**

48. Minimum Moves to Equal Array Elements -- After observation, figure out what the arithmetic equation is and solve it as a math question.

49. Keyboard Row -- We definitely need a data structure to allow us look up the character. We can use array with 256 size as a look up table which is similar with question "Isomorphic Strings".

50. Moving Average from Data Stream -- Could solve by LinkedList or Array respectively.

51. Sliding Window Maximum -- Need to think about how to update the maximum value within linear time instead of O\(KN\). Then find that we need to put the index into a double queue instead of using value.

52. Reverse String III -- Do you best to find all corner cases and make sure your 2-pointer algorithm can cover all of them.

53. Reverse String II -- Find out all corner cases and make sure your 2-pointer algorithm can cover all of them.

54. Reverse Words in a String -- Find out all corner cases and make sure your 2-pointer algorithm can cover all of them.

55. Reverse Words in a String II -- The same with "Reverse Words in a String" but much easier because of less edge cases.

56. Bitwise AND of Numbers Range -- Need to observe and find out that only need to find the same digits from the left and stop at first different digit.

57. Search in Rotated Sorted Array -- Find all cases and summarize it

58. Search in Rotated Sorted Array -- Find the edge cases and figure out it cannot be treated as Binary Search. Therefore, when that happens, linearly decrement the end.

59. Restore IP Addresses -- Backtracking. Need to carefully check if substring is valid and try to prune the search tree.

60. Ugly Number II -- Need to observe, observe and observe!!!!!! Need to find out the rule within this!

61. Palindrome Partitioning -- When drawing the tree flow, find there were lots of revisited node in the tree and can be implemented by bottom up DP. Need to know that the list of array should be created by List&lt;&gt;\[\] list = new List\[len\]

62. Count Univalue Subtrees -- When doing the recursion by helper, DO NOT put the multiple helper into if\(\) condition cuz it may not be executed, e.g if\(helper\(A\) \|\| helper\(B\)\)

63. Add Two Numbers II -- Need to be careful about the carry and the order of list. Since the lists are reversed, we can either 1. reverse them and reverse back or 2.use stacks.

64. Rotate List -- When rotate the list, except for adding a link from tail to head, don't forget to break the link which is linking to new head. Please be careful.

65. 
66. Power of Four -- Observe and analyze the property of the power of four "gradually" and write down all of them one-by-one.

67. 



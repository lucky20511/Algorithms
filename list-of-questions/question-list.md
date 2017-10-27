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

16. Rotate Array -- Observation  the rule. HARD

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

38. Longest Substring with At Least K Repeating Characters -- It's pretty hard to solve this question within N^2 time complexity. Fortunately, there is a "lower case" condition. It's very powerful condition. Therefore, we can know that there is at most 26 unique at least K repeating characters. We now can solve this question by solving the sub-problem "Longest Substring with At Least K Repeating Characters and N Unique Characters" and traverse N from 1 to 26.

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

61. **Palindrome Partitioning** -- When drawing the tree flow, find there were lots of revisited node in the tree and can be implemented by bottom up DP. Need to know that the list of array should be created by List&lt;&gt;\[\] list = new List\[len\]. However, the DP solution is with huge space complexity. The backtracking with top down method is relatively with much lower space complexity. For this problem, **backtracking** seems to be a better choice here.

62. Count Univalue Subtrees -- When doing the recursion by helper, DO NOT put the multiple helper into if\(\) condition cuz it may not be executed, e.g if\(helper\(A\) \|\| helper\(B\)\)

63. Add Two Numbers II -- Need to be careful about the carry and the order of list. Since the lists are reversed, we can either 1. reverse them and reverse back or 2.use stacks.

64. Rotate List -- When rotate the list, except for adding a link from tail to head, don't forget to break the link which is linking to new head. Please be careful.

65. Kth Smallest Element in a Sorted Matrix -- Just like the problem "Find K Pairs with Smallest Sums". Think about it. It's easy.

66. Power of Four -- Observe and analyze the property of the power of four "gradually" and write down all of them one-by-one.

67. Flatten 2D Vector --  When meet complex if else condition, please draw the** tree digram** first for clarification first instead of jumping into the code immediately.

68. Reconstruct Itinerary -- Pretty hard problem. Need to understand the Euler path and circuit and its background knowlege first. If there is a circuit, you just walk through the path by lower lexical order and then you can reach every node anyway. However, if there is no circuit but path, means there are exactly "two node" with odd degree\(according to Euler theorem\). If you meet that node and there's no possible road to go ahead, u can just move back till find the another possible path.

69. Word Ladder -- We can recognize it as graph question after drawing the diagram. And we choose the BFS instead of DFS because the question is ask about "shortest path". The BFS will be the proper way to get the shortest path. And we also aware that there shouldn't be a "cycle" because the path we want is the "shortest" one. If the cycle must be redundant. So we create a set to keep the record of which nodes we haven't reached. We won't visit a node more than once by that set.

70. Median of Two Sorted Arrays -- Need to use the two pinters as the "lower bound" of the bigger part to calculate. Two pointer must be in the same part \(bigger part\).

71. Task Scheduler -- Need to find the rule and solve it in math way.

72. Rearrange String K Distance Apart -- Greedy. Insert char which is valid and with largest count.

73. Reorder List -- Divide the problem into multiple sub-problems. 1\)Split the list into First half and Second half parts and remember to separate them by null pointer, 2\)Reverse the second part, 3\)Merge two parts.  Need to handle the list operations carefully.

74. Sort Characters By Frequency -- When it comes to the frequency of element, create &lt;element, freq&gt;, then create &lt;freq, List&lt;element&gt;&gt;. The frequency must be smaller than the len. We can sort it from 0 ~ len or len ~ 0. No need sort. We can select Array rather than Map \(or you can use Map, doesn't matter. We only need a data structure to keep the data for loop up\). Remember to create a array of list by List&lt;Collection&gt;\[\] array = new List\[len\];

75. Binary Watch -- Need to know how to do the combination and how to handle the terminating condition. In this we can ignore the some bad conditions of backtracking, because they will end by itself.

76. Rotate Function -- Find brute force method first which is O\(N^2\) in time complexity. Then try to figure out how to reduce the redundancy between each iteration. Successfully find out how to reduce the redundancy and improve the time complexity to O\(N\).

77. Maximum Product of Three Numbers -- Draw the diagram to find the rule. By observation, found that we need the max and min for only one element and max and min for two elements and max for three elements. Update them from three to one.

78. Count Numbers with Unique Digits -- Math problem of Combination.

79. Maximum Distance in Arrays -- The max distance must come from the first element and last element. Need to figure out how to avoid that the first and last element come from the same list.

80. Decode Ways II - First, Backtracking. Second find out the repeated node and the optimal substructure. Optimal substructure might be complex. Try to find the whole optimal substructure in all cases. Then, fill up the initial conditions. Finally solve this problem in bottom-up way.

81. Linked List Random Node -- **Reservoir Sampling!**

82. Relative Ranks -- Need to figure out how to get the original index of each element after sorting. It can be achieved by sorting the value and original index together but only regarding the value to sort.

83. Shortest Word Distance -- Need to find out possible edge case first! Need to understand why the time complexity can be reduced from O\(N^2\) to O\(N\).

84. Diagonal Traverse -- Observe the rule with patient and need to write the any idea down.

85. Diameter of Binary Tree -- observe \(1\) when to update the return value, \(2\) what information need to be returned to its parent node and \(3\) terminating conditions.

86. Largest Divisible Subset -- Almost the same as Longest Increasing Sequence \(LIS\) problem. First draw the searching tree diagram. Second, try to observe and get some rule among that. Then find out the "concept" optimal substructure. Finally, think about how to implement the bottom up method and what data structure we need to achieve that.

87. Shortest Word Distance II -- Organize the information into data structure for repeated use. Although it cannot reduce the time complexity, it can save some time.

88. Binary Tree Zigzag Level Order Traversal -- Try to think the original one and focus only on the difference between them first. Then try to solve the problem with the least difference from the original solution.

89. Palindrome Permutation -- Observe the rule, and figure out a solution to that. Then try to figure out how to reduce the space complexity of that.

90. Generalized Abbreviation -- Backtracking first and check if there are any space for DP.

91. Delete Node in a BST -- Not Easy. Try to solve in recursion way.

92. Sum Root to Leaf Numbers -- Need to observe the terminating problem carefully and write them down.

93. Find Mode in Binary Search Tree -- Need to realize that the node with same val will be consecutive together. It is also true when traverse it in-order like 1222333444555. Need to figure out to use "inorer" traversal. Try to think about "BST & sorted --&gt; inorder traversal".  Moreover, need to know the difference between list = new ArrayList&lt;&gt;\(\) and list.clear.

94. Next Greater Element I -- Try to come up with a brute force method first, even though this final solution is a little bit irrelevant to the brute force method. Try to reduce the time complexity from O\(N^2\) to O\(N logN\) or O\(N\). Finally, figure out a solution which only needs to walk through all elements once and store them in to data structure which can provide O\(1\) look up. Then just use this data structure to get the solution for each element of findNums\(nums1\).

95. Evaluate Division  --  Using the Similar idea as the Union find. Find the common divisor.

96. Course Schedule I  -- It's a problem of how to detect a cycle in a directed problem. One solution is traverse this directed graph by topological sorting and see if we can traverse each of node. It is kind of BFS method. The other DFS method is doing the backtracking traversal for start from each node. And for each node, try to do the DFS and see if there is a revisited in nodes in any searching line. Remember to reset the condition when leaving a searching line during backtracking.

97. Course Schedule II -- It is exactly a problem of topological sorting.

98. Course Schedule III --

99. Arithmetic Slices -- Using two pointers but needs to know the timing of updating each status.

100. Design Hit Counter -- Need to know we only need to use array with length 300 to keep the data within 300 sec. Any data will probably be removed after 300 second. Assign value like array\[time%300\];

101. Wiggle Subsequence -- Need to observe the rules by brute force method backtracking searching tree. Then you will find out there are lots of useless path. You only needs to search one path. Also need to find out the initial direction is decided by the graph already. Please need to know how to prove these things above.

102. Valid Triangle Number -- Very beautiful problem. The brute force method would be N^3. After doing the sorting, we try to figure out how to reduce the time complexity to N^2 by the property of sorted array. We understand the conditions make these to length a triangle is the "**sum of any two sides is larger than the other side**". Now the array is sorted so we can rephrase it to be the "**sum of two smaller side is larger than the biggest one**". So given a biggest side we need to find the number of all possible two sides whose sum are larger than that biggest side. The idea is very similar as **two sum**.

103. Wiggle Sort II -- The original idea is divide the data into two groups, small and big. Put the small into even or odd and put the big into another. However, we need to take care of there might be multiple numbers with the same value as median. To achieve this, the core idea is that divide the data into three parts: \(1\) &gt; median, \(2\) &lt; median and \(3\) = median. There might be two main task \(1\) how to find the median and \(2\) how to arrange those data for each three parts. For \(1\) we could use quick select to easily get the Kth wanted value from a array in O\(n\). For \(2\), we want to arrange the data by putting &lt; median part starts from the head of even position and putting &lt; median starts from the tail of even position and leave the =median to the rest empty position. Further, we can transform the index of   0123456 to --&gt; 0246135, then task of arrangement would become 3 way partition \(sort colors\) problem which is quite straightforward.

104. Maximum Average Subarray I -- Very easy. Just observe.

105. Maximum Average Subarray II -- Still don't know the why the condition of remove the index data store in the queue from the tail.

106. Longest Palindromic Subsequence -- Unlike other dp problem,tThe searching diagram is very special. Need to know how to draw the searching diagram of this kind of problem.

107. Path Sum III -- When analyzing the return conditions, we discover that we might needs two kind of recursion function to achieve this, First is count the number of path  including current root. Second is count the number of path according to current value, if meet the root.val is current left target, then +1 and keep counting the left and right. The second function is regardless of the start node of this path, just count. But First need to make sure we count all path started from each node. So this kind of multiple combination recursion function might be very complex for me. Need more practice on **multiple combination recursion problem**. The solution above is with the O\(N^2\) in time complexity. Try to reduce it to lower. Then we have the idea of prefix sum. But the path needs to be contiguous and from top to bottom, there we need to use \(1\)preorder, and \(2\) remove all the current node information when leaving this branch and ready to return so that the path information from top to bottom would only be left. And if we meet the same prefix sum value, just increment the value with the same prefix key.

108. Serialize and Deserialize BST -- We need to put the root in the first place, so there are only two methods, \(1\) BFS  and  \(2\) DFS

109. Mini Parser -- Observe the rule and repeated part. Divide the problem into small subproblems.

110. Pacific Atlantic Water Flow -- Observe we need to  do DFS search from pacific and atlantic. Then find the intersection area. Start from pacific, and mark the visit array to 'p'. Then start from atlantic and mark the visit to 'a'. If meet the 'p' when doing 'a', it means current node is intersection. Add that node to return list and change the visit to 'a'. Keep doing DFS till the end.

111. Unique Path -- Find the revisited node. Try DP.  Find the optimal substructure so use bottom-up. Here we further reduce the space complexity from O\(N^2\) to O\(N\).

112. Unique Path II -- Similar to above problem. But need to notice that when current position is obstacle, set it to zero anyway.

113. Construct the Rectangle -- very simple. Notice this: try to use "mid &lt; area/mid" not to use "mid\*mid &lt; area" which is easy to overflow.   why???????????

114. Nth Digit -- if you want to find out which groups and which position current number N belongs, you can use \(N-1\)/size to find out the group and \(N-1\)%size to find out the position.

115. 4 sum II -- The brute force method would be O\(N^4\). Figure the difference between 4 sum and 4 sum II. In 4 sum II, each value is separate in 4 different 4 set so the selection of each value wouldn't affect other, their for we could divide N^4 to N^2 \* N^2  and the latter could be improved by using the hashmap so that the compleixty N^2 \* N^2 would be N^2 \* 1 which is O\(N^2\)

116. Range Sum Query - Mutable -- The normal method would be O\(N\) in time complexity. Try to divide and distribute the computation cost by using segment Tree.

117. Find K closest Elements -- There are three possible solutions: \(1\) O\(NLog N\), \(2\) O\(N\) \(3\) O\(Log N\). For the third binary search solution, need to think about how to apply binary search for following situations \(1\) 1 2 3 4 5 \(2\) 5 4 3 2 1 \(3\) 3 2 1 2 3

118. Frog Jump -- Cannot do it in bottom up method. So solve it top-down.

119. Backpack\(LintCode\) -- be careful the hole because the array is not sorted.

120. Largest Palindrome Product -- Need to come up with the brute force method

121. 



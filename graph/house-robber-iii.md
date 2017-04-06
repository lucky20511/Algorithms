## **Description**

The thief has found himself a new place for his thievery again. There is only one entrance to this area, called the "root." Besides the root, each house has one and only one parent house. After a tour, the smart thief realized that "all houses in this place forms a binary tree". It will automatically contact the police if two directly-linked houses were broken into on the same night.

Determine the maximum amount of money the thief can rob tonight without alerting the police.

**Example 1:**

```
     3
    / \
   2   3
    \   \ 
     3   1
```

Maximum amount of money the thief can rob = 3 + 3 + 1 = **7.**

**Example 2:**

```
     3
    / \   
   4   5
  / \   \ 
 1   3   1
```

Maximum amount of money the thief can rob = 4 + 5 = **9**.

## Thinking

Taking the following tree as the example, I tried to plot the searching tree for all possible solution.

```
    3
   / \
  4   5
 / \ 
1   3  
```

After plotting the searching tree diagram, It should be like the following:

```
                 
                   max
               /         \
              3o          3x
              +            +
            /  \        /     \
          4x   5x     max       max
          +         /    \      / \
        /  \       4x     4o   5x 5o
      max  max     +       +
     / \   / \    / \     / \
    1o 1x 3o 3x max max  1x  3x 
                / \  / \
               1o 1x 3o 3x

```

We could see that the code






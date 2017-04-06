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

We could see find two things:

\(1\) There are some reused nodes such as 4x.

\(2\) It exists the optimal substructure, because of \(1\) and the fact that the cost value of upper node only depends on node of lower level.

Therefore, we could solve this by **bottom up** method of DP. We just keep it in mind temporarily.



We need to decide how to create the different nodes of selected or non-selected, like 3x 3o. There are two ways.

 First is that you just create two different nodes for selected and non selected. 

Second is that you just skip the non-selected one.

It seems that the latter would be much better, because you don't need create a node that you don't need.

The following is the code of the above idea which is without DP:

```java
public class Solution {
    public int rob(TreeNode root) {
        if(root == null){
            return 0;
        }
        int count_cur_layer = root.val;
        if(root.left != null){
            count_cur_layer += rob(root.left.left) + rob(root.left.right);
        }
        if(root.right != null){
            count_cur_layer += rob(root.right.left) + rob(root.right.right);
        }
        return Math.max(count_cur_layer, rob(root.left)+rob(root.right));
    }
}
```

However, there is still lots overlap tree node like 4x. It's time to introduce the DP to improve the time complexity.

The one method is we just introduce the Map to store the value which we already calculated.



There is still another method which take the use of the property of DFS tree traversal.

The following is that method.

By observation, we can see the following object

```
    max
    / \
   3o 3x
```

as a node. It is better than taking 3o or 3x as two different nodes.

The following is the code with DP:

```java
public class Solution {
    public int rob(TreeNode root) {
        int[] res = Helper(root);
        return Math.max(res[0], res[1]);
    }

    private int[] Helper(TreeNode node){
        int[] ret = new int[2];
        if(node == null){
            return ret;
        }
        int[] left = Helper(node.left);
        int[] right = Helper(node.right);
        ret[0] = Math.max(left[0], left[1]) + Math.max(right[0], right[1]);
        ret[1] = left[0] + right[0] + node.val;

        return ret;
    }
}
```



If you take the 3x or 3o as a single node and do not skip the 3x, the code with DP would become:

```java
public class Solution {
    public int rob(TreeNode root) {
        Map<TreeNode, Integer> map_true = new HashMap<TreeNode, Integer>();
        Map<TreeNode, Integer> map_false = new HashMap<TreeNode, Integer>();
        return Math.max(Helper(false, root, map_true, map_false), Helper(true, root, map_true, map_false));
    }

    private int Helper(boolean if_select, TreeNode node, Map<TreeNode, Integer> map_true, Map<TreeNode, Integer> map_false){
        if(node == null){
            return 0;
        }

        int left_count = 0, right_count = 0;
        if(!if_select){
            if(map_false.containsKey(node)){
                return map_false.get(node);
            }
            left_count = Math.max(Helper(false, node.left, map_true, map_false), Helper(true, node.left, map_true, map_false));
            right_count = Math.max(Helper(false, node.right, map_true, map_false), Helper(true, node.right, map_true, map_false));
            map_false.put(node, left_count + right_count);
            return left_count + right_count;
        }else{
            if(map_true.containsKey(node)){
                return map_true.get(node);
            }
            left_count = Helper(false, node.left, map_true, map_false);
            right_count = Helper(false, node.right, map_true, map_false);
            map_true.put(node, left_count + right_count + node.val);
            return left_count + right_count + node.val;
        }

    }
}
```




# 要求
给定一个二叉树，找出其最大深度。

二叉树的深度为根节点到最远叶子节点的最长路径上的节点数。

**说明**: 叶子节点是指没有子节点的节点。

**注意**
0 ≤ x, y < 2<sup>31</sup>.
<p><h4>示例</h4>
给定二叉树 [3,9,20,null,null,15,7]，
	<pre>
    3
   / \
  9  20
    /  \
   15   7
	</pre>
<p/>
返回它的最大深度 3 。
————————————————————————————————————

**C++**
<pre>
<code>
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    int maxDepth(TreeNode *root) {
        if(!root) return 0;
        int leftDepth = maxDepth(root -> left) + 1;
        int rightDepth = maxDepth(root -> right) + 1;
        return max(leftDepth, rightDepth);
    }
};
</code>
</pre>

**JAVA**
<pre>
<code>
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    public int maxDepth(TreeNode root) {
            if(root == null)
                return 0;
            else if (root.left==null&&root.right==null)
                return 1;
            else{
                int leftDepth = maxDepth(root.left);
                int rightDepth = maxDepth(root.right);
                if(leftDepth>rightDepth)
                    return leftDepth +1;
                else
                    return rightDepth +1;
            }
        }
}
</code>
</pre>
### 解释
遍历

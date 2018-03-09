#  Path Sum II
## 问题分析：
求二叉树路径之和还要找出路径,需要用深度优先搜索DFS和二维的vector
## 编程实现：
```C++
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
    vector<vector<int> > pathSum(TreeNode *root, int sum) {
        vector<vector<int>> res;
        vector<int> out;
        helper(root,sum,out,res);
        return res;
    }
    void helper(TreeNode* node,int sum,vector<int>& out,vector<vector<int>>& res)
    {
        if(!node) return;
        out.push_back(node->val);
        if(sum==node->val && !node->left && !node->right)
        {
            res.push_back(out);
        }
        helper(node->left,sum-node->val,out,res);
        helper(node->right,sum-node->val,out,res);
        out.pop_back();
    }
};
```

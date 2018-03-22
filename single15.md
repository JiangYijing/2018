# Binary Tree Inorder Traversal
## 问题分析：
二叉树中序遍历,对左右子节点分别使用递归函数,根节点访问值
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
    vector<int> inorderTraversal(TreeNode* root) {
        vector<int> res;
        inorder(root,res);
        return res;
    }
    void inorder(TreeNode *root, vector<int> &res) {
        if(!root) return;
        if(root->left) inorder(root->left, res);
        res.push_back(root->val);
        if(root->right) inorder(root->right, res);
    }
};
```        

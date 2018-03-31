# Sum Root to Leaf Numbers 
## 问题分析：
二叉树，运用递归，用参数传递保存前面的值
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
    int sumNumbers(TreeNode* root) {
    int sumAll(TreeNode *root,int sum) {  
        if(root==nullptr) return 0;
        if(root->left==nullptr && root->right==nullptr)  
            return sum*10+root->val;
        else  return sumAll(root->left, sum * 10 + root->val)  +sumAll(root->right, sum * 10 + root->val);  
    }  
};  
int main()  
{  
    TreeNode root(0);  
    TreeNode *r;  
    TreeNode l1(6);  
    TreeNode l2(2);  
    TreeNode r1(4);  
    TreeNode r2(5);  
    r=&root;  
    root.right=&r1;  
    root.right->right=&r2;  
    root.left=&l1;  
    root.left->left=&l2;  
    Solution solu;  
    cout<<solu.sumNumbers(r)<<endl;  
    return 0;  
 }  
}
```

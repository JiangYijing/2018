#Populating Next Right Pointers in Each Node
## 问题分析：
树的层序遍历,完全二叉树所以左节点存在则右节点也存在,利用递归解决
## 编程实现：
```C++
/**
 * Definition for binary tree with next pointer.
 * struct TreeLinkNode {
 *  int val;
 *  TreeLinkNode *left, *right, *next;
 *  TreeLinkNode(int x) : val(x), left(NULL), right(NULL), next(NULL) {}
 * };
 */
class Solution {
public:
    void connect(TreeLinkNode *root) {
        if(!root) return;
        if(root->left)  root->left->next=root->right;
        if(root->right) root->right->next=root->next? root->next->left : NULL;
        connect(root->left);
        connect(root->right);
    }
};

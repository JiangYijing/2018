# Sum Root to left numbers
## 问题分析:
考察树的用法,使用递归,利用先序遍历解决,主要需要考虑递归条件和结束条件。
## 编程实现:
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
        if(!root)
            return 0;
        sum=0;
        DS(root,0);
        return sum;
    }
    void DFS(TreeNode *&temp,int currentSum)
    {
        currentSum=currentSum*10+temp->val;
        if(!temp->left&&!temp->right)
            sum+=currentSum;
        if(temp->left)
            DS(temp->left,currentSum);
        if(temp->right)
            DS(temp->right,currentSum);
    }
private:
    int sum;
};
```

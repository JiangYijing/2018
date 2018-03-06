# Rotate List
## 问题分析：
旋转链表,链表值只能一个一个访问,用快慢指针来解但是要考虑各种的特殊情况
## 编程实现：
```C++
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode* rotateRight(ListNode* head, int k) {
        if(!head) return NULL;
        int n=0;
        ListNode *cur = head;
        while(cur) 
        {
            ++n;
            cur=cur->next;
        }
        k%=n;
        ListNode *fast=head, *slow=head;
        for(int i=0;i<k;++i) 
        {
            if(fast)fast=fast->next;
        }
        if(!fast) return head;
        while(fast->next)
        {
            fast=fast->next;
            slow=slow->next;
        }
        fast->next=head;
        fast=slow->next;
        slow->next=NULL;
        return fast;
    }
};
```

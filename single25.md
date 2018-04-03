# Reorder List
## 问题分析：
重排链表,注意不能改变节点的值,所以考虑将链表反转再重新连接
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
     void reorderList(ListNode *head) 
     {
         if(head==NULL||head->next==NULL)
             return;
        ListNode *preSlow=NULL;
         ListNode *slow=head,*fast=head;
        while(fast&&fast->next)
         {
             preSlow=slow;
             slow=slow->next;
             fast=fast->next->next;
         }  
         preSlow->next=NULL; 
         ListNode *newBeg=slow;
         ListNode *last=newBeg->next;
         while(last)
         {
             ListNode *temp=last->next;
             last->next=newBeg;
             newBeg=last;
            last=temp;
         }
         slow->next=NULL;
 
         //合并
         fast=head;
         preSlow=NULL;
         while(fast) //注：以前半段为条件
         {
             ListNode *tem=newBeg->next;
             newBeg->next=fast->next;
             fast->next=newBeg;
             fast=newBeg->next;
             preSlow=newBeg;
             newBeg=tem;
         }
         if(newBeg !=NULL)   //因节点个数为奇数时，后段比前段多一个，所以最后要判断
             preSlow->next=newBeg;
     }
 };
 ```

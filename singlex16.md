# Merge Sorted Array
## 问题分析：
将两个有序的数组合并到一个数组中,从结尾开始归并,使不会覆盖元素
## 编程实现：
```C++
class Solution {  
public:  
    void merge(int A[],int m,int B[],int n) {  
        int i,j,k;  
        for(i=m-1,j=n-1,k=m+n-1;k>=0;--k)  
        {  
            if(i>=0&&(j<0||A[i]>B[j]))  
            {  
                A[k]=A[i--];  
            }  
            else A[k]=B[j--];  
        }  
    }  
};  
```

# Pascal's Triangle II
## 问题分析
杨辉三角，但只需返回给给定行的数组，需要返回数组长度数组,动态内存分配
两层循环，第一层代表行数，第二层代表列数,此算法涉及数组元素的替换，内层循环需要逆序遍历，否则会改变要相加的元素
## 编程实现
```C++
/**
 * Return an array of size *returnSize.
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* getRow(int rowIndex, int* returnSize) {
    int *result;
    result=(int*)malloc(sizeof(int)*(rowIndex+1));
    int i=0,j=0;
    for(i=0;i<=rowIndex;i++)
    {
        for(j=i;j>=0;j--) //逆序
        {
            if(0==i||i==j)
                result[j]=1;
            else 
                result[j]=result[j]+result[j-1];
        }
    }
    *returnSize=rowIndex+1;
    return result;
}
```


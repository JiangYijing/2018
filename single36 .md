# Distribute Candies
## 问题分析:
遍历数组保证每个人拿到的糖果种类不重复,注意测试数据边缘
## 编程实现:
```C++
class Solution {  
public:  
    int distributeCandies(vector<int>& candies) {  
        int length=candies.size()/2;  
        int result=0;  
        int i=0;  
        vector<int> mark;  
        mark.resize(200001,1);  
        while ((result<length) && (i<length*2))  
        {  
            int a=candies[i]+100000;  
            if (mark[a]<0)
            i++;  
            else 
            {  
                i++;  
                result++;   
                mark[a]=-mark[a];  
            }  
        }  
        return result;  
    }  
};  
```

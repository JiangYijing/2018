# Gray Code
## 问题分析：
格雷码与二进制的转换，由于格雷码只能在一位上有差异，所以利用从最低开始逐位加一的方法解决
## 编程实现：
```C++
class Solution {
public:
    vector<int> grayCode(int n) 
    {         
        vector<int> res(1, 0);
        for(int i=0;i<n;++i) 
        {
            int length=res.size();
            while(length--) 
            {
                int curNum=res[length];
                curNum+=(1<<i);
                res.push_back(curNum);
            }
        }
        return res;
    }
};
```

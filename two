# Container With Most Water
## 问题分析：
装最多水的容器,定义i和j两个指针指向数组两端,向中间搜索然后不断比较得到比较的大的
## 编程实现：
```C++
class Solution {
public:
    int maxArea(vector<int>& height) {
        int res=0,i= 0,j=heights.size()-1;
        while(i<j)
        {
            res= max(res, min(heights[i],heights[j])*(j - i));
            heights[i]<heights[j] ? ++i : --j;
        }
        return res;
    }
};
```

# ZigZag Conversion
## 问题分析：
字符串字形转化,找出排列规律,按照形状输出字符串,注意字符变换完的每一行
## 编程实现：
```C++
class Solution {
public:
    string convert(string s, int numRows) {
        vector<string> vecStrings;
        for(int i=0;i<numRows;++i)
        {
            vecStrings.push_back("");
        }
        
        if(numRows==1)
        {
            return s;
        }
        int total=2*(numRows-1);
        for(int i=0;i<s.size();++i)
        {
            int idx=i%total;
            if(idx>numRows-1)
            {
                idx=total-idx;
            }
            vecStrings[idx]+= s[i];
        }
        string ret;
        for(int i=0;i<numRows;++i)
        {
            ret+=vecStrings[i];
        }
        return ret;
    }
};
```

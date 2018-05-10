# First Unique Character in a String
## 问题分析：
字符串第一个不同字符,用哈希表建立每个字符和其出现次数的映射按顺序遍历字符串
## 编程实现：
```C++
class Solution {
public:
    int firstUniqChar(string s) {
        unordered_map<char, int> m;
        for(char c:s) 
        ++m[c];
        for(int i=0;i<s.size();++i)
        {
            if(m[s[i]]==1)
            return i;
        }
        return -1;
    }
};
```

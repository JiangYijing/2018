# Ransom Note
## 问题分析：
赎金条,利用哈希Map统计字符的个数
## 编程实现：
```C++
class Solution {
public:
    bool canConstruct(string ransomNote,string magazine) {
        unordered_map<char,int> m;
        for(char c:magazine) 
        ++m[c];
        for(char c:ransomNote)
        {
            if(--m[c]<0) 
            return false;
        }
        return true;
    }
};
```

# Group Anagrams
## 问题分析：
群组错位词,群组给定字符串集中所有的错位词,所谓的错位词就是两个字符串中字母出现的次数一样只是位置不同,看把错位词的字符顺序重新排列是否得到相同的结果,重新排序后得到相同字符串
## 编程实现
```C++
class Solution {
public:
    vector<vector<string>> groupAnagrams(vector<string>& strs) {
        vector<vector<string>> res;
        unordered_map<string, vector<string>> m;
        for(string str:strs) 
        {
            string t=str;
            sort(t.begin(),t.end());
            m[t].push_back(str);
        }
        for(auto a:m) 
        {
            res.push_back(a.second);
        }
        return res;
    }
};
```

# Word Break
## 问题分析：
分割成有效的单词,找出所有的组合截取出存在的词
## 编程实现：
```C++
class Solution {
  public:
      bool wordBreak(string s, unordered_set<string> &dict) {
          int len=s.length();
          vector<bool> v(len+1,false);
          v[0]=true;
          for(int pos=0;pos<len;pos++){
              for(int i=pos;v[pos]&&i<len;i++){
                  if(dict.find(s.substr(pos,i-pos+1))!=dict.end())
                     v[i+1]=true;
             }
         }
         return v[len];
     }
 };

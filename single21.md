# Word Ladder
## 问题分析：
广度优先搜索,求无向图最短路径
## 编程实现：
```C++
class Solution {
public:
    int ladderLength(string beginWord, string endWord, unordered_set<string>& wordList) {    
        if(beginWord.size()==0||endWord.size()==0)  return 0;
        if(beginWord.size()!=endWord.size())    return 0; 
        int n = beginWord.size();
        bool exist=false;
        int step=1; 
        queue<string> q; 
        while(!q.empty())   q.pop();
        q.push(beginWord);
        q.push("1");  
        wordList.erase(beginWord); 
        while(!q.empty()){
            string word = q.front();
            q.pop(); 
            if(word == endWord){
                exist = true;
                break;
            }
            if(word == "1"){
                step++;
                continue;
            }
            for(int i=0; i<n; ++i){
                char temp = word[i];
                for(char x='a'; x<='z'; x++){
                    string tmp = word;
                    if(x!=temp){
                        tmp[i] = x;
                        if(wordList.find(tmp) != wordList.end())    q.push(tmp);
                        wordList.erase(tmp);
                    }
                }
            }
            if(!q.empty()&&q.front()=="1")   
            q.push("1"); 
        }  
        if(exist)   return step;
        else    return 0; 
    }
};
```

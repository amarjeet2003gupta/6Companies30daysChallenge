# How to find a perfect Rectangle

Problem Link : [Link](https://leetcode.com/problems/perfect-rectangle/description/)

Solution Link : [Link](https://leetcode.com/problems/perfect-rectangle/submissions/871778340/)

**Solution:-**
```C++

class Solution {
public:
    bool isRectangleCover(vector<vector<int>>& rectangles) {
        map<pair<int,int>,int> m;
        for(auto i : rectangles){
            m[{i[0],i[1]}]++;
            m[{i[2],i[3]}]++;
            m[{i[0],i[3]}]--;
            m[{i[2],i[1]}]--;
        }
        int ct = 0;
        for(auto i : m){
            if(abs(i.second)!=0){
                if(abs(i.second)!=1) return false;
                ct++;
            }
        }
        return ct==4;
    }
};

```

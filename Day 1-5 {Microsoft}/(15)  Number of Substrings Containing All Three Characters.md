# Number of Substrings Containing All Three Characters

Problem Link : [Link](https://leetcode.com/problems/number-of-substrings-containing-all-three-characters/description/)

Solution Link : [Link](https://leetcode.com/problems/number-of-substrings-containing-all-three-characters/submissions/871918421/)

**Solution:-**
```C++

class Solution {
public:
    int numberOfSubstrings(string s) {
        map<char,int> m;
        int ct = 0;
        int i=0,j=0;
        while(j<=s.size()){
            while(m['a']>0 && m['b']>0 && m['c']>0){
                m[s[i]]--;
                i++;
                ct++;
            }
            if(j>=s.size()) break;
            ct += i;
            m[s[j]]++;
            j++;
        }
        return ct;
    }
};

```

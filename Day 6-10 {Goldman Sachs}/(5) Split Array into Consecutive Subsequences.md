
# Split Array into Consecutive Subsequences

Problem Link : [Link](https://leetcode.com/problems/split-array-into-consecutive-subsequences/)

Solution Link : [Link](https://leetcode.com/problems/split-array-into-consecutive-subsequences/submissions/880110872/)

**Solution:-**
```C++

class Solution {
public:
    bool isPossible(vector<int>& nums) {
        map<int,int> m,m1;
        for(auto i : nums) m[i]++;
        for(auto i : nums){
            if(m[i]==0) continue;
            m[i]--;
            if(m1[i-1]>0){
                m1[i-1]--;
                m1[i]++;
            }
            else if(m[i+1]>0 && m[i+2]>0){
                m[i+1]--;
                m[i+2]--;
                m1[i+2]++;
            }
            else return false;
        }
        return true;
    }
};

```

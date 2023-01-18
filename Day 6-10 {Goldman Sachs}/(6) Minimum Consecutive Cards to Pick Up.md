
# Minimum Consecutive Cards to Pick Up

Problem Link : [Link](https://leetcode.com/problems/minimum-consecutive-cards-to-pick-up/)

Solution Link : [Link](https://leetcode.com/problems/minimum-consecutive-cards-to-pick-up/submissions/880130656/)

**Solution:-**
```C++

class Solution {
public:
    int minimumCardPickup(vector<int>& cards) {
        map<int,vector<int>> m;
        for(int i=0;i<cards.size();i++) m[cards[i]].push_back(i+1);
        
        int ans = INT_MAX;
        for(auto i : m){
            for(int j=0;j<i.second.size()-1;j++){
                ans = min(i.second[j+1]-i.second[j],ans);
            }
        }

        if(ans==INT_MAX) return -1;
        return ans+1;
    }
};

```

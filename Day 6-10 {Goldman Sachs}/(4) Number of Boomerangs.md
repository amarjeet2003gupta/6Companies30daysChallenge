
# Number of Boomerangs

Problem Link : [Link](https://leetcode.com/problems/number-of-boomerangs/)

Solution Link : [Link](https://leetcode.com/problems/number-of-boomerangs/submissions/877333179/)

**Solution:-**
```C++

class Solution {
public:
    int numberOfBoomerangs(vector<vector<int>>& a) {
        int ans = 0;
        int n = a.size();
        map<int,vector<int>> m;
        for(int i=0;i<n;i++){
            for(int j=0;j<n;j++){
                if(j==i) continue;
                int x = a[i][0]-a[j][0];
                int y = a[i][1]-a[j][1];
                m[i].push_back(x*x+y*y);
            }
        }
        for(auto i : m){
            map<int,int> ct;
            for(auto j : i.second){
                ct[j]++;
            }
            for(auto j : ct) ans += j.second*(j.second-1);
        }
        return ans;
    }
};
```

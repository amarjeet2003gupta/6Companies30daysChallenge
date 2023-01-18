
# Max Points on a Line

Problem Link : [Link](https://leetcode.com/problems/max-points-on-a-line/)

Solution Link : [Link](https://leetcode.com/problems/max-points-on-a-line/submissions/873833468/)

**Solution:-**
```C++

class Solution {
public:
    int maxPoints(vector<vector<int>>& a) {
        int n = a.size();
        if(n<3) return n;
        int mx = 2;
        for(int i=0;i<n;i++){
            for(int j=0;j<n;j++){
                if(j==i) continue;
                int ct = 2;
                for(int k=0;k<n;k++){
                    if(k==i || k==j) continue;
                    if((a[j][1]-a[i][1])*(a[i][0]-a[k][0])==(a[i][1]-a[k][1])*(a[j][0]-a[i][0])) ct++;
                }
                mx = max(mx,ct);
            }
        }
        return mx;
    }
};


```

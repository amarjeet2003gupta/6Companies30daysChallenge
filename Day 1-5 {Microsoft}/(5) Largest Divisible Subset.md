# Largest Divisible Subset

Problem Link : [Link](https://leetcode.com/problems/largest-divisible-subset/description/)

Solution Link : [Link](https://leetcode.com/problems/largest-divisible-subset/submissions/871760607/)

**Solution:-**
```C++

class Solution {
public:
    vector<int> largestDivisibleSubset(vector<int>& a) {
        sort(a.begin(),a.end());
        int n = a.size();
        vector<int> ans;
        int mx = 1;
        vector<int> dp(n+1,1);
        for(int i=1;i<n;i++){
            for(int j=0;j<i;j++){
                if(a[i]%a[j]==0){
                    dp[i] = max(dp[i],1+dp[j]);
                    mx = max(mx,dp[i]);
                }
            }
        }
        
        int enter = -1;
        for(int i=n-1;i>=0;i--){
            if(dp[i]==mx && (enter==-1 || enter%a[i]==0)){
                ans.push_back(a[i]);
                mx--;
                enter = a[i];
            }
        }
        return ans;
    }
};

```

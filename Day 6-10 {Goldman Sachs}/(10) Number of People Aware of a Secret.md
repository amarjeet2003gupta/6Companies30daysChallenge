
# Number of People Aware of a Secret

Problem Link : [Link](https://leetcode.com/problems/number-of-people-aware-of-a-secret/)

Solution Link : [Link](https://leetcode.com/problems/number-of-people-aware-of-a-secret/submissions/880558850/)

**Solution:-**
```C++

class Solution {
public:
    const int mod = 1e9+7;
    int peopleAwareOfSecret(int n, int delay, int forget) {
        if(delay>=forget) return 0;

        vector<int> a(2222,0);
        a[0] = 1;
        for(int i=0;i<n;i++){
            if(a[i]==0) continue;
            for(int j=i+delay;j<i+forget;j++){
                a[j] = (a[j] + a[i]) % mod;
            }
        }
        
        int i=n-1;
        int sum = 0;
        while(forget--){
            sum = (sum + a[i]) % mod;
            i--;
        }
        return sum;
    }
};


```

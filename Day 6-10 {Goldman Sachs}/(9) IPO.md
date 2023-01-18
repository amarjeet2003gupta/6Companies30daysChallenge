
# IPO

Problem Link : [Link](https://leetcode.com/problems/ipo/)

Solution Link : [Link](https://leetcode.com/problems/ipo/submissions/880432285/)

**Solution:-**
```C++

class Solution {
public:
    int findMaximizedCapital(int k, int w, vector<int>& p, vector<int>& c) {
        vector<pair<int,int>> vp;
        int n = p.size();
        for(int i=0;i<n;i++){
            vp.push_back({c[i],p[i]});
        }
        sort(vp.begin(),vp.end());
        for(auto i : vp) cout << i.first << " " << i.second << endl;

        priority_queue<int> mx;
        int i = 0;
        while(k--){
            while(i<vp.size()){
                if(vp[i].first>w) break;
                mx.push(vp[i].second);
                i++;
            }
            if(mx.size()){
                w += mx.top();
                mx.pop();
            }
        }
        return w;
    }
};

```

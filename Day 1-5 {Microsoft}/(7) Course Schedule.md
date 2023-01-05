
# Course Schedule

Problem Link : [Link](https://leetcode.com/problems/course-schedule/description/)

Solution Link : [Link](https://leetcode.com/problems/course-schedule/submissions/)

**Solution:-**
```C++

class Solution {
public:
    bool cyclic(vector<vector<int>> &adj,vector<int> &visit,int node){
        if(visit[node]==2) return true;
        visit[node] = 2;
        for(int i=0;i<adj[node].size();i++){
            if(visit[adj[node][i]]!=1) if(cyclic(adj,visit,adj[node][i])) return true;
        }
        visit[node] = 1;
        return false;
    }
    bool canFinish(int numCourses, vector<vector<int>>& a) {
        int n = a.size();
        vector<vector<int>> adj(numCourses);
        for(int i=0;i<n;i++) adj[a[i][0]].push_back(a[i][1]);
        vector<int> visited(numCourses,0);
        for(int i=0;i<numCourses;i++){
            if(visited[i]==0) if(cyclic(adj,visited,i)) return false;
        }
        return true;
    }
};

```

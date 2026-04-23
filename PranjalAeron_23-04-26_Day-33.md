**Min Cost Climbing Stairs**
```
class Solution {
public:
    int minCostClimbingStairs(vector<int>& cost) {
        int n=cost.size();
        for(int i=2;i<n;i++)
        {
            cost[i]+=min(cost[i-1],cost[i-2]);
        }
        return min(cost[n-1],cost[n-2]);
    }
};
```
<img width="1470" height="835" alt="image" src="https://github.com/user-attachments/assets/a125b7fb-23a9-4bba-8556-6cdc3f9a35c6" />

**Find Center of Star Graph**
```
class Solution {
public:
    int findCenter(vector<vector<int>>& edges) {
        int n=edges.size();
        vector<int>indegree(n+2,0);
        for(auto&e:edges){
            indegree[e[0]]++;
            indegree[e[1]]++;
        }
        for(int i=1;i<=n+1;i++){
            if(indegree[i]==n){
                return i;
            }
        }
        return -1;
    }
};
```
<img width="1470" height="833" alt="image" src="https://github.com/user-attachments/assets/4cc18cf4-ced0-4cc1-9da0-dcca32173e78" />


**Number of Provinces**
```
class Solution {
public:
    void dfs(int node, vector<int>&vis,vector<vector<int>>& grid ){
        vis[node]=1;
        for(int j=0;j<grid.size();j++){
            if(grid[node][j]==1 && !vis[j]){
                dfs(j,vis,grid);
            }
        }
    }
    int findCircleNum(vector<vector<int>>& grid) {
       int n=grid.size();
        int province=0;
       vector<int>vis(n,0);
       for(int i=0;i<n;i++){
        if(!vis[i]){
            province++;
            dfs(i, vis, grid);
        }
       }
       return province;
    }
};
```
<img width="1466" height="831" alt="image" src="https://github.com/user-attachments/assets/26272c62-1b11-409c-879d-805fdd891b63" />

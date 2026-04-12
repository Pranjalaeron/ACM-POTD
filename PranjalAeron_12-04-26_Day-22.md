**Flood Fill**
```
class Solution {
public:
    vector<vector<int>> floodFill(vector<vector<int>>& image, int sr, int sc, int color) {
        int n=image.size();
        int m=image[0].size();
        vector<vector<int>>vis(n,vector<int>(m,0));

        int old=image[sr][sc];
        if(image[sr][sc]==color) return image;
        image[sr][sc]=color;
        
        queue<pair<int,int>>q;
        q.push({sr,sc});
        vis[sr][sc]=1;

        int drow[]={-1,0,1,0};
        int dcol[]={0,1,0,-1};

        while(!q.empty()){
            int r=q.front().first;
            int c=q.front().second;
            q.pop();

            for(int i=0;i<4;i++){
                int nrow=r+drow[i];
                int ncol=c+dcol[i];

                if(nrow>=0 && nrow<n && ncol>=0 && ncol<m && image[nrow][ncol]==old && !vis[nrow][ncol]){
                    vis[nrow][ncol]=1;
                    image[nrow][ncol]=color;
                    q.push({nrow,ncol});
                }
            }
        }
        return image;

    }
};
```
<img width="1467" height="832" alt="image" src="https://github.com/user-attachments/assets/e5746496-192f-4d05-8f7d-f7fbf8b5caab" />

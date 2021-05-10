```c++
class Solution {
public:
    
    int dx[4] = {-1,1,0,0};
    int dy[4] = {0,0,1,-1};
    int movingCount(int m, int n, int k) {
        int ans = 0;
        if(!m || !n) return ans; 
        vector<vector<int>>vis(m,vector<int>(n,0));
        vis[0][0] = 1;
        dfs(0,0,m,n,k,vis);
        for(int i = 0;i<m;i++)
        {
            for(int j= 0;j<n;j++)
            {
                if(vis[i][j]) ans++;
            }
        }
        return ans;
    }
    
    int sum(int a,int b)
    {
        int sum = 0;
        while(a)
        {
            sum += a%10;
            a/=10;
        }
        while(b)
        {
            sum += b%10;
            b/=10;
        }
        return sum;
    }
    void dfs(int r,int c,int m,int n,int k,vector<vector<int>>&vis)
    {
        for(int i = 0;i<4;i++)
        {
            int tx = r + dx[i];
            int ty = c + dy[i];
            if(tx >=0 && tx < m && ty >=0 && ty <n && !vis[tx][ty] && sum(tx,ty) <=k)
            {
                vis[tx][ty] = 1;
                dfs(tx,ty,m,n,k,vis);
            }
        }
    }
};
```


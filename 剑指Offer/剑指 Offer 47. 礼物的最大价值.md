```c++
class Solution {
public:
    int maxValue(vector<vector<int>>& grid) {
        int m = grid.size();
        int n = grid[0].size();
        vector<vector<int>>dp(m,vector<int>(n,0));
        
        
        for(int i = 0;i<m;i++)
        {
            for(int j = 0;j<n;j++)
            {
                dp[i][j] = grid[i][j];
                if(j-1 >=0)//left
                {
                    dp[i][j] = max(dp[i][j],grid[i][j] + dp[i][j-1]);
                }
                if(i-1 >=0)//up
                {
                    dp[i][j] = max(dp[i][j],grid[i][j] + dp[i-1][j]);
                }
            }
        }
        
        return dp[m-1][n-1];
    }
};
```


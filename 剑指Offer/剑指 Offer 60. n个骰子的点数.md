```c++
class Solution {
public:
    vector<double> twoSum(int n) {
        vector<vector<int>>dp((n+1),vector<int>(6*(n+1),0));

        long long ans = pow(6,n);
        vector<double>s;
        for(int j = 1;j<=6;j++)
        {
            dp[1][j] = 1;
        }
        for(int i = 1;i<=n;i++)
        {
            for(int j = i;j<=6*i;j++)
            {
                for(int k = 1;k<=6;k++)
                {
                    if(j>=k)
                    {
                        dp[i][j] += dp[i-1][j-k];
                    }
                }
                
            }
        }

        for(int j = n;j<=6*n;j++)
        {
            s.push_back((dp[n][j]*1.0)/ans);
        }

        return s;
    }
};
```


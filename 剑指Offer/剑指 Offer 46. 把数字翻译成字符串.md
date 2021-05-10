```c++
class Solution {
public:
    int translateNum(int num) {
        string s = to_string(num);
        vector<int>dp(s.size()+1,0);

        dp[0] = 1;
        dp[1] = 1;
        for(int i = 1;i<s.size();i++)
        {
            dp[i+1] += dp[i];
            if(s[i-1] > '0' && (s[i-1] - '0')*10 + (s[i] - '0') <= 25)
            {
                dp[i+1] += dp[i-1]; 
            } 
        }
        return dp[s.size()];
    }
};
```


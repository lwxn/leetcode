```c++
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        long site = 1;
        int ans = 0;
        for(int i = 0;i<32;i++)
        {
            int t = 0;
            for(int num : nums)
            {
                t += !!(num&site);
            }
            // cout<<t<<endl;
            ans += (t%3)<<i;
            site<<=1;
        }
        return ans;
    }
};
```


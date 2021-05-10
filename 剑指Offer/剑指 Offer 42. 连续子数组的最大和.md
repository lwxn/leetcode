```c++
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int ans = nums[0];
        int Max = ans;
        for(int i = 1;i<nums.size();i++)
        {
            ans = ans <0 ? nums[i] : ans+nums[i];
            Max = max(Max,ans);
        }
        return Max;
    }
};
```


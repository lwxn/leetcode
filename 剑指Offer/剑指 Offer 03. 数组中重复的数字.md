```c++
class Solution {
public:
    int findRepeatNumber(vector<int>& nums) {
        int zero = 0;
        for(int i = 0;i<nums.size();i++)
        {
            if(nums[abs(nums[i])] == 0) zero++;
            nums[abs(nums[i])] = -nums[abs(nums[i])];
            if(nums[abs(nums[i])] >0 || !nums[abs(nums[i])] && zero == 2) return abs(nums[i]);
        }
        return 0;
    }
};
```
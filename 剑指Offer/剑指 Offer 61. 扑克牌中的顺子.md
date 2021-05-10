```c++
class Solution {
public:
    bool isStraight(vector<int>& nums) {
        sort(nums.begin(),nums.end());
        int zero = 0;
        for(int i = 0;i<nums.size()-1;i++)
        {
            if(nums[i] == 0)
            {
                zero++;
            }
            else
            {
                if(nums[i] >= nums[i+1]) return false;
                if(nums[i] == nums[i+1] -1) continue;
                if(nums[i+1] - nums[i] -1 <=zero)
                {
                    zero--;
                }
                else
                {
                    return false;
                }
            }
        }
        return true;
    }
};
```


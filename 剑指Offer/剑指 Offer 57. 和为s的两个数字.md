```c++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int i = 0,j = nums.size()-1;
        while(i<j)
        {
            if(nums[i] + nums[j] == target) return {nums[i],nums[j]};
            else if(nums[i] + nums[j] < target) i++;
            else j--;
        }
        return {};
    }
};
```


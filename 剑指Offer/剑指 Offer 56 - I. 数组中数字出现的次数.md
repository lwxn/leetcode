```c++
class Solution {
public:
    vector<int> singleNumbers(vector<int>& nums) {
        int x = 0;
        for(int i = 0;i<nums.size();i++)
        {
            x ^= nums[i];
        }
        
        cout<<x<<endl;
        int site = 1;
        while((site & x) == 0)
        {
            site <<= 1;
        }
        
        int ans1 = 0,ans2 = 0; 
        for(int num : nums)
        {
            if(num&site) ans1 ^= num;
            else ans2 ^= num;
        }
        return {ans1,ans2};
    }
};
```


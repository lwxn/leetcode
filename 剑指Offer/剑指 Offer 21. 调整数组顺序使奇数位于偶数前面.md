```c++
class Solution {
public:
    
    static bool cmp(const int & a,const int & b)
    {
        return (a&1) > (b&1);
    }
    vector<int> exchange(vector<int>& nums) {
        sort(nums.begin(),nums.end(),cmp);
        return nums;
    }
};
```


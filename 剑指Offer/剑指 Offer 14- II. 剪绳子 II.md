```c++
class Solution {
public:
    int cuttingRope(int n) {
        if(n <= 2) return 1;
        if(n == 3) return 2;
        long ans = 1;
        while(n > 4)
        {
            ans = (ans*3)%1000000007;
            n-=3;
        }
        ans = (ans*n)%1000000007;
        return ans;
    }
};
```


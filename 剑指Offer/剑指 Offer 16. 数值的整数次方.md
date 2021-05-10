```c++
class Solution {
public:
    double myPow(double x, int n) {
        double ans = 1;
        double a = x;
        long n1 = n;
        
        int flag = n1<0 ? 1 : 0;
        n1 = abs(n1);
        
        while(n1)
        {
            if(n1&1)
            {
                ans *= a;
            }
            a *= a;
            n1 >>=1;
        }
        return flag ? 1/ans : ans;
    }
};
```


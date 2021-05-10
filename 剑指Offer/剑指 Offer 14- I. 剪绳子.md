```c++
class Solution {
public:
    int cuttingRope(int n) {
        if(n <= 3) return n-1;
        
        int cnt = n/3;
        int t = n-cnt*3;
        
        if(t == 0) return pow(3,cnt);
        if(t == 1) return pow(3,cnt-1)*4;
        return pow(3,cnt)*2;
    }
};
```


```c++
class Solution {
public:
    int lastRemaining(int n, int m) {
        int t = 0;
        for(int i = 2;i<=n;i++)
        {
            t = (t+m)%i;
        }
        return t;
    }
};
```


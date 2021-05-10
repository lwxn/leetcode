```c++
class Solution {
public:
    int add(int a, int b) {
        int c = 0;
        while(b)
        {
            c = (unsigned int)(a&b)<<1;
            a = a xor b;
            b = c;
        }
        return a;
    }
};
```


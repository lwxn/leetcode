```c++
class Solution {
public:
    int findNthDigit(int n) {
        long site = 9;
        int digit = 1;
        
        while(n > site)
        {
            n -= site;
            digit++;
            site = digit*9 * pow(10,digit-1);
        }
        
        int base = pow(10,digit-1) + (n-1)/digit;
        int num = (n-1)%digit;
        
        return to_string(base)[num]-'0';
    }
};
```


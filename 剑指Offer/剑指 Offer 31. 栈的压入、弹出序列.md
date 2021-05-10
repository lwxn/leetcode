```c++
class Solution {
public:
    bool validateStackSequences(vector<int>& pushed, vector<int>& popped) {
        int i = 0,j = 0;
        stack<int>s;

        while(!s.empty() || i != pushed.size())
        {
            if(!s.empty() && s.top() == popped[j])
            {
                s.pop();
                j++;
            }
            else if(i != pushed.size())
            {
                if(pushed[i] == popped[j])
                {
                    i++;
                    j++;
                }
                else
                {
                    s.push(pushed[i++]);
                }
            }
            else
            {
                break;
            }
        }

        if(j != popped.size()) return false;
        else return true;
    }
};
```


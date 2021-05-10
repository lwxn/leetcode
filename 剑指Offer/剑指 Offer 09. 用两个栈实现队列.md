```c++
class CQueue {
stack<int>s1,s2;
public:
    CQueue() {
        
        
    }
    
    void appendTail(int value) {
        s1.push(value);
    }
    
    int deleteHead() {
        while(!s1.empty())
        {
            int t = s1.top();
            s2.push(t);
            s1.pop();
        }
        
        int ans = -1;
        if(!s2.empty())
        {
            ans = s2.top();
            s2.pop();
        }
        while(!s2.empty())
        {
            int t = s2.top();
            s1.push(t);
            s2.pop();
        }
        return ans;
        
    }
};

/**
 * Your CQueue object will be instantiated and called as such:
 * CQueue* obj = new CQueue();
 * obj->appendTail(value);
 * int param_2 = obj->deleteHead();
 */
```


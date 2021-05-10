```c++
class MedianFinder {
public:
    /** initialize your data structure here. */
    priority_queue<int,vector<int>,less<int>>q1;
    priority_queue<int,vector<int>,greater<int>>q2;
    MedianFinder() {

    }
    
    void addNum(int num) {
        int tmp = num;
        if(!q1.empty() && q1.size() != q2.size())
        {
            q1.push(num);
            tmp = q1.top();
            q1.pop();
            q2.push(tmp);
        }
        else
        {
            q2.push(num);
            tmp = q2.top();
            q2.pop();
            q1.push(tmp);
        }
    }
    
    double findMedian() {
        double tmp = 0;
        if(q1.size() != q2.size()) tmp = q1.top();
        else tmp =  1.0*(q1.top() + q2.top())/2.0;
        return tmp;
    }
};

/**
 * Your MedianFinder object will be instantiated and called as such:
 * MedianFinder* obj = new MedianFinder();
 * obj->addNum(num);
 * double param_2 = obj->findMedian();
 */
```


```c++
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode* deleteNode(ListNode* head, int val) {
        ListNode* H = new ListNode();
        H->next = head;
        
        ListNode* p = H;
        ListNode* q = H->next;
        ListNode* r = NULL;
        
        while(q)
        {
            r = q->next;
            if(q->val == val)
            {
                p->next = r;
                q->next = NULL;
            }
            p = q;
            q = r;
        }
        return H->next;
    }
};
```


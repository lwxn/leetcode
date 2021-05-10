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
    ListNode* reverseList(ListNode* head) {
        if(!head || !head->next) return head;
        ListNode* q = head;        
        ListNode* p = q->next;
        q->next = NULL;
        ListNode* r = NULL;
        while(p)
        {
            if(p->next)
            {
                r = p->next;  
                p->next = q;
                
                q = p;
                p = r;
                //return p;
            }
            else
            {
                p->next = q;
                break;
            }     
        }
        return p;
    }
};
```


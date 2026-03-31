**Middle of the Linked List**
```
class Solution {
public:
    ListNode* middleNode(ListNode* head) {
        ListNode*slow= head;
        ListNode*fast= head;
        while(fast!=NULL && fast->next!=NULL){
            slow=slow->next;
            fast=fast->next->next;
        }
        return slow;
        
    }
};
```
<img width="1470" height="834" alt="image" src="https://github.com/user-attachments/assets/8ddbb13f-397d-4732-bff1-d85cf7e5c7a6" />

**Add Two Numbers**
```
class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode* temp1=l1;
        ListNode* temp2=l2;
        int carry=0;
        ListNode* dummy=new ListNode(-1);
        ListNode*res=dummy;
        while(temp1 || temp2 || carry){
            int ans=0;
            if(temp1!=NULL){
                ans+=temp1->val;
                temp1=temp1->next;
            }
            if(temp2!=NULL){
                ans+=temp2->val;
                temp2=temp2->next;
            }
            ans+=carry;
            res->next= new ListNode(ans%10);
            res=res->next;
            
            carry=ans/10;
        }
        return dummy->next;
    }
};

```
<img width="1468" height="833" alt="image" src="https://github.com/user-attachments/assets/f072a91d-f53d-43ad-a1f0-c7f930a226bc" />

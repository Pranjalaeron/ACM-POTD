**Palindrome Linked List**
```
class Solution {
public:
    ListNode*reverse(ListNode*head){
        if(head==NULL || head->next==NULL) return head;
        ListNode*prev=NULL;
        ListNode*curr=head;
        ListNode*next=NULL;
        while(curr){
            next=curr->next;
            curr->next=prev;
            prev=curr;
            curr=next;
        }
        return prev;
    }
    bool isPalindrome(ListNode* head)  {
        if(head==NULL || head->next==NULL) return true;
        ListNode*temp=head;
        ListNode*slow=head;
        ListNode*fast=head;
        while(fast->next && fast->next->next){
            slow=slow->next;
            fast=fast->next->next;
        }
        ListNode*second=slow->next;
        ListNode*rev=reverse(slow->next);
        ListNode*temp2=rev;
        while(rev && temp){
            if(temp->val==rev->val){
                temp=temp->next;
                rev=rev->next;
            }
            else{
                return false;
            }
        }
        return true;
    }
};
```
<img width="1470" height="834" alt="image" src="https://github.com/user-attachments/assets/c7f284be-560f-4f4e-9145-5c1e17ed7e82" />

**Swap Nodes in Pairs**
```
class Solution {
public:
    ListNode* swapPairs(ListNode* head) {
        if(head==NULL || head->next==NULL) return head;
        ListNode*dummy=new ListNode (0);
        dummy->next=head;
        ListNode*prev=dummy;

        while(prev->next && prev->next->next){
            ListNode*first=prev->next;
            ListNode*second=first->next;

            first->next=second->next;
            second->next=first;
            prev->next=second;
            prev=first;
        }
        return dummy->next;
    }
};
```
<img width="1467" height="833" alt="image" src="https://github.com/user-attachments/assets/7e0a259f-71f4-4adf-927f-2a0eb1840c33" />




          

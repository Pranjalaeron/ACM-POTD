**Reverse Linked List**
```
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
       ListNode*prev=NULL;
       ListNode*curr=head;
       ListNode*next=NULL;
       while(curr!=NULL){
        next=curr->next;
        curr->next=prev;
        prev=curr;
        curr=next;
        
       }
       return prev;
    }
};
```
<img width="1467" height="833" alt="image" src="https://github.com/user-attachments/assets/f5e674ab-b594-4b45-b379-1353b6b0c502" />

**Remove Nth Node From End of List**
```
class Solution {
public:
    ListNode* removeNthFromEnd(ListNode* head, int n) {
        if(head==NULL) return NULL;
        int cnt=0;
        ListNode*temp=head;
        while(temp){
            cnt++;
            temp=temp->next;
        }
        if(n>cnt) return head;
        if(n==cnt) return head->next;
        ListNode*curr=head;
        int k=cnt-n-1;
        while(k--){
            curr=curr->next;
        }
        curr->next=curr->next->next;
        return head;

    }
};
```
<img width="1470" height="831" alt="image" src="https://github.com/user-attachments/assets/aa09b182-3d7c-4608-bb3a-49bba535a5f7" />

**Reverse Nodes in k-Group**
```
class Solution {
public:
    ListNode* reverseKGroup(ListNode* head, int k) {
        ListNode* curr = head;
        int count = 0;
        while (curr && count < k) {
            curr = curr->next;
            count++;
        }
        if (count == k) {
            curr = reverseKGroup(curr, k);

            while (count--) {
                ListNode* temp = head->next;
                head->next = curr;
                curr = head;
                head = temp;
            }
            head = curr;
        }

        return head;
    }
};
```
<img width="1463" height="831" alt="image" src="https://github.com/user-attachments/assets/ee9de471-84eb-48e0-9f15-6fa9ca51e449" />

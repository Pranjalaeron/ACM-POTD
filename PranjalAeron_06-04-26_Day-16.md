**Implement Queue using Stacks**
```
class MyQueue {
public:
    stack <int>s1,s2;
    MyQueue() {
        
    }
    
    void push(int x) {
        s1.push(x);
    }
    
    int pop() {
        if(s2.empty()) {
            while(!s1.empty()) {
                s2.push(s1.top());
                s1.pop();
            }
        }
        
        int val = s2.top();
        s2.pop();
        return val;
    }
    
    int peek() {
        if(s2.empty()) {
            while(!s1.empty()) {
                s2.push(s1.top());
                s1.pop();
            }
        }
        
        return s2.top();
    }
    
    bool empty() {
        return s1.empty() && s2.empty();
    }
};

/**
 * Your MyQueue object will be instantiated and called as such:
 * MyQueue* obj = new MyQueue();
 * obj->push(x);
 * int param_2 = obj->pop();
 * int param_3 = obj->peek();
 * bool param_4 = obj->empty();
 */
```
<img width="1469" height="832" alt="image" src="https://github.com/user-attachments/assets/46671a1d-06f5-4663-8ef2-cd77aa0ec139" />


**Daily Temperatures**
```
class Solution {
public:
    vector<int> dailyTemperatures(vector<int>& temperatures) {
        int n=temperatures.size();
        stack<pair<int,int>>st;
        vector<int>ans(n,0);
        for(int i=n-1;i>=0;i--){
            if(!st.empty()){
                while(!st.empty() && st.top().first<=temperatures[i]){
                    st.pop();
                }
                if(st.empty()) {
                    st.push({temperatures[i],i});
                    ans[i]=0;
                }
                else{
                    ans[i]=st.top().second-i;
                    st.push({temperatures[i],i});
                }
            }
            else{
                st.push({temperatures[i],i});
                ans[i]=0;
            }
        }
        return ans;
    }
};
```
<img width="1467" height="831" alt="image" src="https://github.com/user-attachments/assets/b77e3458-5472-4b8f-8da3-191c76030524" />




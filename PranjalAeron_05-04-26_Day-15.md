**Valid Parentheses**
```
class Solution {
public:
    bool isValid(string s) {
        int n=s.length();
        stack<char>st;
        for(char c:s){
            if(c=='(' || c=='{' || c=='['){
                st.push(c);
            }
            else if(!st.empty()){
                if((c==')' && st.top()=='(')||
                (c=='}' && st.top()=='{')||
                (c==']' && st.top()=='[')) st.pop();
                else{
                    return false;
                }
            }
            else{
                return false;
            }
                    
                
       }
       return st.empty();
       
    }
};
```
<img width="1470" height="830" alt="image" src="https://github.com/user-attachments/assets/6150012b-6888-403f-958c-414e39bd48f5" />

**Min Stack**
```
class MinStack {
public:
    stack<pair<int,int>>s;
    MinStack() {}
    
    void push(int val) {
        if(s.size()==0){
            s.push({val,val});
        }
        else{
            int minval=min(s.top().second,val);
            s.push({val,minval});
        }
       
    }
    
    void pop() {
        s.pop();
        
    }
    
    int top() {
        return s.top().first;
        
    }
    
    int getMin() {
        return s.top().second;
        
    }
};

```
<img width="1470" height="831" alt="image" src="https://github.com/user-attachments/assets/2f4c03bf-bcb8-4cb7-9ab8-4308e95260ef" />



**Backspace String Compare**
```
class Solution {
public:
    bool backspaceCompare(string s, string t) {
        int n1=s.length();
        int n2=t.length();
        stack<char>st1;
        stack<char>st2;
        for(int i=0;i<n1;i++){
            if(!st1.empty() && s[i]=='#') st1.pop();
            else if(s[i]!='#'){
                st1.push(s[i]);
            }
        }
        for(int i=0;i<n2;i++){
            if(!st2.empty() && t[i]=='#') st2.pop();
            else if(t[i]!='#'){
                st2.push(t[i]);
            }
        }
        return st1==st2;
    }
};
```
<img width="1470" height="836" alt="image" src="https://github.com/user-attachments/assets/66506441-f3ce-460d-bc4d-271ccc65fb16" />

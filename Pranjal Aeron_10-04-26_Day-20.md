**Remove Outermost Parentheses**
```
class Solution {
public:
    string removeOuterParentheses(string s) {
        int n=s.length();
        int oc=0;
        int cc=0;
        string ans="";
        int idx=0;
        for(int i=0;i<n;i++){
            if(s[i]=='('){
                oc++;
                if(oc==1){
                    idx=i;
                }
            }
            else{
                cc++;
            }
            if(oc==cc){
                ans+=s.substr(idx+1,i-idx-1);
                oc=0;
                cc=0;
            }
        }
        return ans;
    }

};
```
<img width="1468" height="832" alt="image" src="https://github.com/user-attachments/assets/6f9fe44c-4bd6-4e9c-90d0-903f072118bf" />

**Make The String Great**
```
class Solution {
public:
    string makeGood(string s) {
        int n=s.length();
        string ans="";
        for(int i=0;i<n;i++){
            if(!ans.empty() && abs(ans.back()-s[i])==32){
                ans.pop_back();
            }
            else{
                ans+=s[i];
            }
        }
        return ans;
    }
};
```
<img width="1470" height="833" alt="image" src="https://github.com/user-attachments/assets/4060bf95-b76a-4247-b2aa-f65c78929e9c" />

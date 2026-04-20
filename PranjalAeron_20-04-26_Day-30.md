**Power of Two**
```
class Solution {
public:
    bool isPowerOfTwo(int n) {
        if(n<=0) return false;
        else if((n & n-1) ==0) return true;
        else{
            return false;
        }
    }
};
```
<img width="1089" height="836" alt="image" src="https://github.com/user-attachments/assets/2090a491-2a25-44a0-be51-fe08c5744bfe" />

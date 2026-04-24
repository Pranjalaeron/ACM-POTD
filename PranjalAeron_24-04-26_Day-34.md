**House Robber**
```
class Solution {
public:
    int rob(vector<int>& nums) {
        if (nums.empty()) return 0;
        if (nums.size() == 1) return nums[0];
        
        int prev1 = nums[0], prev2 = 0;
        for (int i = 1; i < nums.size(); i++) {
            int current = max(nums[i] + prev2, prev1);
            prev2 = prev1;
            prev1 = current;
        }
        return prev1;
    }
};
```
<img width="1470" height="835" alt="image" src="https://github.com/user-attachments/assets/6ab95550-4ad7-4110-b132-701568c56edc" />


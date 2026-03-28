**Rotate Array**
```
class Solution {
public:
    void rotate(vector<int>& nums, int k) {
        int n=nums.size();
        if(n==1){
            return;
        }
        if(k>n){
            k=k%n;
        }
        vector<int>temp(n);
        int j=0;
        for(int i=n-k;i<n;i++){
            temp[j]=nums[i];
            j++;
        }
        for(int i=0;i<n-k;i++){
            temp[j]=nums[i];
            j++;
        }
        for(int i=0;i<n;i++){
            nums[i]=temp[i];
        }
    }
};
```
<img width="1468" height="832" alt="image" src="https://github.com/user-attachments/assets/6f8ed67c-1cba-4b6f-a126-98377a4e4313" />

**Increasing Triplet Subsequence**
```
class Solution {
public:
    bool increasingTriplet(vector<int>& nums) {
        int n=nums.size();
        int first=INT_MAX;
        int second=INT_MAX;
        for(int i:nums){
            if(i<=first){
                first=i;
            }
            else if(i<=second){
                second=i;
            }
            else{
                return true;
            }
        }
        return false;
    }
};
```
<img width="1470" height="836" alt="image" src="https://github.com/user-attachments/assets/8b293ded-f151-4634-92df-593f6339ff5a" />

**Maximum Score of a Good Subarray**
```
class Solution {
public:
    int maximumScore(vector<int>& nums, int k) {
        int n = nums.size();

        int left = k;
        int right = k;
        int mini = nums[k];
        int ans = mini;

        while (left > 0 || right < n - 1) {
            if (left == 0) {
                right++;
            } 
            else if (right == n - 1) {
                left--;
            } 
            else if (nums[left - 1] > nums[right + 1]) {
                left--;
            } 
            else {
                right++;
            }

            mini = min(mini, min(nums[left], nums[right]));
            ans = max(ans, mini * (right - left + 1));
        }

        return ans;
    }
};
```
<img width="1470" height="834" alt="image" src="https://github.com/user-attachments/assets/4f296662-c09e-4362-854b-7a12c27f1472" />

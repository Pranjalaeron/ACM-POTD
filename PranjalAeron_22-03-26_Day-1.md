
# Day 1 - POTD
# Remove Duplicates from Sorted Array
![PHOTO-2026-03-22-21-47-41](https://github.com/user-attachments/assets/700f8d91-ffa2-4426-8f07-68520cde44bc)


## 💻 Code
```cpp
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
       int i=0;
       int j=1;
       while(j<nums.size()){
            if(nums[i]!=nums[j]){
                i++;
                swap(nums[i],nums[j]);
            }
            j++;
       }
       return i+1;
    }
};
```



#3 sum
![PHOTO-2026-03-22-21-47-57](https://github.com/user-attachments/assets/ed39b495-5b01-4a8e-ac56-d68a1668819d)

## 💻 Code
```cpp
class Solution {
public:
    vector<vector<int>> threeSum(vector<int>& nums) {
        vector<vector<int>> ans;
        sort(nums.begin(), nums.end());
        int n = nums.size();

        for(int i = 0; i < n; i++){
            if(i > 0 && nums[i] == nums[i-1]) continue;

            int target = -nums[i];
            int j = i + 1;
            int k = n - 1;

            while(j < k){
                int sum = nums[j] + nums[k];

                if(sum == target){
                    ans.push_back({nums[i], nums[j], nums[k]});
                    j++;
                    k--;

                    while(j < k && nums[j] == nums[j-1]) j++;
                    while(j < k && nums[k] == nums[k+1]) k--;
                }
                else if(sum < target){
                    j++;
                }
                else{
                    k--;
                }
            }
        }
        return ans;
    }
};
```


#Trapping Rain Water
![PHOTO-2026-03-22-21-52-15](https://github.com/user-attachments/assets/a526791b-f7c7-4225-9be6-3fcfde17c603)

## 💻 Code
```cpp
class Solution {
public:
    int trap(vector<int>& height) {
        int n = height.size();
        int left = 0, right = n-1;
        int leftMax = 0, rightMax = 0;
        int res = 0;

        while (left < right) {
            if (height[left] <= height[right]) {
                if (height[left] >= leftMax) {
                    leftMax = height[left];
                } else {
                    res += leftMax - height[left];
                }
                left++;
            } else {
                if (height[right] >= rightMax) {
                    rightMax = height[right];
                } else {
                    res += rightMax - height[right];
                }
                right--;
            }
        }
        return res;
    }
};
```

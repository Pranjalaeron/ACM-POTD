**Missing number**

```
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n=nums.size();
        int sum=0;
        for(int i:nums){
            sum+=i;
        }
        return (n*(n+1)/2)-sum;
    }
};
```
<img width="1470" height="838" alt="image" src="https://github.com/user-attachments/assets/21f3d00c-ec56-4f23-ace5-d60cfd072023" />

**Two Sum II – Input Array Is Sorted**

```
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        
        int n=nums.size();
        int i=0;
        int j=n-1;
        while(i<j){
            if(nums[i]+nums[j]>target){
                j--;
            }
            else if(nums[i]+nums[j]<target){
                i++;
            }
            else{
                return {i+1,j+1};
            }
        }
        return {};
    }
};
```
<img width="1470" height="836" alt="image" src="https://github.com/user-attachments/assets/4e7819ad-5f25-4076-a69d-0f08d289187b" />

**Count of Smaller Numbers After Self**

```
class Solution {
public:

    void merge(int left, int mid, int right, vector<pair<int, int>>& arr,vector<int>& count)
    {
        vector<pair<int, int>> temp(right - left + 1);
        
        int i = left;
        int j = mid + 1;
        int k = 0;
        
        while(i <= mid && j <= right)
        {
            if(arr[i].first <= arr[j].first)
            {
                temp[k++] = arr[j++]; 
            }
            else
            {
                count[arr[i].second] += (right - j + 1);
                
                temp[k++] = arr[i++];
            }
        }
        
        while(i <= mid)
        {
            temp[k++] = arr[i++];
        }
        
        while(j <= right)
        {
            temp[k++] = arr[j++];
        }
        
        for(int l = left; l <= right; l++)
        arr[l] = temp[l - left];
        
    }
                
    void mergeSort(int left, int right, vector<pair<int, int>>& arr, vector<int>& count)
    {
        if(left >= right)
        {
            return;
        }

        int mid = left + (right - left) / 2;
        
        mergeSort(left, mid, arr, count);
        mergeSort(mid + 1, right, arr, count);
        
        merge(left, mid, right, arr, count);
    }
    
	vector<int> countSmaller(vector<int>& nums) {
	    
        int n=nums.size();
	    vector<pair<int, int>> arr;
        
	    for(int i = 0; i < n; i++)
	    {
	        arr.push_back({nums[i], i});
	    }
	    
	    vector<int> count(n, 0);
	    
	    mergeSort(0, n - 1, arr, count);
	    
	    return count;
	}
  
};
```
<img width="1470" height="840" alt="image" src="https://github.com/user-attachments/assets/0943eeca-41f1-4dbe-a148-a59d0e8cc76a" />





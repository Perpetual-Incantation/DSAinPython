## Q1) Move Zeroes at End 
https://leetcode.com/problems/move-zeroes/

### Approach
* Take a left pointer =0, put elements at left if not zero
* Increment left idx
* Then run a new loop from left till n, put zeroes there

### Code

```python
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        left=0
        for i in range(len(nums)):
            if nums[i]!=0:
                nums[left]=nums[i]
                left+=1
        for i in range(left, len(nums)):
            nums[i]=0
```

## Q2) https://leetcode.com/problems/max-consecutive-ones/description/

### Approach

* Check if nums[i]==1 inc temp else temp=0
* then ans variable should contains max

### Code

```python

class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        ans=0
        temp=0
        for i in range(len(nums)):
            if nums[i]==0:
                temp=0
            elif nums[i]==1:
                temp+=1
            ans=max(ans, temp)        
        return ans

```

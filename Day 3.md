# 1️⃣ Maximum Average Subarray I

🔗 **Problem Link:**  
https://leetcode.com/problems/maximum-average-subarray-i/description/

### 💡 Approach

- Use the **Sliding Window** technique.
- Find the sum of the first `k` elements using slicing.
- Store it as the current and best sum.
- Traverse the array from index `k` to `len(nums) - 1`.
- For every new window:
  - Remove the previous element from the sum.
  - Add the new element to the sum.
- Update the best sum if the current sum is greater.
- Return the maximum average by dividing the best sum by `k`.

### 🧑‍💻 Code

```python
class Solution:
    def findMaxAverage(self, nums: List[int], k: int) -> float:

        curr_tot = sum(nums[0:k])
        best_tot = curr_tot

        for i in range(k, len(nums)):
            curr_tot = curr_tot - nums[i-k] + nums[i]
            best_tot = max(curr_tot, best_tot)

        return best_tot / k
```

### ⏱️ Complexity

- Time Complexity: **O(n)**
- Space Complexity: **O(1)**

### ⭐ Pattern Used

`Sliding Window (Fixed Size)`

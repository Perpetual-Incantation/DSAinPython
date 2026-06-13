## Q1. Check if Array Is Sorted and Rotated

**Problem Link:**
https://leetcode.com/problems/check-if-array-is-sorted-and-rotated/

### 💡 Approach

* Traverse the array and count the number of times an element is greater than the next element.
* Use modulo (`%`) to compare the last element with the first element.
* If the count is greater than `1`, the array cannot be sorted and rotated.
* Otherwise, return `True`.

### 🧑‍💻 Code

```python
class Solution:
    def check(self, nums: List[int]) -> bool:
        cnt = 0

        for i in range(len(nums)):
            if nums[i] > nums[(i + 1) % len(nums)]:
                cnt = cnt + 1

        if cnt > 1:
            return False
        else:
            return True
```

### ⏱️ Complexity

* Time Complexity: **O(n)**
* Space Complexity: **O(1)**

---

## Q2. Rotate Array

**Problem Link:**
https://leetcode.com/problems/rotate-array/description/

### 💡 Approach

* Create a helper function to reverse elements between two indices.
* Reverse the entire array.
* Compute `k % n` to handle cases where `k` is greater than the array size.
* Reverse the first `k` elements.
* Reverse the remaining elements from index `k` to `n - 1`.
* The array gets rotated to the right by `k` positions.

### 🧑‍💻 Code

```python
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """

        n = len(nums)
        k = k % n

        def reverse(left, right):
            while left < right:
                nums[left], nums[right] = nums[right], nums[left]
                left += 1
                right -= 1

        reverse(0, n - 1)
        reverse(0, k - 1)
        reverse(k, n - 1)
```

### ⏱️ Complexity

* Time Complexity: **O(n)**
* Space Complexity: **O(1)**

### ⭐ Pattern Used

* Array Traversal
* Observation Based Logic
* Two Pointers
* Reversal Technique

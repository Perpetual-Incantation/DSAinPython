# 🚀 Two Pointer Problems

---

# 1️⃣ Two Sum II - Input Array Is Sorted

🔗 **Problem Link:**  
https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/description/

### 💡 Approach
Use Two Pointers and traverse from both ends of the array.

- Calculate the sum of elements at `left` and `right`.
- If the sum is smaller than the target, move `left` forward.
- If the sum is greater than the target, move `right` backward.
- Stop when the sum becomes equal to the target.

### 🧑‍💻 Code

```python
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        left = 0
        right = len(numbers) - 1

        while left < right:
            temp = numbers[left] + numbers[right]

            if temp < target:
                left = left + 1

            elif temp > target:
                right = right - 1

            else:
                return [left + 1, right + 1]
```

### ⏱️ Complexity
- Time Complexity: **O(n)**
- Space Complexity: **O(1)**

---

# 2️⃣ Container With Most Water

🔗 **Problem Link:**  
https://leetcode.com/problems/container-with-most-water/description/

### 💡 Approach
Use Two Pointers starting from both ends of the array.

- Calculate the width using `right - left`.
- The height of the container is determined by the smaller of the two heights.
- Calculate the area and update the maximum area found so far.
- Move the pointer pointing to the smaller height because only that can potentially increase the area.

### 🧑‍💻 Code

```python
class Solution:
    def maxArea(self, height: List[int]) -> int:
        left = 0
        right = len(height) - 1
        ans = 0

        while left < right:
            width = right - left
            high = min(height[left], height[right])

            temp = width * high
            ans = max(ans, temp)

            if height[left] < height[right]:
                left += 1
            else:
                right -= 1

        return ans
```

### ⏱️ Complexity
- Time Complexity: **O(n)**
- Space Complexity: **O(1)**

---

# 3️⃣ Merge Sorted Array

🔗 **Problem Link:**  
https://leetcode.com/problems/merge-sorted-array/description/

### 💡 Approach
Traverse both arrays from the end.

- `mint` points to the last valid element in `nums1`.
- `nint` points to the last element in `nums2`.
- `right` points to the last position in `nums1`.
- Compare elements from both arrays and place the larger element at the `right` position.
- Move the corresponding pointer backward.
- Continue until all elements of `nums2` are merged into `nums1`.

### 🧑‍💻 Code

```python
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """

        mint = m - 1
        nint = n - 1
        right = m + n - 1

        while nint >= 0:
            if mint >= 0 and nums1[mint] > nums2[nint]:
                nums1[right] = nums1[mint]
                mint = mint - 1
            else:
                nums1[right] = nums2[nint]
                nint -= 1

            right -= 1
```

### ⏱️ Complexity
- Time Complexity: **O(m + n)**
- Space Complexity: **O(1)**

---

## ⭐ Concepts Used
- Two Pointers
- In-place Array Modification
- Greedy Decision Making
- Sorted Array Traversal

# Array Questions

## Q1. Delete an Element from the Middle of an Array

### Approach
Find the element to be deleted, then run a loop from that index and shift all elements one position to the left. Finally, remove the last element using `pop()`.

### Code

```python
def delete(arr, t):
    n = len(arr)

    for i in range(n):
        if arr[i] == t:
            for j in range(i, n - 1):
                arr[j] = arr[j + 1]

            arr.pop()
            break

    return arr
```

---

## Q2. Reverse an Array

**Problem Link:** https://www.geeksforgeeks.org/problems/reverse-an-array/1

### Approach
Used the swapping method with a two-pointer approach.
One pointer starts from the beginning and the other from the end. Swap both elements and move the pointers towards each other until they meet.

### Code

```python
class Solution:
    def reverseArray(self, arr):
        left = 0
        right = len(arr) - 1

        while left < right:
            temp = arr[left]
            arr[left] = arr[right]
            arr[right] = temp

            left = left + 1
            right = right - 1
```

---

## Q3. Remove Duplicates from Sorted Array

**Problem Link:** https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/

### Approach
Find the duplicate elements using two pointers.

- `left` keeps track of the last unique element.
- `r` traverses the array.
- Whenever a new unique element is found, move `left` one step ahead and place the new unique element at that position.
- Return `left + 1` as the count of unique elements.
- The array from index `0` to `left` contains all unique elements.

### Code

```python
class Solution:
    def removeDuplicates(self, nums):
        left = 0

        for r in range(len(nums)):
            if nums[r] != nums[left]:
                left = left + 1
                nums[left] = nums[r]

        return left + 1
```

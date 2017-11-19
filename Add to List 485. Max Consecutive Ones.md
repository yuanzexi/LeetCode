Given a binary array, find the maximum number of consecutive 1s in this array.
### Example 1:
```
Input: [1,1,0,1,1,1]
Output: 3
Explanation: The first two digits or the last three digits are consecutive 1s.
    The maximum number of consecutive 1s is 3.
```
### Note:
* The input array will only contain 0 and 1.
* The length of input array is a positive integer and will not exceed 10,000
# Solution(python, 68ms, O(n) time, O(1) space)
```python
class Solution(object):
    def findMaxConsecutiveOnes(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        result = 0
        temp = 0
        for num in nums:
            if num == 0:
                if temp > result:
                    result = temp
                temp = 0
            else:
                temp += 1
        if temp > result:
            result = temp
        return result
```

# Solution (reference from leadboard, a new perspective, 69ms)
```python
class Solution(object):
    def findMaxConsecutiveOnes(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        # reference from leadboard
        return max([len(i) for i in bytearray(nums).split(b'\x00')])
```

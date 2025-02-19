## Approach

- Create a variable `closest` and assign the 0 index value i.e nums[0].
- Run a loop through the array and check if the `abs(i)` is less than `abs(closest)` if yes then update the closest value with `i`.
- After the loop check if the closest is less than 0 and its abs value is present in the array.
- If yes then return the abs value else the closest value

## Python solution

```python
class Solution:
    def findClosestNumber(self, nums: List[int]) -> int:
        closest = nums[0]
        for i in nums:
            if abs(i) < abs(closest):
                closest = i
        if closest < 0 and abs(closest) in nums:
            return abs(closest)
        else:
            return closest
```

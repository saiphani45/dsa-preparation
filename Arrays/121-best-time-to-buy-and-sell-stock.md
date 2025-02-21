## Approach

- The solution uses two variables:

  - min_price: Tracks the lowest price seen so far (initialized to infinity)
  - max_profit: Tracks the maximum profit possible (initialized to 0)

- For each price in the array, it:
  - Updates min_price if current price is lower than existing min_price
  - Calculates potential profit by subtracting min_price from current price
  - Updates max_profit if current profit is higher than existing max_profit

Example walkthrough:

```
Copyprices = [7,1,5,3,6,4]
Day 1: price = 7, min_price = 7, profit = 0
Day 2: price = 1, min_price = 1, profit = 0
Day 3: price = 5, min_price = 1, profit = 4
Day 4: price = 3, min_price = 1, profit = 4
Day 5: price = 6, min_price = 1, profit = 5
Day 6: price = 4, min_price = 1, profit = 5
Return: 5
```

- The algorithm is efficient with O(n) time complexity as it only requires a single pass through the array.

## Python Solution

```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        min_price = float('inf')
        max_profit = 0
        for price in prices:
            if price < min_price:
                min_price = price
            profit = price - min_price
            if profit > max_profit:
                max_profit = profit
        return max_profit

```

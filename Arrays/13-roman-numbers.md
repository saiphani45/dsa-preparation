## Approach

- The solution uses a dictionary to map both single Roman numerals (like "I" = 1) and special two-character combinations (like "IV" = 4) to their integer values.
- For each position in the string, it first tries to match a two-character combination (like "IV", "CM") with the dictionary. If found, it adds that value and skips two positions.
- If no two-character match is found, it uses the single character's value and moves to the next position.
- The process continues until the entire string is processed, with appropriate handling for the last character of the string.
- The algorithm is efficient with O(n) time complexity as it processes each character at most once.

## Python Solution

```python
class Solution:
    def romanToInt(self, s: str) -> int:
        romanNumbers = {
            "I": 1,
            "IV": 4,
            "V": 5,
            "IX": 9,
            "X": 10,
            "XL": 40,
            "L": 50,
            "XC":90,
            "C": 100,
            "CD": 400,
            "D": 500,
            "CM":900,
            "M": 1000
        }
        arr = list(s)
        i = 0
        total = 0
        while i <= len(arr) -1:
            conc = ""
            try:
                if i + 1 < len(arr):
                    conc = arr[i] + arr[i + 1]
                if romanNumbers.get(conc):
                    total  = total + romanNumbers.get(conc)
                    i = i + 2
                else:
                    getValue = romanNumbers.get(arr[i])
                    total = total + getValue
                    i = i + 1
            except IndexError:
                break
        return total
```

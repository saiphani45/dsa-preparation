## Approach

- The solution uses a two-pointer technique, where one pointer (s_pointer) tracks position in string 's' and the loop itself acts as pointer for string 't'.
- Initial check: If string 's' is empty, it's automatically considered a subsequence, so return True.
  For each character in string 't', it:
- Compares current character with character at s_pointer in string 's'
- If they match, increments s_pointer to look for next character of 's'
- If all characters of 's' are found (s_pointer == len(s)), returns True
- If the loop completes without finding all characters of 's', returns False.

## Python Solution

```python
class Solution:
    def isSubsequence(self, s: str, t: str) -> bool:
        if not s:
            return True
        s_pointer = 0
        for char in t:
            if char == s[s_pointer]:
                s_pointer += 1
                if s_pointer == len(s):
                    return True

        return False
```

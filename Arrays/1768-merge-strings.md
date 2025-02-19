## Approach

### Input Handling
- Takes two input strings: word1 and word2
    `Example: word1 = "abc", word2 = "pqr"`


### Core Merging Process


- Uses zip() to pair up characters from both strings
- Loop continues until shorter string ends
- For each pair, adds both characters to result

```
"abc" + "pqr"
First iteration: 'a' + 'p' → "ap"
Second iteration: 'b' + 'q' → "apbq"
Third iteration: 'c' + 'r' → "apbqcr"
```

### Handling Remaining Characters


- After zip loop ends, checks if either string has leftover characters
- If word1 is longer: adds remaining characters from word1
- If word2 is longer: adds remaining characters from word2

```
Example with uneven lengths:
word1 = "abcd", word2 = "xy"
After zip: "axby"
Remaining 'cd' from word1 added: "axbycd"
```

- Returns final merged string


## Python solution

```python
class Solution:
    def mergeAlternately(self, word1: str, word2: str) -> str:
        merged =""
        for i, j in zip(word1, word2):
            merged = merged + i + j
        if len(word1) > len(word2):
            merged = merged + word1[len(word2):]
        else:
            merged = merged + word2[len(word1):]
        return merged
```

`or`

```python

class Solution:
    def mergeAlternately(self, word1: str, word2: str) -> str:
        i,j = 0,0
        result=[]
        while i< len(word1) and j < len(word2):
            result.append(word1[i])
            result.append(word2[j])
            i = i + 1
            j = j + 1 
        result.append(word1[i:])
        result.append(word2[j:])
        return ''.join(result)

```
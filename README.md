# 387. First Unique Character in a String

**Difficulty:** Easy | **Topics:** Hash Table, String, Queue, Counting  
**Link:** [LeetCode Problem 387](https://leetcode.com/problems/first-unique-character-in-a-string/)

---

## Problem Summary
Given a string `s`, find the first non-repeating character and return its index. If none exists, return `-1`. 

* **Example 1:** `s = "leetcode"` $\rightarrow$ Output: `0` (`'l'` is unique)
* **Example 2:** `s = "loveleetcode"` $\rightarrow$ Output: `2`
* **Example 3:** `s = "aabb"` $\rightarrow$ Output: `-1`
* **Constraints:** `1 <= s.length <= 10^5`, lowercase English letters only.

---

## Approach & Complexity
* **Intuition:** Use a frequency array or hash map (size 26) in two passes—first to count character occurrences, and second to find the first character with a count of `1`.
* **Time Complexity:** $\mathcal{O}(N)$ where $N$ is the length of string `s`.
* **Space Complexity:** $\mathcal{O}(1)$ since the alphabet size is constant ($26$).

---

## Solution Code

### Python
```python
from collections import Counter

class Solution:
    def firstUniqChar(self, s: str) -> int:
        count = Counter(s)
        for index, char in enumerate(s):
            if count[char] == 1:
                return index
        return -1
```

*(Note: C++ and Java implementations can also be structured in this directory, or full code examples viewed directly on [LeetCode Problem 387](https://leetcode.com/problems/first-unique-character-in-a-string/).)*

---


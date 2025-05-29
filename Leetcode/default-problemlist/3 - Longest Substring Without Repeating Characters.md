All right, linked lists again it seems, i'm still not used to them to an extent (last exercise had me go through them), so i'll probably try and bruteforce it.

At first i thought of going through the same train of thought i had on the last exercise (for letter in word: / wordlist = wordlist + letter / for letter in wordlist: *check if next value is the same letter as current, if it is you stop the count, at the end of the initial for string it just checks all current string combinations and counts if there are any of the same ), but i'm too stubborn to let go of learning linked lists.

**it was not linked lists** you dummy, it was sliding windows.

i had gpt help me define the overall structure of code since was in a hurry (had to go help my grandmother after the surgery she had) i will study this structure later on to replicate it by myself, i had somewhat of the logic (track unique characters and stop at duplicates) but didnt have the right mechanics to go through with it.

```
class Solution:

    def lengthOfLongestSubstring(self, s: str) -> int:

        max_length = 0

  

        for i in range(len(s)):

            seen = set()

            for j in range(i, len(s)):

                if s[j] in seen:

                    break

                seen.add(s[j])

                max_length = max(max_length, j - i + 1)

  

        return max_length
```
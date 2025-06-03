took me 30 mins to find whatever the hell i should return, i looked it up because i was stuck. i still dont feel able to solve these without any sort of assistance, yet i am getting some progress in understanding the basic structure.

```
class Solution:

    def nextGreatestLetter(self, letters: List[str], target: str) -> str:

        l, r = 0, len(letters) - 1

        while l <= r:

            m = (l + r) // 2

            if letters[m] > target:

                r = m - 1

            else:

                l = m + 1

        return letters[l % len(letters)]
```
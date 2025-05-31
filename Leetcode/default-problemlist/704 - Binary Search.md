Since i got a little confused on #4, i decided to go through binary search as i saw it should be used in said case. This was the solution i found to this problem:

i only had syntax problems on this one

```
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        for i, number in enumerate(nums):
            if number == target:
                return i
            else:
                return -1
```

dont return on the else dummy, you'll return after the first number.

ended up w/

```
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        for i, number in enumerate(nums):
            if number == target:
                return i
        return -1
```
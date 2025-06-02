great, started with this solution:

```
class Solution:

    def searchInsert(self, nums: List[int], target: int) -> int:

        for i, number in enumerate(nums):

            if number == target:

                return i
```

worked for case 1, now gotta sort out the missing value issue, where i would have to input the index it would be at.

```
class Solution:

    def searchInsert(self, nums: List[int], target: int) -> int:

        num_alt = 0

  

        for i, number in enumerate(nums):

            if number == target:

                return i

            else:

                num_alt = num_alt + 1

        return num_alt
```

works for case 1 and 3, may be for the fact that its the last index and it just sums until the last one. i might try to bruteforce it so that num_alt is defined on 
a specific case of ifs, cond1 and cond2

```
class Solution:

    def searchInsert(self, nums: List[int], target: int) -> int:

        num_alt = 0

        num_temp = 0

  

        for i, number in enumerate(nums):

            if number == target:

                return i

            if num_temp < target and number > target:

                return i

            num_temp = number

        return i+1
```

this was my final solution, until i remembered it was binary search, it was a long day so i got a little distracted :^].

```
class Solution:

    def searchInsert(self, nums: List[int], target: int) -> int:

        left = 0

        right = len(nums) - 1

        counter = 0

        while left <= right:

            mid = (left + right) // 2

            num_temp = nums[mid]

  

            if num_temp == target:

                return mid

            elif num_temp < target:

                left = mid + 1

            else:

                right = mid - 1

            counter += 1

        return left
```

this was my final solution, im kinda getting the hang of it, just gotta get rid of old habits so that i dont automatically go the wrong way.
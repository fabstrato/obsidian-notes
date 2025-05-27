Just don't count this one, I made a faulty prompt on GPT which guided me directly on how to finish it, i wanted it only to fill in the gaps such as how to get an index without having to manually get the value for optimization, will improve prompt before progressing towards other problems.

Initial prompted solution(i wanted to get the indexes without making it look terrible):

```
class Solution:

    def twoSum(self, nums: List[int], target: int) -> List[int]:

        for number in nums:

            current_number = number

            for alt_number in nums:

                if current_number + alt_number =
```

Final solution:

```
class Solution:

    def twoSum(self, nums: List[int], target: int) -> List[int]:

        for i, number in enumerate(nums):

            for j, alt_number in enumerate(nums):

                if i != j and number + alt_number == target:

                    return [i, j]
```
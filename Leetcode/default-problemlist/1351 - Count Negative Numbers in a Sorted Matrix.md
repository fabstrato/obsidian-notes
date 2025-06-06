i was almost going insane building the count until i realized that the rows are sorted decreasingly, meaning once you get a negative, all the other ones to the right are negative :^O (i have to start doing these in the morning)

```
def countNegatives(grid):
    rows, cols = len(grid), len(grid[0])
    row = rows - 1
    col = 0
    count = 0

    while row >= 0 and col < cols:
        if grid[row][col] < 0:
            count += cols - col
            row -= 1
        else:
            col += 1

    return count
```
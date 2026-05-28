# Lab-1: Backtracking Algorithms:

Problems:
- Well defined problems
- Constraint satisfaction problems

## sudoku:

```python
def is_valid(bo, num, pos): #pos is a list that's why pos[0]>x-pos and pos[1]>y-pos
    # Check Row
    for i in range(9):
        if bo[pos[0]][i] == num and pos[1] != i:
            return False

    # Check Column
    for i in range(9):
        if bo[i][pos[1]] == num and pos[0] != i:
            return False

    # Check 3x3 Box
    box_x = pos[1] // 3
    box_y = pos[0] // 3

    for i in range(box_y*3, box_y*3 + 3):
        for j in range(box_x*3, box_x*3 + 3):
            if bo[i][j] == num and (i, j) != pos:
                return False
```


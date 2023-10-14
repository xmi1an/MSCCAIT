# Practical-04.md

## Artificial Intelligence with ML

### Practical Program 4

The classic Eight Queens game is to place eight queens on a chessboard such that no two queens can attack each other (i.e., no two queens are in the same row, same column, or same diagonal).

```python
def is_safe(board, row, col):
    # Check if there is a queen in the same column
    for i in range(row):
        if board[i][col] == 'Q':
            return False

    # Check if there is a queen in the upper left diagonal
    i = row - 1
    j = col - 1
    while i >= 0 and j >= 0:
        if board[i][j] == 'Q':
            return False
        i -= 1
        j -= 1

    # Check if there is a queen in the upper right diagonal
    i = row - 1
    j = col + 1
    while i >= 0 and j < 8:
        if board[i][j] == 'Q':
            return False
        i -= 1
        j += 1

    return True

def solve_queens(board, row):
    if row == 8:
        # All queens have been placed, print the solution
        for i in range(8):
            print(board[i])
        print()
        return

    for col in range(8):
        if is_safe(board, row, col):
            # Place the queen in the current position
            board[row][col] = 'Q'

            # Recursively solve for the next row
            solve_queens(board, row + 1)

            # Remove the queen from the current position
            board[row][col] = '-'

# Create an empty chessboard
board = [['-' for _ in range(8)] for _ in range(8)]

# Solve the Eight Queens problem
solve_queens(board, 0)
```

In this program, we define a function `is_safe` to check if it is safe to place a queen in a given position on the chessboard. The function checks if there is a queen in the same column, same upper left diagonal, and same upper right diagonal. If there is no queen in any of these positions, it returns `True`, indicating that it is safe to place a queen.

We also define a recursive function `solve_queens` to solve the Eight Queens problem. The function takes a chessboard and a row number as input. It tries to place a queen in each column of the current row, and then recursively solves for the next row. If all queens have been placed (i.e., `row == 8`), it prints the solution.

Finally, we create an empty chessboard and call the `solve_queens` function to solve the Eight Queens problem.

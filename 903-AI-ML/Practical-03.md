# Practical-03.md

## Artificial Intelligence with ML

### Practical Program 3

Create a game Tic-Tac-Toe using MinMax search technique. Tic-Tac-Toe is a simple game to play between two people. One player is X and the other player is O. On a simple nine-square grid (which we call the board), the players take turns placing their X or O on the board. If a player gets three of their marks on the board in a row, column, or one of the two diagonals, they win.

```python
def print_board(board):
    for row in board:
        print(row)

def check_winner(board):
    # Check rows
    for row in board:
        if row[0] == row[1] == row[2] != ' ':
            return row[0]

    # Check columns
    for col in range(3):
        if board[0][col] == board[1][col] == board[2][col] != ' ':
            return board[0][col]

    # Check diagonals
    if board[0][0] == board[1][1] == board[2][2] != ' ':
        return board[0][0]
    if board[0][2] == board[1][1] == board[2][0] != ' ':
        return board[0][2]

    return None

def is_board_full(board):
    for row in board:
        if ' ' in row:
            return False
    return True

def get_empty_cells(board):
    empty_cells = []
    for row in range(3):
        for col in range(3):
            if board[row][col] == ' ':
                empty_cells.append((row, col))
    return empty_cells

def minimax(board, depth, maximizing_player):
    winner = check_winner(board)
    if winner == 'X':
        return -1
    elif winner == 'O':
        return 1
    elif is_board_full(board):
        return 0

    if maximizing_player:
        max_eval = float('-inf')
        for empty_cell in get_empty_cells(board):
            row, col = empty_cell
            board[row][col] = 'O'
            eval = minimax(board, depth + 1, False)
            board[row][col] = ' '
            max_eval = max(max_eval, eval)
        return max_eval
    else:
        min_eval = float('inf')
        for empty_cell in get_empty_cells(board):
            row, col = empty_cell
            board[row][col] = 'X'
            eval = minimax(board, depth + 1, True)
            board[row][col] = ' '
            min_eval = min(min_eval, eval)
        return min_eval

def get_best_move(board):
    best_eval = float('-inf')
    best_move = None
    for empty_cell in get_empty_cells(board):
        row, col = empty_cell
        board[row][col] = 'O'
        eval = minimax(board, 0, False)
        board[row][col] = ' '
        if eval > best_eval:
            best_eval = eval
            best_move = empty_cell
    return best_move

def play_game():
    board = [[' ' for _ in range(3)] for _ in range(3)]
    current_player = 'X'
    while True:
        print_board(board)
        if current_player == 'X':
            row = int(input("Enter the row (0-2): "))
            col = int(input("Enter the column (0-2): "))
            if board[row][col] != ' ':
                print("Invalid move. Try again.")
                continue
            board[row][col] = 'X'
        else:
            best_move = get_best_move(board)
            row, col = best_move
            board[row][col] = 'O'
        winner = check_winner(board)
        if winner:
            print_board(board)
            print(f"{winner} wins!")
            break
        elif is_board_full(board):
            print_board(board)
            print("It's a tie!")
            break
        current_player = 'O' if current_player == 'X' else 'X'

play_game()
```


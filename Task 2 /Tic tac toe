import math

# Create empty board
board = [" " for _ in range(9)]


# Display board
def print_board():
    print("\n")
    for i in range(3):
        print(board[i * 3] + " | " + board[i * 3 + 1] + " | " + board[i * 3 + 2])

        if i < 2:
            print("--+---+--")
    print()


# Check winner
def check_winner(player):

    winning_combinations = [

        [0, 1, 2],
        [3, 4, 5],
        [6, 7, 8],

        [0, 3, 6],
        [1, 4, 7],
        [2, 5, 8],

        [0, 4, 8],
        [2, 4, 6]
    ]

    for combination in winning_combinations:

        if (
            board[combination[0]] == player and
            board[combination[1]] == player and
            board[combination[2]] == player
        ):
            return True

    return False


# Check draw
def check_draw():

    return " " not in board


# Minimax Algorithm
def minimax(is_maximizing):

    if check_winner("O"):
        return 1

    if check_winner("X"):
        return -1

    if check_draw():
        return 0


    # AI TURN
    if is_maximizing:

        best_score = -math.inf

        for i in range(9):

            if board[i] == " ":

                board[i] = "O"

                score = minimax(False)

                board[i] = " "

                best_score = max(score, best_score)

        return best_score


    # HUMAN TURN
    else:

        best_score = math.inf

        for i in range(9):

            if board[i] == " ":

                board[i] = "X"

                score = minimax(True)

                board[i] = " "

                best_score = min(score, best_score)

        return best_score


# AI Move
def ai_move():

    best_score = -math.inf
    best_move = 0

    for i in range(9):

        if board[i] == " ":

            board[i] = "O"

            score = minimax(False)

            board[i] = " "

            if score > best_score:

                best_score = score
                best_move = i

    board[best_move] = "O"


# Human Move
def human_move():

    while True:

        try:

            move = int(input("Enter position (1-9): ")) - 1

            if move < 0 or move > 8:
                print("Invalid Position!")

            elif board[move] != " ":
                print("Position Already Taken!")

            else:
                board[move] = "X"
                break

        except ValueError:
            print("Please Enter a Number!")


# Instructions
print("===== TIC TAC TOE AI =====")
print("You  : X")
print("AI   : O")

print("\nBoard Positions:\n")

print("1 | 2 | 3")
print("--+---+--")
print("4 | 5 | 6")
print("--+---+--")
print("7 | 8 | 9")


# Game Loop
while True:

    print_board()

    # Human Turn
    human_move()

    if check_winner("X"):

        print_board()

        print("Congratulations! You Win!")

        break

    if check_draw():

        print_board()

        print("Match Draw!")

        break


    # AI Turn
    ai_move()

    if check_winner("O"):

        print_board()

        print("AI Wins!")

        break

    if check_draw():

        print_board()

        print("Match Draw!")

        break

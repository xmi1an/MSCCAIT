# Practical-01.md

## Artificial Intelligence with ML

### Practical Program 1

Create a game that picks 21 cards from a deck of 52 cards and makes three stacks of 7 cards each. Guess one particular card from any stack and declare only the stack where the selected card is available. Repeat the same process two times to help you find the selected card.

```python
import random

def create_deck():
    suits = ['Spades', 'Hearts', 'Diamonds', 'Clubs']
    ranks = ['Ace', '2', '3', '4', '5', '6', '7', '8', '9', '10', 'Jack', 'Queen', 'King']
    deck = [(rank, suit) for suit in suits for rank in ranks]
    return deck

def create_stacks(deck):
    random.shuffle(deck)
    stack1 = deck[:7]
    stack2 = deck[7:14]
    stack3 = deck[14:21]
    return stack1, stack2, stack3

def guess_card(stack1, stack2, stack3):
    selected_stack = None
    selected_card = None

    print("Guess a card from the following stacks:")
    print("1. Stack 1")
    print("2. Stack 2")
    print("3. Stack 3")

    while selected_stack not in [1, 2, 3]:
        selected_stack = int(input("Enter the stack number: "))

    if selected_stack == 1:
        selected_card = random.choice(stack1)
    elif selected_stack == 2:
        selected_card = random.choice(stack2)
    elif selected_stack == 3:
        selected_card = random.choice(stack3)

    return selected_stack, selected_card

def play_game():
    deck = create_deck()
    stack1, stack2, stack3 = create_stacks(deck)

    print("Game Start!")
    print("You have to guess a card from the stacks.")
    print("You will have two chances to find the selected card.")

    for i in range(2):
        print(f"\nAttempt {i+1}:")
        selected_stack, selected_card = guess_card(stack1, stack2, stack3)
        print(f"The selected card is {selected_card[0]} of {selected_card[1]} in Stack {selected_stack}.\n")

    print("Game Over!")

play_game()
```

This program creates a game that picks 21 cards from a deck of 52 cards and makes three stacks of 7 cards each. The player has to guess a card from any of the stacks, and the program will reveal the stack where the selected card is available. The process is repeated two times to help the player find the selected card.


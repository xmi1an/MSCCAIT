# Practical-02.md

## Artificial Intelligence with ML

### Practical Program 2

Create a game that picks four cards from a deck of 52 cards and computes their sum. An ace, king, queen, and jack represent 1, 13, 12, and 11, respectively. Your program should display the number of picks that yield the sum of 24.

```python
import random

def create_deck():
    suits = ['Spades', 'Hearts', 'Diamonds', 'Clubs']
    ranks = ['Ace', '2', '3', '4', '5', '6', '7', '8', '9', '10', 'Jack', 'Queen', 'King']
    deck = [(rank, suit) for suit in suits for rank in ranks]
    return deck

def compute_sum(cards):
    sum = 0
    for card in cards:
        rank = card[0]
        if rank == 'Ace':
            sum += 1
        elif rank == 'King':
            sum += 13
        elif rank == 'Queen':
            sum += 12
        elif rank == 'Jack':
            sum += 11
        else:
            sum += int(rank)
    return sum

def play_game():
    deck = create_deck()
    random.shuffle(deck)
    picks = deck[:4]

    print("Game Start!")
    print("You have picked the following cards:")
    for card in picks:
        print(card[0], "of", card[1])

    total_sum = compute_sum(picks)
    print("The sum of the picked cards is:", total_sum)

    if total_sum == 24:
        print("Congratulations! You have picked cards that yield the sum of 24.")
    else:
        print("Sorry, the sum of the picked cards is not 24.")

play_game()
```

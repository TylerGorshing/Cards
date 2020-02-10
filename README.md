# Cards
A exercise in learning OOP in Python

## About the Project

As I continued to learn more and more about programming, I discovered the concept of object oriented programming and decided it would be worth my time to learn those concepts in Python more thoroughly. This project was a fun exercise in just that.

Programing a deck of cards in python is a great way to learn some of the concepts of OOP. A single playing card has two main attributes: suit and value. A deck is composed of 52 card objects and can have various methods like shuffling the deck or drawing a card from the top of the deck. I was even able to use inheritance, magic methods, and property decorators in this exercise.

I don't really know if what I've done is the best or most conventional way of OOP in python, but it's functional.

## Learning Goals

Primarily, I wanted to learn how object oriented programming works in python. My goals were as follows:

- Familiarize myself with creating objects and using instances in a python program
- Understand the syntax and process of defining a custom class and its behavior
- Modify the behavior of a custom class using the __init__() method and other magic methods in python
- Use inheritance to better organize my code

## About the Code

The code for this little program isn’t too complicated. There are a few custom classes each with their own instance varibales and attributes.

### The Card Class

*class* `cards.Card(value, suit, hidden=False)`

This class represents a standard playing card. The card can also be hidden from view if needed.

Example:

    >>> from cards import Card
    >>> card = Card(1, 'Spades') # An ace of Spades 
    >>> card.show()
    Ace of Spades
    >>> card.hidden = True
    >>> card.show()
    This card is hidden.


Parameters:
- **value** (int) - The value of the card. For a standard deck of playing cards, 1 is ace, 11 is Jack, 12 is Queen, and 13 is King.
- **suit** (str) - The suit of the card. Generally, the four suits are `'Spades'`, `'Hearts'`, `'Diamonds'`, and `'Clubs'`.
- **hidden** (bool) - If `False` (the default), details aobut the card can be printed to the screen. If `True`, the information about the card cannot be printed to the terminal.

`show()`

Prints information about the card to the terminal. If `hidden` is False, prints the value and the suit of the card. If `hidden` is True, this methond prints 'This card is hidden.' to the terminal.

**changeHidden**(*hidden=none*)

Changes the value of `hidden`. 

Returns the same card instance that called the method

Parameters:
- **hidden** (bool) - The value that `hidden` is changed to. If `None`, flips to the opposite value.

**Other Notes:**

This class also implements the ordering magic methods. Only the `value` of the card object is used in determining an order.

Example:

    >>> card_a = Card(3, 'Hearts')
    >>> card_b = Card(8, 'Diamonds')
    >>> card_a == card_b
    False
    >>> card_a < card_b
    True
    >>> card_c = Card(3, 'Spades')
    >>> card_a == card_c
    True

### The Collection Class

*class* `cards.Collection(value, suit, hidden=False)`



### The Deck Class

The Deck class describes a deck of playing cards. Because a Deck object inharits from the Collection Class, it only needs two additional methods. One methong, `build`, fills the deck with the 52 standard playing cards. The other method, `reset`, resets the deck with the original 52 playing cards.

## Running the Program

The best way (really, the only way) to interact with this program is using the interactive shell and importing the cards module.

```
>>> from cards import *
```

Once the module in imported, we can create a Card instance and play around a bit.

Note, the `changeHidden` method in the Card class returns the instance that calls it.

```
>>> card = Card(4, 'Hearts')
>>> card.show()
4 of Hearts
>>> card.changeHidden()
<cards.Card object at 0x10ba1fe10>
>>> card.show()
This card is hidden.
```

We can paly around with a Deck object.

```
>>> deck = Deck()
>>> deck.show()
Ace of Spades
2 of Spades
3 of Spades
4 of Spades
5 of Spades
6 of Spades
7 of Spades
8 of Spades
9 of Spades
10 of Spades
Jack of Spades
Queen of Spades
King of Spades
Ace of Hearts
2 of Hearts
3 of Hearts
4 of Hearts
5 of Hearts
6 of Hearts
7 of Hearts
8 of Hearts
9 of Hearts
10 of Hearts
Jack of Hearts
Queen of Hearts
King of Hearts
Ace of Diamonds
2 of Diamonds
3 of Diamonds
4 of Diamonds
5 of Diamonds
6 of Diamonds
7 of Diamonds
8 of Diamonds
9 of Diamonds
10 of Diamonds
Jack of Diamonds
Queen of Diamonds
King of Diamonds
Ace of Clubs
2 of Clubs
3 of Clubs
4 of Clubs
5 of Clubs
6 of Clubs
7 of Clubs
8 of Clubs
9 of Clubs
10 of Clubs
Jack of Clubs
Queen of Clubs
King of Clubs
>>> deck.hide()
>>> deck.show()
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
This card is hidden.
>>> deck.shuffle()
>>> deck.reveal()
>>> deck.show()
Ace of Hearts
3 of Spades
10 of Diamonds
Queen of Hearts
Jack of Hearts
3 of Diamonds
King of Diamonds
Queen of Clubs
5 of Diamonds
3 of Hearts
5 of Clubs
Ace of Spades
King of Clubs
10 of Clubs
4 of Spades
Ace of Clubs
2 of Clubs
4 of Clubs
Jack of Diamonds
8 of Diamonds
2 of Diamonds
6 of Diamonds
5 of Spades
4 of Hearts
7 of Spades
9 of Diamonds
7 of Hearts
Queen of Spades
2 of Hearts
King of Spades
9 of Spades
Queen of Diamonds
6 of Clubs
4 of Diamonds
Jack of Spades
Jack of Clubs
8 of Spades
9 of Hearts
3 of Clubs
6 of Spades
8 of Clubs
2 of Spades
7 of Diamonds
9 of Clubs
10 of Hearts
Ace of Diamonds
10 of Spades
8 of Hearts
King of Hearts
5 of Hearts
6 of Hearts
7 of Clubs
>>> 
```
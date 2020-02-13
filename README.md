# Cards
An OOP learning exercise in Python.

### About the Project

As I continued to learn more and more about programming, I discovered the concept of object oriented programming and decided it would be worth my time to learn those concepts in Python more thoroughly. This project was a fun exercise in just that.

Programing a deck of cards in python is a great way to learn some of the concepts of OOP. A single playing card has two main attributes: suit and value. A deck is composed of 52 card objects and can have various methods like shuffling the deck or drawing a card from the top of the deck. I was even able to use inheritance, magic methods, and property decorators in this exercise.

### Learning Goals

Primarily, I wanted to learn how object oriented programming works in python. My goals were as follows:

- Familiarize myself with creating objects and using instances in a python program
- Understand the syntax and process of defining a custom class and its behavior
- Modify the behavior of a custom class using the `__init__()` method and other magic methods in python
- Use inheritance to better organize my code

### How to Improve

Like with any learning project, my skills improved significantly while working on this program, and as such, I can see many areas with flawed code that may or may not create bugs, places where I didn't follow proper conventions laid out in PEP8, or structural flaws that limit how the program can be scaled for use in other applications. 

All that being said, my goal was not to create a *perfect* program, but rather use the concepts of OOP in python to make a *functional* program, and that's exactly what I've done. I could spend more time on this program making it come closer to perfection, but I've decided to use what I've learned and move on to other projects.

# About the Code

The code for this little program isn’t too complicated. There are a few custom classes each with their own instance variables and attributes.

## The Card Class

This class represents a standard playing card. The card can be hidden from view if needed.

### *class* `cards.Card(value, suit, hidden=False)`

Parameters:
- **value** (int) - The value of the card. For a standard deck of playing cards, 1 is Ace, 11 is Jack, 12 is Queen, and 13 is King.
- **suit** (str) - The suit of the card. Generally, the four suits are `'Spades'`, `'Hearts'`, `'Diamonds'`, and `'Clubs'`.
- **hidden** (bool) - If `False` (the default), details about the card can be printed to the screen. If `True`, the information about the card cannot be printed to the terminal.

#### `show()`
Prints information about the card to the terminal. If `hidden` is False, prints the value and the suit of the card. If `hidden` is True, this method prints 'This card is hidden.' to the terminal.

#### `changeHidden(hidden=none)`
Changes the value of `hidden`. Returns the same card instance that called the method


### Other Notes
This class also implements the ordering magic methods. Only the `value` of the card object is used in determining an order. See examples below.

### Examples:

Creating and using a card object:
```
>>> from cards import Card
>>> card = Card(1, 'Spades') # An ace of Spades 
>>> card.show()
Ace of Spades
>>> card.hidden = True
>>> card.show()
This card is hidden.
```

Implementing the ordering methods:
```
>>> card_a = Card(3, 'Hearts') # 3 of Hearts
>>> card_b = Card(8, 'Diamonds') # 8 of Diamonds
>>> card_a == card_b
False
>>> card_a < card_b
True
>>> card_c = Card(3, 'Spades') # 3 of Spades
>>> card_a == card_c
True
```

## The Collection Class

This class is a parent class for any object whose purpose is to hold cards, for example, a deck of playing cards or a player's hand in a card game.

### *class* `cards.Collection(cards=None, replacement=False)`

Parameters: 
- **cards** (list or None) - A list of playing cards held by the Collection object. If `None` (the default), then the Collection object is initialized with an empty list to be filled with cards at a later time.
- **replacement** (bool) - Determines if cards are drawn from the collection with or without replacement. If `False` (the default), then cards are drawn without replacement. Cards are drawn with replacement if `replacement` is set to `True`.

#### `cards`
A list of playing card objects. 

#### `discard()`
Empties the `cards` list. If there are no more references to any of the card objects, I think they're garbage collected by python.

#### `draw()`
Returns a card object from the `cards` list. If `replacement` is set to `False`, the first card object in the `cards` list is removed and that card is returned. If `replacement` is set to `True`, a random card in the `cards` list is returned *without* removing it from the list.

#### `hide()`
Sets the `hidden` attribute for every card in the `cards` list to `True`.

#### `reveal()`
Sets the `hidden` attribute for every card in the `cards` list to `False`.

#### `show()`
Prints information about each card object in the `cards` list. This calls the `show()` method on each card object.

#### `shuffle()`
Randomizes the order of the `cards` list. This is like shuffling a deck of cards.

### Other Notes
This class also defines the `len()` magic method as well as the `+` operation. See the Deck class for examples. 

## The Deck Class

A standard deck of 52 playing cards. This class extends the `Collection` class, and includes all the attributes from its parent.

### *class* `cards.Deck(cards=None)`

Parameters:
- **cards** (list or None) - A list of playing cards to be placed in the Deck at construction. If `None` (the default), the deck is constructed with the standard set of 52 playing cards.

#### `build()`
Adds the 52 standard playing card objects to the deck *without* removing any cards already in the deck. To remove the cards already in the deck, see the `reset()` method. This method is called at construction of a new deck object if the `cards` parameter is `None`.

#### `reset()`
Resets the deck object to a standard deck of 52 playing cards. This removes all card objects from the deck then fills the empty deck with 52 playing cards.

### Examples
```
>>> from cards import *
>>> deck_a = Deck() # the deck object starts with 52 playing cards
>>> len(deck_a)
52

>>> deck_a.show()
Ace of Spades
2 of Spades
3 of Spades
...
10 of Clubs
Jack of Clubs
Queen of Clubs
King of Clubs

>>> deck_a.shuffle() # the deck can be shuffled
>>> deck_a.show()
6 of Clubs
8 of Diamonds
7 of Hearts
3 of Spades
...
10 of Hearts
4 of Spades
6 of Spades
3 of Clubs

>>> deck_b = Deck()
>>> deck_b.hide() # all the cards in a deck can be hidden
>>> deck_b.show()
This card is hidden.
This card is hidden.
...
This card is hidden.
This card is hidden.

>>> deck_c = deck_a + deck_b # adding two decks together returns a third deck
>>> len(deck_c)
104

>>> deck_c.shuffle()
>>> deck_c.show() # The cards from deck_b are still hidden
This card is hidden.
This card is hidden.
7 of Spades
This card is hidden.
...
8 of Spades
4 of Spades
This card is hidden.
This card is hidden.
```

# Cards
A exercise in learning OOP in Python

## About the Project

As I continued to learn more and more about programming, I discovered the concept of object oriented programming and decided it would be worth my time to learn those concepts in Python more thoroughly. This project was a fun exercise in just that.

Programing a deck of cards in python is a great way to learn some of the concepts of OOP. A single playing card has two main attributes: suit and value. A deck is composed of 52 card objects and can have various methods like shuffling the deck or drawing a card from the top of the deck. I was even able to use inheritance, magic methods, and property decorators in this exercise.

## Learning Goals

Primarily, I wanted to learn how object oriented programming works in python. My goals were as follows:

- Familiarize myself with creating objects and using instances in a python program
- Understand the syntax and process of defining a custom class and its behavior
- Modify the behavior of a custom class using the __init__() method and other magic methods in python
- Use inheritance to better organize my code

## About the Code

The code for this little program isn’t too complicated. There are a few custom classes each with their own attributes and methods.

### The Card Class

The first class defined in the program is the Card class. As the name implies, the Card class defines a playing card. Each card has a suit and a value, and can be visable to players or hidden from view. This class uses non-public variables that are accessed with the `@property` decorator and are madified with a setter. I don't think using the property decorator is necessary (or even optimal in this case), but I wanted to try it here.

There are two custom methods. The first changes the hidden state of the card (kind of like revealing a face-down card to all players), and the second prints information about the card to the terminal.

Lastly, the class uses magic methods to define an order so that different instances can be compared.

### The Collection Class

I wanted to use inharitance in this excercise, so the Collection class is meant to be a base class for anything that holds Card objects, ie. a deck of cards. When designing this class, I tried to keep everything as general as possible. There are a few methods that can be used on any set of cards such as shuffling the order of the cards or revealing all the cards to a player.

This is the parent class for a Deck object, and is also subclassed in other projects I've worked on.

### The Deck Class

The Deck class describes a deck of playing cards. Because a Deck object inharits from the Collection Class, it only needs two additional methods. One methong, `build`, fills the deck with the 52 standard playing cards. The other method, `reset`, resets the deck with the original 52 playing cards.


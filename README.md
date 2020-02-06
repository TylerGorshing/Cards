# Cards
A exercise in learning OOP in Python

## About the Project

As I continued to learn more and more about programming, I discovered the concept of object oriented programming and decided it would be worth my time to learn those concepts in Python more thoroughly. This project was a fun exercise in just that.

Programing a deck of cards in python is a great way to learn some of the concepts of OOP. A single playing card has two main attributes: suit and value. A deck is composed of 52 card objects and can have various methods like shuffling the deck or drawing a card from the top of the deck. I was even able to use inheritance, special methods, and property decorators in this exercise.

## Learning Goals

Primarily, I wanted to learn how object oriented programming works in python. 

Familiarize myself with creating objects and using instances in a python program

Understand the syntax and process of defining a custom class and its behavior

Modify the behavior of a custom class using the __init__() method and other special methods in python

Use inheritance to better organize my code

## About the Code

The code for this little program isn’t too complicated. 

First, we see the Card class is defined. It has a couple parameters required when making a new instance and a third attribute determining if the card is visible or hidden. There are a few @property decorators and with setters for data encapsulation, and a bit further down, I defined some special functions such as __eq__() and  __le__() for the Card class to define equality and an order.

The next class I’ve defined is a 
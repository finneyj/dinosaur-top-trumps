# SCC.111: Term 2 Assessment Task: Dinosaur Top Trumps!

## Introduction

Imagine you are part of a software development team developing a Java version of the popular **Top Trumps card game**. You and your colleagues have been contracted to develop a digital version of the game using the Swing graphical package.

The work was due to be delivered to your customer in the SCC1x1 lab next week. Your team had completed the work, but one of your junior colleagues who developed some of the software for the project has suffered a minor accident and his laptop was eaten by a giant worm on Arrakis. He failed to use version control for the project (you would never do that right?), so now three of the core Java classes required to deliver the product have been lost.

**It is now up to you to complete the project by rewriting these three classes before the deadline in your SCC1x1 lab next week.**

## Top Trumps Rules

Top Trumps is simple, very popular card game for children. It consists of a set of cards that identify object within a theme (e.g. cars, animals, etc). Each card represents a single item, such as a Ferrari F40 or Great White Shark. The cards also include numerical attributes about that object, such as its acceleration or length. All the cards in a deck contain the same attributes, but, obviously, some cards are better than others… A Ferrari is faster than a Kia, and a Great White Shark is longer than a goldfish!

The game is for two players, each of which holds a deck of cards. They secretly each take the top card from their deck in turn, and one player chooses a category. The player with the highest value in that category wins both cards, and they are added to that players deck. If both cards have the same value, the player who did not choose the category wins the cards. Whoever wins the cards also gets to choose the category for the next round. Play continues until one player has all the cards… then they are declared the winner.

If you are unfamiliar with the game, you can play an online version here: 
[https://www.supercarworld.com/cgi-bin/setuptrumps.cgi](https://www.supercarworld.com/cgi-bin/setuptrumps.cgi)

Top Trumps rules are available here:
[https://toptrumps.com/pages/how-to-play-top-trumps](https://toptrumps.com/pages/how-to-play-top-trumps)

## The Task

Your task is to complete the implementation of the Top Trumps software, by implementing the missing classes. Once completed, you should have a working Top trumps game, much like the following:

![alt text](https://i.imgur.com/M9IKZMG.png)

**Luckily, a complete version of the most complex of the classes have survived.** Clone the following repo to get all the Java code that is left of the project.

```bash
git clone https://scc-source.lancs.ac.uk/scc.Y1/scc.111/Week19
```

In the repo you will find two java classes. **TopTrumps and PlayerWindow**. ***These two classes are complete. You are not permitted to change them in your solution.***

**TopTrumps**. This class contains an implementation of the Top Trumps game rules, and the names and attributes of the cards to be used – in this case, the cards are all about dinosaurs. It also contains the `main()` method for the application. p.s. Did you know the person who created the term “Dinosaur”, Sir Richard Owen, came from Lancaster?

**PlayerWindow**. This class creates a graphical user interface for a player. It creates a window that can show the name and picture of a dinosaur and list that dinosaur’s attributes. It also allows the relevant player to choose the category to compare in that round. 

***You may wish to review and analyse these classes to understand how they operate. Remember that no changes are permitted to the TopTrumps and PlayerWindow classes.***

Unfortunately, the **Category**, **Card** and **Player** classes have been lost. You are required to rewrite these to the following specification, such that they combine with the **TopTrumps** and **PlayerWindow** classes to create a complete solution. The three sections below define the work needed for each of these classes…

**Category**
-	Create a class called `Category` to represent a single category of a Top Trumps card (such as speed, or weight). 
-	Create two attributes in your `Category` class, to represent the `name` and `value` of the category. The name is simply a piece of text, and the value is a whole number with no fractions. *Remember that attributes should not be directly visible from outside the class*.
-	Create a *constructor* method that initializes these attributes to the values provided by two parameters to the constructor (name and value, **in that order**).
-	Create *accessor* methods for both of these two attributes (`getName` and `getValue`).

<br><br>

**Card**
-	Create a class called `Card` to represent a Top Trumps card (such as a T-Rex). 
-	Create two attributes in your `Card` class. One should represent the `name` of the dinosaur. The other should be an array of type `Category`, that holds the name and value of each category for that card. Each card contains five categories.
-	Create a constructor method that takes the `name` of the card and its category values as parameters (speed, weight, era, legs, wings) **in that order**. Your constructor should initialise all the attributes in the class, and the relevant entries in the array.
-	Create an accessor method for the name of the card.
-	Create a method called `getCategory` that takes a string as a parameter. The method should return the `Category` object matching the given name in the array.
-	Create a method called `isBetterThan`. This method should take another `Card` and the `name` of a category as its parameters, in that order. The method should return true if the card’s value for the given category is strictly higher than the equivalent in the Card given as a parameter. The method should return false otherwise.
<br><br>

**Player**
-	Create a class called `Player` to represent a user playing Top Trumps.
-	This class should contain an *array* of `Card` objects as an attribute. You may also add any further attributes you feel useful.
-	Create a *constructor* matching the expectation of its use in the TopTrumps class.
-	The class should contain an `addCard` method that takes a single `Card` as its only parameter. *This should be added to the first available non-null slot in the array*.
-	The class should contain a `removeCard` method that takes a single `Card` as its only parameter. If present in the array, this Card should be *removed from the array* and *replaced by a null value*.
-	You should also write *accessor* method called `getCardCount` that returns the number of non-null cards in the array, and `getPlayerName` which simply returns the name of the player.
-	Write a `nextCard` method that takes no parameters and selects the next non-null card from the player’s deck. Remember that this should be one further into the array than the last card used by that player. If the end of the array is reached, it should start again at the beginning of the array.
-	Write a `getCurrentCard` method that takes no parameters and returns the `Card` that is currently being used by the player.
-   Write a boolean `hasWon` method that returns `true` if the current cards count the player has is equal to the total cards count, otherwise it returns `false`.

**Submission**

You will submit your work during the end of term on-lab quiz in Week 20. Ensure you keep your work safe until then. 

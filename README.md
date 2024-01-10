# Mellow rain
 > Authors: [Austin Yang](https://github.com/Toona114),
 >          [Zain Ashraf](https://github.com/zain-ashraf),
 >          [Brandon Paulsen](https://github.com/Poly1581),
 >          [Jimmy Delgado-Hernandez](https://github.com/Maker424)

## Project Description
 > Our group project is a text-based RPG game that utilizes only text to interact with the game with no visuals. Our game is called "Mellow Rain" and you are fighting three bosses that get progressively harder. You will have to either attack, guard, or heal to slowly beat all three bosses or give up if odds were against you.
This project is interesting for us because we all have interest in video games and played through turn based games at least once in our life. By being able to create a project in creating our own text-based RPG game, we're interested in learning how the inside and behind the stage concept for how these games are planned and executed and what hidden problems and situations we might encounter and resolve through creating our own version.
 > The project will be put together in the programming language of C++ utilizing the strategy pattern.
 > The input for our projects will be user's decisions on what ability/move they want to utilize per turn while our output will be a text summary of what the aftermath of the user's input resulted in in addtion to boss's attack summary.

 ## Phase II
## Class Diagram
![Copy of project UML-2](https://cdn.discordapp.com/attachments/961506732679503932/982401685936812082/Copy_of_project_UML.jpeg)




## Class Description
As a player, I want to choose a character so I can play as them throughout the game.

As a player, I want to heal so I can have more health.

As a player, I want to be able to see how much damage each weapon can do so I can choose one to attack others.

As a player, I want to attack my enemy so I can decrease their health.

As a player, I want to block myself so I can avoid damage.

As a player, I want to be given an option to block an attack so I can avoid damage.

As a player, I want to be given the option to run away so I can quit the game.

The TextDisplay class functions as the main entry point into the game.  It initializes the character with the name input by the user and has the logic to progress through the boss states iteratively taking turns between the boss and the user.  The TextDisplay has two internal pointers to Character objects - one for the boss and one for the player.

The Character class functions to keep all methods for an individual character together.  It keeps track of max health, current health, attack and heal objects and other stats associated with the class.  It also functions as the method to display the character stats.

The health class acts as a common interface for all concrete healing classes.  These classes include healRange (which heals the player for a value within a range) and healValue (which heals for a specific value) - both of which inherit from the heal interface.  Right now, heal objects are set by the TextDisplay class at runtime, but it might be more useful in the future to have them associated with individual items in an inventory system.

The attack class functions similarly to the health class in that it is a common interface for all attacking classes.  These classes include AttackRange (which acts similarly to the healRange class) and attackValue (which acts similarly to the healValue class).

The character class aggregates heal and attack classes while the textdisplay aggregates the character class.


More in-depth
Ideas:
Character
Class/Attributes
Enemies

Actions
->Attack
->Block (if there’s time)
				->Don’t want to do 100% damage education because that would just make it so you can just defend 24/7
				->Don’t want to do just damage education because you’ll just want to attack no matter what then
->Heal
->Run



 ## Phase III
 ## Design Pattern: 
Strategy Pattern
>We will use Strategy Pattern so we can have one main class where we call other functions to create the flow of the game. By utilizing Strategy Pattern, we are able to modify individuals functions (attack, heal, and blocking) to do different things when it's called by main.
-We picked the Strategy design pattern to make our lives easier in the long run. We have strategies and want to be able to implement them easily without extending our program.
 -Strategy (behavioral) design pattern - We don't actually have to write out multiple functions, we can just write multiple classes to change the behavior and add different moves if necessary (as just a class). If we change any of the methods, we dont have to recomiple the entire program, just that one class.
 
 ## Screenshots
  ![p1](https://cdn.discordapp.com/attachments/961506732679503932/982116806653267988/1.JPG)
  ![p2](https://cdn.discordapp.com/attachments/961506732679503932/982116806875561994/2.JPG)
  ![p3](https://cdn.discordapp.com/attachments/961506732679503932/982116807156572170/3.JPG)
  ![p4](https://cdn.discordapp.com/attachments/961506732679503932/982116807450189824/4.JPG)
 ## Installation/Usage
To run the game, clone the repository and compile with Cmake3 ., make, then ./CS100_PROJECT.
To play the game, you'll first have to input a name and an appropriate age. Afterwards you choose moves to either attack, block, or heal to defeat 3 bosses. If you want to give up mid game, you can press 0 to give up.

 ## Testing
Testing was done using the google test framework to establish proper functionality of the main classes and their interaction with eachother.  Continuous Integration was not used, as professor Reem indicated that it might not work properly given that this is a CS100 github associated with the school github.
 

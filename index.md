# Introduction: LCR
The artifact we are working on for the ePortfolio is the dice game application, Left-Center-Right, developed in IT-312 last semester here at SNHU. This artifact was developed independently at my own choice in one of my final programming courses. I chose this item because I saw all the room for improvement while developing it and everything is still fresh in my mind. 

## Software Engineering / Design
My selected artifact to display my software engineering skills will be the dice game, Left Center Right, developed in IT-312 here at SNHU. 
My enhancement plan is to implement a state machine to run the game. Currently, the main loop is very linear, running through all the different states of the game. However, what I would ideally like to do is fire up a state machine that would take over managing the game and its states. This would also allow me to also add new game states in a modular manner. 
```
Class StateMachine:
	Property _state
	Function ExecuteState():
		_state.Execute()
	Function ChangeState():
		If ready for new state
			_state = new State //overridden version appropriate for current game
Abstract Class State
	Abstract Function Execute():
		Implement logic unique to each state here
```
This will allow me to display my ability to design a new feature for an existing product and the ability to implement an advanced game feature.

## Algorithms and Data Structures
My selected artifact to display my Algorithm and Data Structure skills will be the dice game, Left Center Right, developed in IT-312 here at SNHU.
My enhancement plan is to change how we move between players to resolve their turns. Currently, we iterate over a defined player count. However, I would like it more if the player objects were contained within a linked list. This would allow us to just keep repeating the same game state as long as another player exists, without knowing how many players there are. Multiple items will likely need to be adjusted for this, such as displaying score between rounds. 
```
Class Player:
	Define Player Properties
	Hold pointer reference to next player object or null
```
This will allow me to display my ability to implement more complex data structures.

## Databases
My selected artifact to display my database skills will be the dice game, Left Center Right, developed in IT-312 here at SNHU.
My enhancement plan is to add a database to track players and their high scores. This is intended to build on top of the new state machine addition.
```
Class StateSaveScores:
	Function Execute():
Connect to DB
		Add data to DB
		Close DB Connection
		
Class StateDisplayHighScores():
	Function Execute():
		Connect to DB
		Retrieve data from DB
		Close DB Connection
		Display formatted data

This will allow me to display my ability to implement a DB within an existing program. 
```

<iframe width="560" height="315" src="https://www.youtube.com/embed/x8v8Zsadk3Q" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# Narrative
## Software Engineering
I was able to meet the program enhancements listed in Module One. This would be that we were changing the man game loop over to a state machine to handle processing and logic. The process of enhancing this was very difficult. Due to the nature of the changes I was making, many lines of code were written without compiling. This left lots of little errors littered about by the time I was able to first compile. Mostly this was how I was accessing object properties through the use of pointers. 

This biggest challenge I faced though was a circular dependency between header files. This was between the Player Turn state and the Print Score state, as we switch back and forth between these states at some point. It took me a long time to uncover this issue, due to the ambiguous nature of the error received (some kind of type not defined error). Ultimately, I ended up resolving it by adding a property to the state machine that allowed me to store a reference to a single circular state to prevent errors from occurring. 

## Data Structures & Algorithms
I was able to meet the program enhancements listed in Module One. This would be that we converted the Players array over to a linked list of players. This process touched many different files, seeing as any place a player was referenced/accessed needed to be updated. The logic flow for determining how we rounded from the last player back to the first player needed adjustment as well. 

We did this by having the Game Manager hold references to the first player, last player, and current player. While we could have skipped holding the reference to the last player and just traversed our linked list until the last player, doing so would have increased computational cost. Each player, except for the first and last, held references to both the player before and after them. 

The challenges I faced while working on this largely pertained to working with pointers, empty pointers, and semantic errors. While working with pointers, sometimes it is hard to understand why we only receive errors on only Player 3. A simple semantic error can prevent you from traversing the list and initializing properly.  

## Database
I was unable to fully meet the program enhancements listed in Module One. This would be that we implemented a full database connection to track players and their high scores. While investigating the implementation of a database in C++, I became worried about portability and the scale of my design. Instead, I transitioned to a flat file (.csv) and just performed simple read/write operations on that table.

This enhancement allowed me to uncover the flaws I made in my design. Having worked in more expressive languages, I made assumptions as to the scope of work. However, I was able to increase my adherence to the single responsibility paradigm and did provide a minimum viable product that meet the use case of providing a way to track high scores. 

The challenges I faced while working on this largely pertained to where within the flow of logic this piece belonged. While originally, I had planned to make a new state to track high scores, I had found the Game Over state to be rather empty and a fitting place to develop. I also had to make minor improvements to the main menu code to provide a cleaner implementation of the new menu item.  


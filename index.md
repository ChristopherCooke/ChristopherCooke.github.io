The artifact we are working on for the ePortfolio is the dice game application, Left-Center-Right, developed in IT-312 last semester here at SNHU. This artifact was developed independently at my own choice in one of my final programming courses. I chose this item because I saw all the room for improvement while developing it and everything is still fresh in my mind. 

Software Engineering / Design
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
Algorithms and Data Structures
My selected artifact to display my Algorithm and Data Structure skills will be the dice game, Left Center Right, developed in IT-312 here at SNHU.
My enhancement plan is to change how we move between players to resolve their turns. Currently, we iterate over a defined player count. However, I would like it more if the player objects were contained within a linked list. This would allow us to just keep repeating the same game state as long as another player exists, without knowing how many players there are. Multiple items will likely need to be adjusted for this, such as displaying score between rounds. 
```
Class Player:
	Define Player Properties
	Hold pointer reference to next player object or null
```
This will allow me to display my ability to implement more complex data structures.
Databases
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

<video width="320" height="240" controls>
  <source type="video/mp4" src="https://robocop79.github.io/Websiteland//Twitter/FLT.mp4">
</video>

<div class="embed-container">
  <iframe
      src="https://www.youtube.com/embed/kzVzDIh2_mU"
      width="700"
      height="480"
      frameborder="0"
      allowfullscreen="">
  </iframe>
</div>


## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/ChristopherCooke/ChristopherCooke.github.io/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/ChristopherCooke/ChristopherCooke.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

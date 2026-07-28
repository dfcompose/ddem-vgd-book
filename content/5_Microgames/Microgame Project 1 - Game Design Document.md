
Now that we've explored what the Godot game engine has to offer, it's now your turn to design and develop your own game! Well, your own micro-game! A microgame is a single mechanic game that lasts roughly five seconds maximum. For this project you will create one microgame of your own design which will then be collected into one microgame collection for the entire class. But before you jump into the engine you'll first need to create a game design document.

For this project your game *must* include the following:

* A win condition (how does your player win your game)
* A lose condition (How your player loses your game)
* Animation
* Sound

Your game is also limited to:

* A total of 5 seconds. Your player can lose or win by running out of time but you cannot use more than 5 seconds of time.
* You can only use the arrow keys ("ui_left", "ui_right", "ui_up", "ui_down") and spacebar ("ui_accept").

## Game Design Document

A game design document is a written document detailing all aspects of your game. This document should be written in a clear and readable language. The game design document should be detailed enough that you could give the document to a team and they would be able to create your game from it. No two game design documents are exactly the same though. Below is a basic template of a game design document:

### General Info

Project Name:
Project Team:
Genre:
Aesthetic:
Graphics:

Overview: This should be a short description of your project (3-5 sentences). This should include descriptions of what your game is, why someone would be interested in it.

Gameplay: How will your game play? This should be a short description, more detail will come later.

### Entities and Story

Story Synopsis: Does your game have a story? If so, you would describe the basic story beats here. For example: John is a janitor that falls into a portal that takes him to a magical world. He meets a group of adventurers that ask him to join them on their quest to defeat the Dark Lord Craig. Using his janitorial know-how, can John help the adventurers defeat the Dark Lord Craig and find his way home?

This section would include player characters, NPCs, opponents, or any other entity in your game. This should include descriptions of who the characters are, what they can do, and what they look like. This section should be as long as 

### Mechanics

Here you will list the mechanics of your game. These should be *thorough* and should include pseudo-code. Each mechanic should have a written explanation, drawing, and pseudo-code. This is also where you may write out a finite state machine graph before you start working in the engine. Here is an example for jumping:


```handdrawn-ink
{
	"versionAtEmbed": "0.3.4",
	"filepath": "Ink/Drawing/2025.11.20 - 21.45pm.drawing",
	"width": 500,
	"aspectRatio": 1
}
```

The player can jump when they are on the ground and press the space key. This makes the player's y velocity a large negative number for a single frame. 

pseudo-code:

```
var jump_power = -400

if on the ground and the player presses space:
	set y velocity = jump_power
```


### Game States and Levels

Here you will define the different states for your game. This should include things like menus, levels, or any other screen your player may encounter. This should include how you move between each scene and what happens in the scene. Use drawings and descriptions here.

### Audio

Here you will explain the audio you will use in your project. What will have sound effects? What will those sound effects be? You can link to the sounds you want to use here. Describe when the sounds would happen.
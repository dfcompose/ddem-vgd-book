---
title: Game States
weight: 3
---

In this section, we'll start implementing our *game states* and discuss what a *game state* is. 


Now that we've gotten our core **Mechanic** functioning properly, let's turn our attention to some other aspects of our game. We previously mentioned the term *game state* in this project but haven't expanded on it yet. We can think of a *state* as a set of rules for how our game will *act*. Our game may have many different possible *states*, but it can only ever be in <ins>one</ins> *state* at a time. For this game we'll have three different *states*:

- "start": The opening screen
- "playing": When the player is actively playing the game
- "gameover": When the game ends

Take some time to discuss what each *state* might entail. What can the user do in each state? Why might it be useful to separate these into *states*? When and how might these *states* change? What should happen when the *state* changes?


<details style="background-color:rgba(92, 184, 92, 0.25);">
<summary style = "cursor:pointer">Reveal Answer</summary>

- "start"
- - In this state, the user should not be able to move or see the *Player*. There should be background music. The score should be set to 0 in this state and not increase. There should be a button for them to press to change the *state* to "playing". When the *state* changes to "playing" the music should stop.
- "playing"
- - In this state, the user should be able to move the player and collect the collectibles and increase their score. There should be different music playing in this section. The player should not be able to exit the play area. After 30 seconds the *state* should change to the "gameover" state and the current music should end.
- "gameover"
- - In this state, the player should no longer be able to collect anything or increase their score. The current score should be displayed to the player as well as their high score. Ending music should play. There should be a button that allows the player to start the game back over.

</details>




Topic - Game States
Lesson - Basket Catch: Game States
Goals
* Separate the actions of the game into separate *states*
* Implement states in the Basket Catch game
* 
Outcomes
* Three distinct states in the Basket Catch game
* Transitions between each state
* 
Content and Standards alignment
Topic
Topic
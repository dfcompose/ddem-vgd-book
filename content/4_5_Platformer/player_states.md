# The Finite State Machine

Game logic can become extremely complex with many different systems running and interacting simultaneously. One way to help organize our logic is to use a coding pattern called a **Finite State Machine**. 


## Our Player's States

* Running
* Jumping
* Falling
* Damaged


Let's start by doing some game design. Think about the actions the player can take in each state, what should they be able to do, what's happening, and how do they transition into the state. Let's start with running:

### The Running State

In this state, our player is on the ground and can move left and right at a fixed speed. The player does this by pressing either the left input or the right input. If the player is "powered up", they can also create projectiles to defeat enemies. The player's "run" animation is played when velocity != 0 and the "idle" animation is played when velocity == 0

The player exits this state in one of the following ways:
* Pressing the "jump" key -> Jump state
* Coming in contact with an enemy -> Damage state
* Is no longer on the ground but did not jump -> Falling state

Notice that in this description we do not mention how the other states will work, only how we may transition to them.


### The Jumping State

In this state, our player will have an initial force applied and rise through the air. The player can move left and right in this state. If the player is "powered up" they can also create projectiles to defeat enemies. The player's "jump" animation is played.

The player exits this state in one of the following ways:
* Landing on the ground -> Running state
* The player's y velocity becomes positive (they are moving downward) -> Falling
* The player comes in contact with an enemy -> Damage state


### The Falling State

In this state, the player can move left or right while falling through the air. If the player is "powered up" they can also create projectiles to defeat enemies. The player's "fall" animation is played.

The player exits this state in one of the following ways:
* Landing on the ground -> Running state
* The player comes in contact with an enemy -> Damage state

Notice that this state cannot transition to the three other available states. 

### The Damage State

In this state, the player is pushed away from the enemy that damaged it. The player is unable to directly control their player. A timer is started during which the player cannot be damaged again. The "damaged" animation is played.


The player exits this state in the following way:
* After the timer ends -> Falling state

Notice here that we have only one state that the player can move to. This is because the *falling state* covers all scenarios that a player might arrive in after taking damage.



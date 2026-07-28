

Often we'll want to have a script that we can access from anywhere in our project that does not get deleted from scene to scene. This kind of script, often called a **Singleton** or in Godot terms an **Autoload**, is very powerful and allows us to store and manipulate data game-wide. We'll use these kinds of scripts for any multi-stage game, any game with persistent data, and any game that uses UI to communicate the state of the player. Let's start by creating our global script.

We'll create a new script by going to the **FileSystem**, right-click **res://** and selecting *Create New -> Script*. We'll rename this script "Global". Next, we'll go to the **Project Settings** and select the **Globals** tab. Then we'll select our "Global" script by pressing the folder icon next to the "Path" text field. This will open a dialogue where we can select our script. Once we've selected the "Global" script we'll click "+Add" to make the script a **Global** script.

<p align="center">
<video width="640" height="360" autoplay muted loop controls>
    <source src="../../../../media/BasketCatchImages/MakeGlobal/MakingGlobal.mp4" type="video/mp4">
</video>
</p>

We can then open our *Global* script by double clicking the *Global.gd* file in the **FileSystem**. We should see the following code:

```
extends Node


# Called when the node enters the scene tree for the first time.
func _ready() -> void:
	pass # Replace with function body.


# Called every frame. 'delta' is the elapsed time since the previous frame.
func _process(delta: float) -> void:
	pass
```


From here, let's add a variable where we'll store the *Player*'s current score. Set its initial value to 0.


<details style="background-color:rgba(92, 184, 92, 0.25);">
<summary style = "cursor:pointer">Reveal Answer</summary>

```
extends Node

var score = 0

# Called when the node enters the scene tree for the first time.
func _ready() -> void:
	pass # Replace with function body.


# Called every frame. 'delta' is the elapsed time since the previous frame.
func _process(delta: float) -> void:
	pass

```

</details>

Now that we have a place to store this information we'll want to be able to access it. We'll do this by *calling* the *Global* script as if it were an object in our code. That means we can access the **variables** of our script using *dot notation* where the *Global* is the object. So to access the *score* variable we just made we can write: 

```
Global.score
```

 Let's jump over to our *Player* script to implement this. We want to increase the *Player*'s score every time we catch an object. Additionally, we'll add a line of code to print the *Global.score* to the output. How would we do this? What do we need to do to the *Global.score* variable? After you've added this code run your *Main* scene to test that your score increases when you catch an apple.

<details style="background-color:rgba(92, 184, 92, 0.25);">
<summary style = "cursor:pointer">Reveal Answer</summary>


- In our *Player* script, in the *on_body_entered()* **Signal Function**, we'll add the following code:

```
func _on_area_2d_body_entered(body: Node2D) -> void:
	
	body.queue_free()
	Global.score += 1
	print(Global.score)

	pass # Replace with function body.
```
- Remember: The "+=" operator is used for *incrementing* a variable, meaning we're increasing the value stored in *Global.score* by one every time we catch something.

</details>


Now we should be able to update and store our score!

We'll now add another variable to our *Global* script. This will hold the current *game state*, we'll use this to determine when some actions can or can not happen. We'll go back to our *Global* script and add a new variable there. We'll name it *game_state* and set its default value to the **string** *"playing"* (Make sure this is in your *Global* script. If it is in your *Player* script some functionality will not work in the future.)

<details style="background-color:rgba(92, 184, 92, 0.25);">
<summary style = "cursor:pointer">Reveal Answer</summary>

```
extends Node

var score = 0

var game_state = "playing"

# Called when the node enters the scene tree for the first time.
func _ready() -> void:
	pass # Replace with function body.


# Called every frame. 'delta' is the elapsed time since the previous frame.
func _process(delta: float) -> void:
	pass
```

</details>


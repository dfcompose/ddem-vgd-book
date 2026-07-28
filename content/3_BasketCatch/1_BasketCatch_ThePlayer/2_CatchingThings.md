---
title: Catching Things - Area2D and Signals
weight: 2
---

Now that we can control our player and they can't be so easily pushed off the screen, lets turn our attention to catching our falling objects. Here we'll introduce a new node: the **Area2D**. We'll use an **Area2D** any time that we want to be able to monitor if an object is either *entering* or *exiting* a certain location, such as the the *center* of our player. **Area2D**s communicate this by using **Signals**. Whenever a **PhysicsBody** or another **Area2D** *enters* or *exits* an **Area2D** a **Signal** will be sent out. We can connect this **Signal** to any node that has a **Script** attached to it. This allows us to check when *collisions* are happening and run certain code when that happens.

Let's jump over to our *Player* scene. We'll start by adding an **Aread2D** to the root of our scene. We'll see that we have a caution symbol on our **Area2D**, this is because we need to define the *shape* of the **Area2D** using a **CollisionShape2D**. (This will look very similar to how we structure our **PhysicsBodies**) Once you've added your **CollisionShape2D**, select a **Rectangle2D** as its *Shape* in the **Inspector** and place it in the center of your player. Your scene tree and player should look similar to this:

![How your Area2D should look](<../../../media/BasketCatchImages/Area2D and Signals/Area2DSetup.png>)

Now that we have our **Area2D** properly configured and placed we'll need to connect a **Signal** to our *Player* script. We'll do this by clicking on our **Area2D** in the scene tree and then opening the **Node** tab on the **Inspector** dock. This will display all of the **Signals** that the **Area2D** can send:

![All of the Area2D Signals](<../../../media/BasketCatchImages/Area2D and Signals/Area2DSignals.png>)


We see that we have many option for the type of **Signal** to send, but let's think about what we need. Should we send a signal when another **Area** or a **PhysicsBody** enters our **Area2D**? (Hint: Think about what the falling objects are made out of [you can check the "apple" scene to find out]) Do we need to check when the object **Enters** or **Exits** our **Area2D**? Do you see a **Signal** that satisfies both criteria? (You can hover over a **Signal** to get extra information about it.)


<details style="background-color:rgba(92, 184, 92, 0.25);">
<summary style = "cursor:pointer">Reveal Answer</summary>

- The <ins>"body_entered()"</ins> **Signal** is the one we're looking for. It is sent when a **PhysicsBody** *enters* our **Area2D**
- Be careful! "body_shape_entered()" is not the same as "body_entered()". We don't want the *shape* of the **PhysicsBody** but the actual **PhysicsBody** itself. 

</details>

We connect the signal by either double-clicking it or right-clicking and selecting "Connect...". This will open a dialogue that allows us to select the node to *send* the **Signal** to. As stated above, we can only connect a **Signal** to a node that has a **Script** attached to it. In our *Player* scene the only node with a **Script** is the *root* node itself. We'll go ahead and connect the signal there:

![Connecting a Signal](<../../../media/BasketCatchImages/Area2D and Signals/ConnectASignal.png>)

This will generate a new **Function** in our *Player* script. Anything that we put in this **Function** will be ran when our *Player* recieves the **Signal** from the **Area2D**. A few important things to notice about this new **Function**: the new **Function**'s name by default will include the name of the **Signal**, a **Function** that is connected to a **Signal** will have a green box and arrow symbol next to its *declaration*, some **Signals** pass an *argument* into the **Function** (we'll discuss this more in depth in this lesson.).

![The Signal Function](<../../../media/BasketCatchImages/Area2D and Signals/SignalFunction.png>)


We see that the **Signal** passes the argument *body* into our **Function**. This is the **PhysicsBody** that is entering our **Area2D**. Let's add some code to test if our **Area2D** is properly recognizing the **PhysicsBodies** being caught by our *Player*. As always, we'll debug by using the **print()** method. We'll want to print the caught object's *name* property. We'll use *dot notation* to do this. Once you've added the code run your *Main* scene to test it.


<details style="background-color:rgba(92, 184, 92, 0.25);">
<summary style = "cursor:pointer">Reveal Answer</summary>

```
func _on_area_2d_body_entered(body: Node2D) -> void:
	
	print(body.name)
	
	pass # Replace with function body.
```

</details>


We'll notice that some of the apples will output "Apple" while others will output "RigidBody2D@X" this is expected. However, if you have any outputs that read "Player" your **Area2D**'s **CollisionShape2D** is too large and is *colliding* with the *Player*'s *collisions*. Resize your **Area2D**'s **CollisionShape2D** to prevent this from happening. If this isn't perfect don't worry, we'll also add some extra code later to make sure we only register the falling objects.

Now that we can tell when we're catching our objects, let's get rid of them once we catch them. First, let's delete our print statement. Then we'll add some code to remove any **PhysicsBody** that enters our **Area2D**. We'll do this by *calling* the **queue_free()** method on the *body* in our **Signal Function**. Run your *Main* scene to test that you can catch and delete the apples.

<details style="background-color:rgba(92, 184, 92, 0.25);">
<summary style = "cursor:pointer">Reveal Answer</summary>

```
func _on_area_2d_body_entered(body: Node2D) -> void:
	
	body.queue_free()
	
	pass # Replace with function body.
```

</details>


You may notice that your *Player* is deleted if an apple lands on the side of the basket. Don't worry! This is fine for now, we'll fix it later in this lesson. What we're concerned with at the moment is that you can get rid of the apples when you catch them.



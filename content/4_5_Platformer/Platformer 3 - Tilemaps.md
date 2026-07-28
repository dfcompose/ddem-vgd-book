
A 2D platformer may have complex level design with multiple layers, moving elements, enemies, collectibles, and any number of other features. If we needed to painstakingly add these elements by hand (creating new physicsbodies for every unique element) it would take an immense amount of time. Luckily, Godot includes a special node for handling this task: TilemapLayer. Let's first talk about what exactly a Tilemap and a Tileset are.

## Tilesets

A Tileset is an image made up of individual *tiles* that represent all of the graphical elements of the level of our game. Below is an example of a tileset:

![[tileset.png]]

This Tileset includes many images that we can use to "paint" our level with. In this way we can think of a Tileset as the pallet from which we will create our levels.

## TilemapLayer

If a Tileset is our pallet then a Tilemap is our canvas. This Node allows us to apply physics to the tiles, paint them into a scene, organize multiple tilesets, and pretty much anything else we would like to do with them. Let's go through the process of setting up a TilemapLayer:

First, we need to add our Tileset to our TilemapLayer. Like we've done for other Nodes, we will do this in the inspector. First click on your TilemapLayer in the Scene Tree, then find the "Tileset" property, click it, and select "New TileSet":

![[Pasted image 20251028094219.png]]

We can then add the images of our TileSet by going to the bottom of the screen and clicking the TileSet tab. It should look like this:

![[Pasted image 20251028094413.png]]

Then, we can add a new image by clicking the "+" button and selecting "Atlas"

![[Pasted image 20251028094501.png]]

Once we select the image for our TileSet a dialogue box will open, click yes on this to automatically generate tiles for the image:

![[Pasted image 20251028094841.png]]

Congratulations! We now have access to our TileSet in the TilemapLayer! However, there is still some more setup work we need to do. First, we may want things to be able to collide with certain tiles, but not with others. For example, this bridge component below. We would want our player to be able to collide with the floor of the bridge but not any of the railing or upper parts


![[Pasted image 20251028095301.png]]

To do this we need to first add physics to our TileSet. We'll do this by first clicking on our TilemapLayer in the Scene Tree and then clicking on the TileSet property in the inspector. This will open up the TileSet's properties. Here we can see an option for "Physics Layers". We'll click this dropdown and press the "Add Element" button:

![[Pasted image 20251028095541.png]]

This will create a new PhysicsLayer on our TileSet:

![[Pasted image 20251028095622.png]]

Next, we need to assign which tiles will have physics attached to them. We'll do this in the TileSet tab, under the "Paint" section:

![[Pasted image 20251028100047.png]]

Here we'll click "Select a property editor" and select "Physics Layer 0":

![[Pasted image 20251028100131.png]]

Then we can "paint" which tiles will have physics attached to them. Here's the example of the bridge element:

![[Pasted image 20251028100427.png]]

## Adding Tiles to a Scene

Once we've properly set up our entire TileSet we can use it to paint tiles into our Scene using the TilemapLayer. We'll do this by first selecting the "TileMap" tab at the bottom of the screen:

![[Pasted image 20251028100639.png]]

Then, we can select which tiles we want to paint by either clicking on a single tile in the TileMap or a collection of tiles by clicking and dragging in the TileMap:

Selecting one tile:
![[Pasted image 20251028100918.png]]

Selecting multiple tiles:
![[Pasted image 20251028100943.png]]

We can then paint with these tiles by clicking the *Viewport* (Make sure you have your TilemapLayer selected!):

![[Pasted image 20251028101027.png]]

## Adding scenes to a TilemapLayer

Often we will find that we need to add many of the same element to a level. For instance, we may have a coin that the player is able to collect that we want to place throughout our level. Dragging and dropping individual instances from the FileSystem would take a prohibitive amount of time. In this situation we can add the scene to our TilemapLayer's TileSet and draw it just like we would any other tile! We can add a scene to the TileSet in much the same way as we did when we added an image. First, click on the "TileSet" tab at the bottom of the screen, then click the plus button and select "Scenes Collection":

![[Pasted image 20251029222844.png]]

Then, we can drag scenes from the FileSystem to the TileSet to add them:

![[Pasted image 20251029230307.png]]

Finally, we can draw these scenes into our scene in the same way we would tiles. Select the "TileMap" tab at the bottom of the scene, select the "Scene Collection Source" category, select your desired scene, and paint away!

![[Pasted image 20251029230518.png]]

## Using multiple TilemapLayers

It is best to use multiple TilemapLayers to paint different elements. We may want one TilemapLayer for the ground or other static objects our player will stand on, another for purely graphical elements, another for collectibles, and yet another for enemies. 

## Now it's your turn!

In your platformer project complete the following tasks:

1. In your "Collectible" scene, make sure you've added the coin image provided in the platformer asset pack.
2. Add 3 new TileMapLayer Nodes to your "Level 1" scene, name them Tilemap, Collectibles, and Enemies
3. Add a new TileSet to each TileMapLayer and give them the following
	1. Add the TileSet image provided in the asset pack
		1. Make sure to add physics to the tileset
	2. Add the Collectible
	3. Add the Enemy 1 and Enemy 2 scenes
4. Sketch out your level! Make sure to include coins (at least 20) and enemies (at least 3 of each)
5. Add your player to the level
6. Add a "goal" Area2D at the end of your level that changes the scene to level 2
7. Do the same for Level 2, make sure each level is distinct. (Hint: You can copy and paste your TileMapLayers between scenes but make sure you erase all of the tiles before starting fresh)
---
title: File System
weight: 3
---

### The Godot 4 Filesystem

When you work on a project in Godot 4, all of your files and resources are organized in a special structure called the filesystem. Think of it as a virtual organizer where you keep all the things you need for your game. Here’s a simple breakdown:

#### 1\. **Project Root - res://**

-   **What it is**: This is the main folder that contains your entire project. When you create a new project, Godot asks you where you want to save it, and it sets up this root folder for you.
-   **Example**: If your project is named `Doe_Jane_Project1`, then `Doe_Jane_Project1` is your project root.

#### 2\. **Scenes**

-   **What they are**: These are the building blocks of your game. Each scene can be a level, a character, a menu, or any other part of your game.
-   **How to use them**: Save each scene as a `.tscn` file. You might have a scene for the main menu (`MainMenu.tscn`), one for the player character (`Player.tscn`), and another for the level (`Level1.tscn`).

#### 3\. **Scripts**

-   **What they are**: Scripts are pieces of code that control the behavior of your game. They’re like the instructions for what happens in your game.
-   **How to use them**: Save each script as a `.gd` file. For example, you might have a script for player controls (`PlayerControls.gd`) and another for enemy behavior (`EnemyBehavior.gd`).

#### 4\. **Assets**

-   **What they are**: Assets include all the visual and audio elements of your game, like images, sounds, and fonts.
-   **How to use them**: Store these in organized folders. For example, you might have a `textures` folder for images, a `sounds` folder for audio, and a `fonts` folder for text styles.

#### 5\. **Imports**

-   **What they are**: Godot automatically generates import files to optimize your assets. These files help your game run more efficiently.
-   **How to use them**: You generally don’t need to worry about these. Godot handles them in the background.

### Navigating the Filesystem in Godot

-   **FileSystem Dock**: On the right side of the Godot Editor, you’ll find the FileSystem dock. This is where you can see and manage all your project’s files and folders.
-   **Creating and Organizing Folders**: You can right-click in the FileSystem dock to create new folders and organize your files. Keeping your files organized will make it easier to manage your project as it grows.

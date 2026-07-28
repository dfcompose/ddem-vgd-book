---
title: Scene Tree
weight: 4
---
This is the Godot 4 SceneTree.

### The Godot 4 Scene Tree and Node Hierarchy
Imagine building with LEGO bricks. Each brick represents a part of your game. In Godot, these bricks are called **nodes**, and when you put them together in a certain way, you create something called a **scene**. The way these nodes are arranged is called the **scene tree**.

#### 1. **Nodes**: The Building Blocks
- **What are nodes?** Nodes are the basic elements of your game. Each node does something specific. For example, a **Sprite** node displays an image, a **Label** node shows text, and a **Timer** node keeps track of time.
- **Types of nodes**: There are many types of nodes, each with a different function. Some common ones include:
  - **Sprite**: Shows images.
  - **Label**: Displays text.
  - **Area2D**: Detects 2D collisions.
  - **Timer**: Counts down or up.

#### 2. **Scene**: A Collection of Nodes
- **What is a scene?** A scene is like a group of nodes working together to create something bigger, like a level, a character, or a menu. Think of it as a blueprint for a part of your game.
- **Example**: You might have a scene for the main menu of your game, with nodes like buttons, labels, and backgrounds.

#### 3. **Scene Tree**: The Hierarchy of Nodes
- **What is the scene tree?** The scene tree is the structure that shows how nodes are connected in a scene. It looks like a family tree, where each node can have a parent node and child nodes.
- **Hierarchy**: In the hierarchy, nodes are organized in a parent-child relationship. The top node is called the **root node**, and it can have multiple children. Each child can also have its own children.

#### Example Breakdown

Let's create a simple game where we place an object on the screen.

**1. Player Scene**:
- **Root Node**: `Player` (Node2D)
  - **Child Node**: `Sprite` (sprite2D - holds image)
  - **Child Node**: `CollisionShape2D` (detects collisions with other objects)

**2. Level Scene**:
- **Root Node**: `Level` (Node2D)
  - **Child Node**: `Background` (ColorRect - Color Background)
  - **Child Node**: `Player` (the Player scene)

#### Visual Example

```
Level (Node2D)
│
├── Background (ColorRect)
│
└── Player (Node2D)
    ├── Sprite
    ├── CollisionShape2D
    └── Script
```

### Why It’s Important

1. **Organization**: The scene tree helps keep your game organized. You know exactly where each part of your game is and how it’s connected.
2. **Reusability**: You can create scenes that can be reused in different parts of your game. For example, the player scene can be used in multiple levels.
3. **Easy Management**: Modifying or updating parts of your game is easier because everything is neatly organized in the scene tree.

### Summary

- **Nodes**: The basic elements of your game (like LEGO bricks).
- **Scene**: A collection of nodes working together.
- **Scene Tree**: The hierarchy showing how nodes are connected.


---
title: "Aetherea Architecture - From composition, inheritance and scriptable objects"
date: 2023-03-24
author: Fabian Albrecht
---
### Hello Adventurers,

in this blogpost we want to give you a glimpse into the architecture of Aetherea. We will talk about the different design patterns we used and why we chose them. We will also talk about the different components of our game and how they are connected to each other.

### Composition over inheritance
Composition over inheritance is a principle that suggests that instead of using inheritance to build complex objects, developers should use composition. Composition refers to the process of combining simpler objects to form a more complex object. In Unity, this principle is often used to create game objects that have different functionalities.

Nonetheless for some components we decided to use inhertance, e.g. for the spells. The reason is that altohugh all spells have the same base functionality (e.g. casting or cooldown time) the way how they are casted is different. For example the fire spell shoots a projectile in view direction while the lightning spell shoots down on the selected enemy and area of effect spells such as the freeze spell affect all enemies in a certain radius.
The same applies for the movement of enemies: Though we have some humanoid enemies (creatures with 2 legs and 2 arms) we also have some enemies that are not humanoid (e.g. spiders). As you may have guessed, the movement of these enemies is not similar at all. Down below you can see the inheritance architecture of our game:

![Inheritance architecture](/architecture/AethereaGame.png)

However we minimized the use of inheritance so that the e.g. the cooldown or damage system of the spells is performed by simple components. Down below you can see the composition architecture of the different spell classes:

|  Passive Spell  | Area spell  | Single target |
| ------------- | ------------- | ------------- |
| ![](/architecture/BasePassiveSpell.svg)  | ![](/architecture/BaseAreaSpell.svg)  | ![](/architecture/BaseSingleSpell.svg) | 

### Scriptable Objects

Scriptable Objects are a Unity-specific concept that allows developers to create reusable data structures that can be used in multiple instances. Scriptable Objects are a way of creating data-driven game objects that can be used to store, manage and share data between different parts of the game.

We use scriptable objects the properties of all the player, enemies and spells in the game. This include properties like the health, damage, speed, etc. of the different entities. 
These scriptable objects allow us to easily modify the properties of the objects without having to modify code directly. Making it easier to balance the game and make changes as needed. Since scriptable objects are are serializable and can be saved to disk, it is possible to share them between different scenes in the game. Here are some examples how we use scriptable objects in our game: 
|  Player  | Enemy  |
| ------------- | ------------- |
| ![](/architecture/Player.svg)  | ![](/architecture/Enemy.svg)  |

### Setup of new entities

The aforementioned concepts allow us to easily create new entities in the game. For example, if we want to create a new enemy, we can simply create a new scriptable object for the enemy and assign it to the enemy prefab. The procedure is the same for a new player or spell entity. Code must only be written/adapted to enable animations of characters or if spells need to be casted in a special way. Even then, due to the composition over inheritance principle, we can reuse a lot of code and only need to add/change about 20 - 30 lines of code to include a new entity.

As you can see this saves us a lot of time and allows us to create new entities in a short amount of time. This is especially important for our game as we want to create a lot of different enemies and spells, so that the game feels unique and immersive.

If you have any questions or suggestions, feel free to leave a comment below. We are always happy to hear your feedback!
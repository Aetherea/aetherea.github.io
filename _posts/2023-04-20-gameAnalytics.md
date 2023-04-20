---
title: "Aetherea Architecture - Game Analytics - Insights into players 🧠"
date: 2023-03-24
author: Fabian Albrecht
---
### Hello Adventurers,

Game analytics are crucial for the success of a video game, as they provide invaluable insights into player behavior, engagement, and preferences. By analyzing in-game data, we as developers can optimize gameplay mechanics, and tailor the gaming experience to better retain and satisfy players. Ultimately, game analytics allow us to make data-driven decisions, ensuring that Aetherea provides the best gaming experience possible.

Thus for the first steps we decided to implement the following metrics into our game:

#### **Playtime (Session length)**

This metric us used to determine how long a player spends playing the game. We want to use this metric to achieve a number of things:
1. Find out how long the game is played on average and if the game is too short or too long
2. Find out how long it takes players complete a playthrough, including multiple dungeon rooms and a final boss fight. This will help us to determine whether the overall difficulty of the game is too high or too low and if the number of rooms used in a run is appropriate.
3. Find out how long it takes players to complete a single dungeon room. This will help us to determine whether the difficulty of individual rooms is too high or too low.

In general one can say, the longer the playtimes the higher the difficulty of the game or dungeon room!
Because this metric can also be used to determine the difficulty of the game, we also want to use the metric to improve the algorithm that selects the dungeon rooms for a playthrough. At the moment the algorithm is very simple and only selects a random number of rooms from a list of all available rooms. We want to improve this algorithm by using the playtime metric to have a constant difficulty for each playthrough, but at the same time have a variety and divers selection of rooms.

#### **Usage of each spell**

This metric is used to determine which spells are used the most and which are used the least. We want to use this metric to achieve a number of things:
1. Find out which spells are used the most and which are used the least. This will help us to determine whether the spells are balanced or if some spells are too strong or too weak.
2. Find out which type of spells (AoE, single target, etc.) are used the most and which are used the least. This will help us to determine, what are the most popular spells among the players and what are the least popular spells.

Both of these metrics can not only be used to identify unbalanced spells but are also an important factor for data driven development. For example if the data shows that single target spells are used the most, we can focus on developing new single target spells or even a new spell variation that is based on single target spells (e.g. spells that shoot two projectiles in different directions). It is possible to extend the aforementioned metrics, by a metric that keeps tracks how often spells are used in specific room, opening up further possibilities for data driven development.

#### **Unity Analytics**

Unity Analytics is a powerful tool that allows developers to easily gather and analyze game data, offering insights into player behavior, engagement, and preferences. Thats why we decided to use Unity Analytics to implement the aforementioned metrics into Aetherea.

Unity Analytics offers an out-of-the-box solution to track session length. By implementing the Unity Analytics SDK in our game, we can automatically collect playtime data and analyze the average duration of play sessions. This information can then be used to determine if the game is too short or too long, and we can make necessary adjustments to the game's overall difficulty and dungeon room selection algorithm. To measure how long it takes players to complete a run or a single dungeon room, we can create custom events in Unity Analytics. For example, a custom event can be triggered when a player enters a dungeon room and another event when they complete it. By comparing the timestamps of these events, we can calculate the time spent in each room and analyze the difficulty of individual rooms and the overall game.

To track the usage of each spell, we implemented custom events in Unity Analytics. Whenever a player casts a spell, a counter is incremented. At the end of a run a custom event is triggered, sending information about the spell's type, power, alongside the counter. By categorizing spells based on their characteristics (e.g., AoE, single target), we can analyze the popularity of different spell types among players. Moreover, by extending our custom events to include details about the room in which a spell is used, we could further refine our data-driven development strategy.

By leveraging Unity Analytics capabilities, we can hopefully optimize gameplay mechanics and enhance the overall gaming experience, ensuring player satisfaction and retention. However this would imply that enough players play our game, so that we have solid database to analyze.
If you have any questions or suggestions, feel free to leave a comment below. We are always happy to hear your feedback!


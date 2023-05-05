---
title: "Aetherea V. 1.0 - Happy Release Day! 🎉"
date: 2023-05-02
author: Fabian Albrecht
---
### Hello Adventurers,

maybe the last time for a while now. It was a long but quite interesting story from back in March when started to develop the idea of Aetherea until now when we are finally able to release the first version of Aetherea game. We are very happy with the current state of the game but lets look back at the last few weeks and what we have achieved.

### Idea of Aetherea

Our first post started with the following words: 

*In the magical world of Aetherea, there lived a young magician named Alara. He was a talented and ambitious mage who had been studying the art of magic for as long as he could remember. Alara had always dreamed of finding a powerful artifact that was said to grant the user immense magical abilities. He knew that many other mages and adventurers were also searching for this artifact, but he was determined to find it first.*

To bring this idea to life we decided for an 3d isometric view in our second blogpost. We also decided to create a vast variety of different enemies and bosses in form of various magical creatures and dragons, all with a unique set of abilities! The combat system should be a mix of melee and range combat. However for the version 1.0 we decided to only implement both systems for the enemies and to concentrate on spells for the player. As a result we have a wide range of magical spells in Aetherea for the player to use and in addition to multiple bosses (both melee and range) more than 5 different enemies with their own unique abilities! The available spells however can also be enhanced after each level through a custom skill tree.

We wanted that Aetherea poses a new challenge every time you play it, thus we implemented automatic level generation. This means that no two playthroughs will be the same as the rooms are randomly selected from a pool of different rooms. Rooms have different sizes and can contain different enemies. 

If you want to know more about the idea of Aetherea, you can find extensive information [here](https://aetherea.github.io/firstPost/) and [here](https://aetherea.github.io/secondPost/). Also have a look at the demo video to get yourself interested in our game!

<video src="https://user-images.githubusercontent.com/85937078/236397182-0f008c0b-2941-4819-b885-42b476408b55.mp4" controls="controls" style="max-width: 730px;">
</video>

### Download

If you want to **download** and **install** Aetherea, you can do so [here](https://drive.google.com/file/d/1wZ5M6fsjZ2__dwPAtznKx8UFyoezCLhz/view?usp=sharing)!

### Architecture

After we were happy with the idea of Aetherea we started the implementation. But before we could even start to think about coding we needed to decide DevOps structure and the architecture of the game. We decided to use Unity as game engine and GitHub as version control system. However choosing github in combination with unity was not as easy as we thought. We had to find a way to work together on the same project without overwriting each others work. We decided to use the [git lfs](https://git-lfs.github.com/) extension to store the large binary files of unity.

After DevOps structure was set we started to think about the architecture of the game. We extensively used scriptable objects to create a data driven architecture and to save a lot of time in the development process. For the development of game objects we followed (for most of time) the composition over inheritance principle. This allowed us to create a lot of different game objects with different abilities and properties without the need to create a new class for each object. We dedicated a full blogpost to the architecture of Aetherea which you can find [here](https://aetherea.github.io/architecture/).

### Addictive Patterns

We also introduced some patterns to keep **you** playing longer and more often! To achieve this, we thought of some aspects of how to get someone new to play our game, as also how to get players to come back.

Therefore, we implemented the **skill tree**, where you can level up your spells, as some sort of reward system. We've also added a **hardcore mode**, in which all enemies have increased health, to make it even more interesting to start playing and to beat the game. **Milestones** are the last part we added to Aetherea, so you can tell all your friends, if you could get any milestones or just died in the first level.

### Game Analytics

We wanted to be able to steadily improve Aetherea. To ensure this we decided to implement a game analytics system. We decided to use the [Unity Game Services](https://unity.com/solutions/gaming-services) as it is free and has the best integration into the unity development workflow. We implemented the system in a way that we can track the usage of spells, the overall playtime of the user and time it takes players to beat specific rooms. You can find more information about our game analytics system [here](https://aetherea.github.io/gameAnalytics/).

Even before version 1.0 the described system helped us improve our game:
* From the data we were able to see, that the fireball spell was used way less than the other spells. That´s probably because it is way harder to actually hit a target with the fireball than with any other spell. We've decided to improve the fireball spell by increasing the damage and the speed of the fireball and the data already showed some results: the fireball spell is now used more often than before.
* We also saw that the time it takes players to beat the skeleton room was way higher than the time it takes to beat the other rooms. We decided to improve the skeleton room by reducing the number of skeletons in the room and their health a little bit. After the change the data showed that the time it takes players to beat the skeleton room is now in line with the other rooms.

### Coming up next : Music and Sound Effects

The version 1.0 of Aetherea does not include any music or sound effects. The reason is that we have a collaboration with the *Hochschule für Musik Karlsruhe* (Music college of Karlsruhe). We are currently working together with music students to create a unique soundtrack and sound effects for Aetherea. These will include the following sounds:
* Distinct music for each enemy type in Aetherea
* Distinct music for each boss in Aetherea
* Sound effects for each spell in Aetherea
* Sound effect when you finish the room
* (Optional) Sound effects for the footsteps of the player

We are excited to see how the music and sound effects will improve the overall experience of Aetherea. We will release a new version of Aetherea as soon as the music and sound effects are finished.

### Final Words

We are very happy with the current state of Aetherea and we are exited to see how the game will evolve in the future. We hope you enjoy playing Aetherea as much as we enjoyed developing it. In addition over the last 3 months we learned a lot about unity, game development and things like game analytics or game architecture that were completely new to us. Becoming familiar with all these new topics was a lot of fun but it also took some time. Here is the time we spent on Aetherea up until now:

- Tim: ~ 57,5 hours 
- Fabian: ~ 56,5 hours

For the 9 complete weeks that we had this semester this is a total of 114 hours resulting in a little bit more than 6 hours per Person per Week. This means we reached our goal of 6 - 7 hours per Person per week.

If you have any feedback or ideas for improvement, please let us know. We are always happy to hear from you 😉!


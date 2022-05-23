---
layout: post
title: "Game Dev Adventures Part 1"
categories: misc
author: Eyad Hasan
---

# Part 1

## Preface
I'm unsure how many parts this will have, if it has more than one, seeing as it's entirely likely I get too far down the rabbit hole and burnout.  
However, in my bored and often overly caffienated state, I needed something to-do, so I figured to pick up game development.  This is sort of like a catalog of my ramblings as I learn and make progress.  This part is kind of weird since I wrote this after finishing the tutorial and starting to put together my own game.

## Getting Started
Okay so lets get started.  The first part was figuring out how to start really.  I did some searching online, and a popular engine called [Godot](https://godotengine.org/) seemed to be a good starting point.  If you haven't used a game engine before, it's really nice.  It takes care of all the annoying parts you would've had to-do yourself if you used something like SDL, or Pygame, like creating a screen, handling inputs, animations, sounds, etc.  The list goes on and you get the point.  I had a vague idea of the game I wanted to make, something similar to hotline miami and postal.  A violent, beat-em up sort of game, with the premise is you're a super buff milk man stealing peoples milk.  

To get started I followed godots tutorial.  They have fantastic documentation, and I walked through the [Your first 2D game tutorial](https://docs.godotengine.org/en/stable/getting_started/first_2d_game/index.html), which helped me get started with the Godot IDE, and just some basic items I'd need to put together something of my own.

## Big Milk Man

Okay so thanks to the tutorial I was able to kick start big milk man pretty quickly.  I reused a lot of stuff from the tutorial to get some basic things going, like setting up inputs, the character you play as, and the screen, here's a gif of all that working

![](https://i.imgur.com/AJPuJai.gif)

After getting this part working I went on to create the object you steal, the milk.  I basically reused the hostile NPC setup that the tutorial had to create this but swapped some classes around.  I needed the milk to detect when the player entered so it would add a point.  I did run into an issue where the colissions weren't being detected, and found out I had accidently ticked the "disabled" box in the scene, so that was fun.  But after the first day of working I was able to get this:

![](https://i.imgur.com/eNwXgHZ.gif)

This was a pretty big first step, since it meant I had the foundations for a collectable object, that would detect when the player would run into it.  The next part was creating NPCs.  I'm still not super sure how I want NPCs and levels to work, but the nice thing about Godot and probably other engines, is I can create each item on it's own, throw it into a main scene to test, and then keep making adjustments.  Basically, all I needed to-do for now was focus on creating NPCs, and making sure if the player hits one, the player "dies".  Again I was able to reuse the NPC setup from the tutorial to create these NPCs.  I did run into a collision issue, where the player and NPC weren't detecting each other.  This was because I was using an Area2D for my player, and that meant my player wouldn't see the NPC, a RigidBody2D, when they "collided".  I struggled with this for a bit because the milk was an Area2D and could detect when a body entered it, but I found later RigidBody2D's don't normally detect collisions.  I swapped my player to a KinematicBody2D, and added an Area2D with a collision box to handle the collisions.  Because of this switch, I did get a pretty interesting change when the player collides with the NPC:

![](https://i.imgur.com/7kbx6Fd.gif)

## End

So far I've got a NPC, the milk, and the player all completed.  I can adjust the aspects of where the player starts, where the milk is, and how NPCs spawn pretty easily.  If you notice in the earlier gif, the NPC just randomly spawns on the edge of the screen.  There are some interesting tools that Godot has to set this up.  Basically you create a path, and a spawn path.  When the game starts you seed the random number generator, and then have the NPCs spawn along that line randomly, with a determined direction that'll take them to a different edge of the screen.  This is primarily for testing, I wanted to check collisions worked and that the player disappeared when they hit a NPC before continuing on.  In the next stage I want to have the NPCs "detect" the player, and walk towards them using some pathfinding.  This way, when I design a level, the NPCs can be prespawned, and approach the player when the player is within a certain distance.  I also want to add some mechanic for the player to hit NPCs, so there is some mechanic for fighting back.  For now, baby steps.
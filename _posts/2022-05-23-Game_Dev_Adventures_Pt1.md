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

Okay so thanks to the tutorial I was able to kick start big milk man pretty quickly.  I reused a lot of stuff from the tutorial to get some basic things going, like setting up inputs, the character you play as, and the screen.  After getting this part working I went on to create the object you steal, the milk.  I basically reused the hostile NPC setup that the tutorial had to create this.  I needed the milk to detect when the player entered so it would add a point.  I did run into an issue where the colissions weren't being detected, and found out I had accidently ticked the "disabled" box in the scene, so that was fun.  But after the first day of working I was able to get this:
[](https://imgur.com/eNwXgHZ)
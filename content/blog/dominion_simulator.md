---
title: Dominion Simulator Project
description: Work in progress Strategy simulator for the deck building game Dominion
date: 2023-08-29
tags: 
---
# Dominion
I learned dominion at a fairly young age, and was highly competive in my teens. In 2018, I took fourth place in the world championship, and at one point for a couple of hours I was the highest rated player on the leaderboard. This passion for dominion has combined with my desire to write software and I began creating a dominion simulator. 
The idea behind this dominion simulator, is that the user can create two strategies, and the program will quickly simulate 10s of thousands of games between them to let the user know how much better a given strategy is compared to another. This project is not the first dominion simulator, and is inspired by [Geronimoo's dominion simulator](https://github.com/Geronimoo/DominionSim).
Dominion is a deck builder created by Donald X. Vaccarino in 2009. Each game 10 cards are choosen from a massive pool of 366 cards. Because every game has different cards, strategies that exist on one kingdom simply don't exist in others because the cards are different. Because of this, it is helpful to know the relative strength of many different strategies. As a human who has played thousands of games, I have developed a decent intuition on what is good, but it is really helpful to have numbers to either back me up or change my mind so that people can become even better at dominion.
### Why Rust??
For this project, I choose to use rust because
- The type system is very expressive, allowing me to model dominion in a more complete way, and in a way that ensures that I implement functionality for every card of a type
- Memory safety is guaranteed
- Rust is fast
### This project has to do implement
- Game engine
  - Drawing, discarding, playing, buying, playing and trashing cards
  - Manage player state
  - Check game end conditions
- Strategy
  - Buy strategy
  - Play strategy
  - Save and load strategies
  - User create strategies
- All 366 cards need to be implemented
### Extensions to this project
- User interface for ease of use
- Support to pit multiple strategies against each other to create a table of dominion strategies with their relative strengths
- Performance optimization
- Support to simulate strategies from a certain game state
- Support to auto create strategies
  - Auto pit them against each other
  - Find best strategies for a kingdom
### Progress
I started this project in the June 2023, and have the basic game engine implemented, and am working on implementing user creating, loading and saving strategies.
### Lessons learned
Rust has a very fussy compiler. This is both a good and a bad thing. On the bright side, because it is so fussy, when you get the code to pass the compiler, it usually works how you intend it to, another great feature of the compiler is that the error messages often tell you exactly what you need to do to fix the problem.
One downside of rust is that borrow checker can make it hard to use reuse references that could be easily done in a garbage collected language, or a manual allocated language. This project has helped me learn to deal with the borrowed refrences and lifetimes. Rust's type system and match statements are really enjoyable to use and ensure that all cases of enums are handled which is a commonly used throughout the project.

You can see the source code right [here](https://github.com/SimeonSteward/dominion_simulator)

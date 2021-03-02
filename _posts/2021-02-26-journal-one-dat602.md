---
layout: post
title:  "Journal #One [DAT602] - Design Brief" 
author: Dale Stephenson
categories: [ DAT602, Journal, Database Application Development ]
image: assets/images/DAT602-J1.jpeg
featured: true
hidden: true
---
<i>Design Brief</i>

JOURNAL #ONE [DAT602]

<h2>Design Brief</h2>

<h3>WHAT</h3>

<h4>Milestone 1 - Analysis & Design</h4>

The first step in the database application development process is to create a system brief that allows for an understanding of the business and functional requirements. This is followed by storyboards, use cases, use stories and CRUD analysis, these will be detailed as the project progresses.

<h3>WHY</h3>

The aims of understanding requirements is to gain clarity of, and document the needs of the organisation and the processes the new system must perform. This clarity is obtained through a process of discovery but can include modelling to aid the understanding of the requirements.

To obtain a clear understanding of the requirements we begin by first understanding the problem domain for which the new system must provide a solution. There are a number of activities that can be performed that help define what the system must solve, which is why a high level system brief is developed.

<h3>HOW</h3>

The database being developed is for a multi-user, 2D <i>'point-and-click'</i> prototype game application based on a tiled map layout.

<h4>Business Requirements</h4>

- Auto registration of players on first login
- Registration requires password input
- New players are displayed as online and available for game play
- If the user name already exists a player has five tries to submit the correct password
- Administrator accounts are used for unlocking locked accounts, end game play, update existing player data and remove players
- Two or more players can play against each other
- Multiple games can operate concurrently 
- Players select other players as opponents to start a new game
- Players start on a defined 'home tile'
- Only one player can be on a tile at any time, except for the 'home tile'
- Players move around the board to a tile adjoining the current tile 
- Players who click on an empty tile first move to that tile
- Tiles contain items which are collected by players
- Items either gain players points or lose them points
- If a player leaves the game their last position is logged
- When a player returns to a game their location and state is restored 
- If a player returns and another player is in their last location, they must choose one of the adjoining tiles
- Players collect items as assets that can be used in the game play
- Players can communicate with each other through a text chat feature
- Players can delete their account
- Players can also be administrators

<h4>Functional Requirements</h4>

- User registration auto displays a notification that registration includes starting as a new player
- New players are added to a list in the remote database 
- System must check if user already exists 
- Prompt for password on user login if user name already held
- If all login attempts are incorrect the system locks the account
- Players turns are stored on the database as live game play occurs
- System displays all players currently online and their 'high scores'
- The system must track players, their current location and the assets they have collected
- The system must track the location of assets as they move around the board
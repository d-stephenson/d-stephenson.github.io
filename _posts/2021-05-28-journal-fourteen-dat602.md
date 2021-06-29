---
layout: post
title:  "Journal #Fourteen [DAT602] - GUI Components with Data Access" 
author: Dale Stephenson
categories: [ DAT602, Journal, Database Application Development ]
image: assets/images/DAT602-J14.jpeg
featured: true
hidden: true
---
<i>GUI Components with Data Access</i>

JOURNAL #FOURTEEN [DAT602]

<h2>GUI Components with Data Access</h2>

Development work for milestone 3 of the game development has required updates of both the SQL and data access class, ensuring it can function with the GUI forms created for the storyboard in milestone 1. The videos show the work achieved, the functionality includes:

- Register as a new player without admin privileges 
- Login credential check to access the game area
- Create a new game that other players can then join
- Join an existing game where the player count is less than 7
- Move character, find and select a gem which updates game points
- Access the admin area where a user is authorised 
- Select a game and kill it, removing it from the database
- Add a new player and set all the various privileges 
- Update a player, allows for all the player fields to be updated
- Delete a player from the database 
- Logout of the game 

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/B_XcjKr-Cbo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></center>

The game play (player move, find and select gem) functionality that runs the related SQL procedures has also been developed as an extension of the data access class created for milestone 2. The following video shows the player move to an adjacent tile, find gems, if any, that are located on the tile and select a gem to complete the game play.

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/N2XfF_ODv-4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></center><br>
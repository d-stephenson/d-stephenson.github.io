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

Development work for milestone 3 of the game development has required updates of both the SQL and data access class, ensuring it can function with the GUI forms created for the storyboard in milestone 1. The video shows the work achieved to date, the functionality includes:

- Register as a new player without admin privileges 
- Login credential check to access the game area
- Create a new game that other players can then join
- Join an existing game where the player count is less than 7
- Access the admin area where a user is authorised 
- Select a game and kill it, removing it from the database
- Add a new player and set all the various privileges 
- Update a player, allows for all the player fields to be updated
- Delete a player from the database 
- Logout of the game 

The gameplay (player move) functionality that runs the related SQL procedures is not yet developed outside the data access class created for milestone 2. The next step is to allow a player to move to an adjacent tile to complete the gameplay.

<center><iframe width="400" height="300"
    src="https://www.youtube.com/watch?v=Xz4g9qfIaBc">
</iframe></center>
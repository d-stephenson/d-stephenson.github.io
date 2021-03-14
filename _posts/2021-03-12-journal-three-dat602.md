---
layout: post
title:  "Journal #Three [DAT602] - Logical Diagram Development" 
author: Dale Stephenson
categories: [ DAT602, Journal, Database Application Development ]
image: assets/images/DAT602-J3.jpeg
featured: true
hidden: true
---
<i>Logical Diagram Development</i>

JOURNAL #THREE [DAT602]

<h2>Logical Diagram Development</h2>

<h3>WHAT</h3>

<b>Game Logical ERD</b>

The relational (logical) modelling diagram is developed to both improve the system and improve how it is visualised and communicated. The relational model details the events that take place and lists the data required. Further benefits from producing the relational diagram is that it builds the foundations for the creation of the physical diagram.

The logical ERD for the Seven Dwarfs Gem Hunt has gone through many iterations to get it to its current state as follows:

<img src="/assets/images/DAT602_LogicalDiagram_v2.2.png" alt="Game Logical ERD"><br>

The most difficult part to understand and get right was the relationship between the game table, player table, character table and item table. Several variations were developed, however they didn’t satisfy normalisation. Ultimately, it came down to the play table to resolve some of the issues in addition to developing the item/game table to include the tile location and play ID, both as nullable fields. 

<h3>WHY</h3>

Logical diagrams are used to allow for a better understanding of the database by the non-technical business team. This is extremely beneficial to the development team as it allows them to involve the business users in the process. This is useful because the business team can be more capable at rooting out errors made in the assumptions, in addition to identifying any shortcomings within the database design from a business perspective.

<h3>HOW</h3>

The logical diagram has been developed using Visual Paradigm to create the entities required for the game and to understand the relationships between those entities. 

The entities of the database that satisfied the business requirements were developed first, the relationships between the tables that served the functional requirements, and ensuring the correct use of crows foot notation was more problematic to solve. It would, perhaps, have been a good idea to draw up a quick sketch of a conceptual model first, which would have aided the creation of a logical diagram. 

The relationships that have been established to ensure proper game functionality include:

Play, Player, Game - A player can play one or many games, and a game can be played by one or many players.

Player, Play, Character - One player plays one or many characters, characters are played by one or many players.

Play, Player, Tile - At any point in the game the player is located on a tile, one player can be located on one tile at any time, a tile can contain zero or one player.

Tile, Item/Game, Play - Each item on the board must be located on a tile in order for it to be found by the players, once an item has been found by a player the relationship between the item and the tile is removed from the database, instead a relationship with the player is established. 

Board, Board/Tile, Tile - One board has many tiles and tiles can be located on many boards, this many to many relationship requires a Board/Tile join table that establishes the relationship between board and tile.

Item, Item/Game, Game - Each item can exist as part of one or many games, each game can contain one or many items. In order to satisfy normalisation a join table is created between the game table and the item table. 
---
layout: post
title:  "Journal #One [DAT601]"
author: d-stephenson
categories: [ DAT601, Journal, Database Design & Administration ]
image: assets/images/conceptualDiagram.png
featured: true
hidden: true
---

JOURNAL #ONE [DAT601]

Learning Summary<br>

<b><u>WHAT</u></b>

Class sessions have involved group work surrounding the development of a Conception Model Entity Relationship Diagram (ERD) for an online tile game that our group have called 'Game of Tiles'.

In class sessions we have looking at the structure of the ERD specifically the notations and symbols involved in conceptual visualization of a relational database.

A Conceptual ERD is used to present a high level view of the business system or organisation. It is used to define the business objects involved, listed as Entities and shoe the relationships between the Entities. 

<i>N.B. Research carried out into Conceptual Diagrams show there is disagreement as to whether Attributes and Cardinality should be included at this level. Sources show attributes and Cardinality being introduced at the Logical level.</i>

<i>Guide to the ERD:</i>

Entity = Rectangle or Square<br>
Attributes = Oval<br>
Relationship = Diamond<br> 

<b>Entity:</b>

An entity is a definable or major element, commonly a noun, that is represented in the database. This could be an object or a person, a concept or event. The entity is the first consideration when looking at database design.

<b>Attribute:</b>

An attribute is something that characterizes the entity. For example in the case of 'Game of Tiles' we have a entity of 'Skill', the attributes related to the entity are skills that can be used by the Characters in the game.

Attributes can be split further:

Simple Attribute: cannot be split further e.g. Age.
Composite Attribute: Can be further split into sub-attributes e.g. Name can be split into First, Middle and Last. 

<b>Relationship:</b>

Relationships signify a link between two entities. For example in the case of 'Game of Tiles' Character has a relationship with Player. The Player plays the Character and the Character is played by the Player. 

<b>Cardinality:</b>

Cardinality looks at the number of occurrence's or the potential occurrence's between entities that have a relationship. For example in the case of 'Game of Tiles' a Character can play 1 Game, but a Game can have many (m) Characters.

There are three cardinal relationships discussed in class that are used in the ERD: 

<i>1 to 1:</i> Can split an entity such as Player and Character to make the data easier to understand.

<i>1 to Many (m):</i> A sole instance of one entity relates to many of another entity. Can be viewed in reverse as Many (m) to 1.

<i>Many (m) to Many (n):</i> Many instances of one entity relates to many of another entity.

<b><u>WHY</u></b>

Creating ERDs is extremely useful when trying to understand how a business system or organisation functions. 

ERDs allow all users or potential users of the system to visualize who the entities are interacting with the data system, what the relationships are between the entities and what attributes are associated with the entities. The development team can use the diagram to determine what the technical requirements are of the software and what data is required.

Fundamentally ERDs help stakeholders of the system, in conjunctions with other diagramming techniques, to create a visual image of how the data in the system is connected in a very general way so that multiple user groups can review and provide input based on their perspective.

Having come from a business development background and been through critical change processes in local government I have participated in the support process of large technical change and how the data from multiple systems would need to be integrated into a single system to be used across multiple government departments. The more complex a system, which often comes with age and and historically poor planning the more useful these higher level diagrams are in gaining the understanding of all those involved in the process.

<b><u>HOW</u></b>

Developing my understanding of the ERD at conceptual level has been helped by prior learning from last semester in DAT502. 

I find class work provides a solid base in which to carry out personal research. It was doing this that I discovered that there variations to what is included at the Conceptual level and what then is added at the Logical level. I also found this in DAT502. 

I can see in a practical way how leaving Attributes out at the Conceptual level may be of benefit when dealing with people who are not technically minded but need to understand and provide input to a system. 

Once everyone is working on the same page, Attributes can then be added at the Logical level in an incremental way. 

The caveat to this is that a technical team might prefer Attributes listed at the Conceptual level as they are more familiar with the technique.

As a result of having a working background in business I generally try to apply my learning to business environment which is useful when trying to retain the information and specific details. 

Saying that this course relates to systems development with regards to gaming of which I know next to nothing. However the challenge will be fun, and a game is still a business entity especially if there are options to introduce paid for elements of the play which is the case with applications from the Apple App store for instance. 

I have been fortunate in joining a team where the other contributors are gamers and they have proven extremely useful in plugging the games in my knowledge surrounding how a game such of this might work and operate. There is also some crossover with other systems, such as player login which functions in the same way as an email login for example. 

<b><u>Game of Tile Documentation</u></b>

<object data="/assets/docs/GoT_ERD.pdf" type="application/pdf" width="100%" height="1000%">
  <p>Download Game of Tiles <a href="assets/docs/GoT_ERD.pdf">Documentation</a></p>
</object>












---
layout: post
title:  "Journal #One [DAT601]"
author: d-stephenson
categories: [ DAT601, Journal, Database Design & Administration ]
image: assets/images/conceptualDiagram.png
featured: true
hidden: true
---
<i>Conceptual ERD created by Team Excellence</i>

JOURNAL #ONE [DAT601]

Learning Summary<br>

<b><u>WHAT</u></b>

Class sessions have involved group work and have focussed on the development of a Conception Model Entity Relationship Diagram (ERD) for an online tile game that our group have called 'Game of Tiles'.

We have been looking at the structure of the ERD and specifically the notations and symbols involved in conceptual visualization of a relational database.

A conceptual ERD is used to present a high level view of a business system or organisation. It is used to define the business objects involved, which are listed as entities, and show the relationships between the entities. 

<i>N.B. Research carried out into Conceptual Diagrams show there is disagreement as to whether attributes and cardinality should be included at this level. Sources show attributes and cardinality being introduced at the logical level.</i>

<i>However both attributes and cardinality are displayed on the ERD.</i>

<i>Guide to the ERD:</i>

Entity = Rectangle<br>
Attribute = Oval<br>
Relationship = Diamond<br> 

<b>Entity:</b>

An entity is a definable or major element, commonly a noun, that is represented in the database. This could be an object or a person, a concept or event. The entity is the first consideration when looking at database design.

When considering an entity in the ERD we can view it in a hierarchical way. We can group entities together to represent a more general view, this is called Generalisation. Likewise we can do the exact opposite and break an entity up into more specialised entities, known as Specialisation. 

This was done originally in the ERD, player and character was generalised into just player. Later after class discussion player was specialised into player and character with their own unique attributes.

<b>Attribute:</b>

An attribute is something that characterises the entity. For example, in the case of 'Game of Tiles' we have a entity of 'skill', the attributes related to the entity are skills that can be used by the characters in the game.

Attributes can be more complex and broken into two distinct versions:

Simple Attribute: cannot be split further e.g. Age.
Composite Attribute: Can be further split into sub-attributes e.g. Name can be split into First, Middle and Last, or address into local street and wider regional parts, including postcode. 

<b>Relationship:</b>

Relationships signify a link between two entities. For example in the case of 'Game of Tiles' character has a relationship with player. The player plays the character and the character is played by the player. 

<b>Cardinality:</b>

Cardinality looks at the number of occurrence's or the potential occurrence's between entities that have a relationship. For example in the case of 'Game of Tiles' a character can play 1 Game, but a game can have many (m) characters.

There are three cardinal relationships as discussed in class that are used in the ERD: 

<i>1 to 1:</i> Here we would split an entity that might otherwise be classed as one into two, such as player and character. They are arguably the same thing however splitting them and forming a 1 to 1 relationship makes the data easier to understand.

<i>1 to Many (m):</i> A sole instance of one entity relates to many of another entity. Can be viewed in reverse as a Many (m) to 1 relationship.

<i>Many (m) to Many (n):</i> Many instances of one entity relates to many instances of another entity. In this case we use an 'm' and an 'n' to show the amount of 'many' as potential different.

<b><u>WHY</u></b>

Creating ERDs is extremely useful when trying to understand how a business system or organisation functions. 

ERDs allow all users or potential users of the system to visualize who the entities are that interact with the data system, what the relationships are between the entities and what attributes are associated with the entities. The development team can use the diagram to determine what the technical requirements are of the software system, and what data is required.

Fundamentally ERDs help stakeholders of the system, in conjunctions with other diagramming techniques, to create a visual image of how the data in the system is connected in a very general way. This is so beneficial because multiple user groups are able to review and provide input based on their perspective.

Having come from a business development background, and been through critical change processes in local government, I have participated in the support process of large technical change. This experience has allowed me to see how the data from multiple systems would need to be integrated into a single system to be used across multiple government departments. 

The more complex a system, which often comes with the age of the system and data stored, and historically poor planning and implementation means these higher level diagrams are even more useful in attempting to gain an understanding of the multiple elements involved in the development.

<b><u>HOW</u></b>

Developing my understanding of the ERD at conceptual level has been helped by prior learning from last semester in DAT502. 

I find class work provides a solid base in which to carry out personal research. It was doing this that I discovered that there variations to what is included at the conceptual level and what then is added at the logical level. I also found this in DAT502. 

I can see in a practical way how leaving attributes out at the conceptual level may be of benefit when dealing with people who are not technically minded, but nevertheless need to understand and provide input to a system. 

Once everyone is working on the same page, attributes can then be added at the logical level in an incremental way. 

The caveat to this is that a technical team might prefer attributes to be listed at the conceptual level, as they are more familiar with the technique and could speed up their understanding.

As a result of having a working background in business I generally try to apply my learning to business environments, which is useful when trying to retain the information and specific details. 

Saying that, this course relates to systems development with regards to gaming, of which I know next to nothing. However the challenge will be fun, and a game is still a business entity, especially if there are options to introduce paid add-ons within the game play, which is the case with applications from the Apple App store for instance. 

I have been fortunate in joining a team where the other contributors are gamers and they have proven extremely useful in plugging the gaps in my knowledge, specifically surrounding how a game such as this might work and operate. There is also some crossover with other systems, such as player login which functions in the same way as an email login for example. 

Below is the documentation produced to accompany the ERD displayed in the image of this Journal.

<b><u>Game of Tile Documentation</u></b>

<object data="/assets/docs/GoT_ERD.pdf" type="application/pdf" width="100%" height="1000px">
  <p>Download Game of Tiles <a href="assets/docs/GoT_ERD.pdf">Documentation</a></p>
</object>












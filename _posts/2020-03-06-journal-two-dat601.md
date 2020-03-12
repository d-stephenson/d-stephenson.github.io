---
layout: post
title:  "Journal #Two [DAT601]"
author: d-stephenson
categories: [ DAT601, Journal, Database Design & Administration ]
image: assets/images/conceptualDiagramV.2.PNG
featured: true
hidden: true
---
<i>Conceptual ERD development process - created by Team Excellence</i>

JOURNAL #TWO [DAT601]

Learning Summary<br>

Much of the group effort this week has revolved around furthering our understanding of the symbols and rules to utilise in the Conceptual ERD. This led to the creating of an ERD legend that can be used as a reference guide and updated when required as our learning develops. 

Our Conceptual ERD has gone through a number of cycles at this stage and the additional complexity has led us to review our previous interpretation of how the game would operate, and what data would need to be stored at what stage. This has led to some minor changes but also a significant change surrounding 'Player' and 'Administrator', which we determined were specialisations of a newly introduced entity known as 'Account'. 

This process is known as Generalisation and is discussed in further detail in this Journal.

<i>Additional understanding from this week:</i> Chens Rule for the ERD - attributes cannot participate in another relationship, if an attribute needs to participate in relationships with other entities then we must consider that the attribute is in fact its own entity.  

<b><u>WHAT</u></b>

<b>Weak (Child) Entity & Strong (Parent) Entity:</b>

There are two types of entities within an ERD. 

A strong entity is an entity within the ERD that can 'stand on its own'. What we mean by this is it can exist independently, without any other entity.

A strong entity is identified by a rectangle with either no, or one outline. A strong entity may have total or partial participation in a relationship and will always have a primary key.

In comparison a weak entity does not exist without the strong entity, it relies on the strong entity for its existence.

A weak entity is identified by a rectangle with a double outline. A weak entity must always have total participation in the relationship.

<b>Weak Relationship:</b>

A weak relationship is the relationship that exist between the weak entity and the strong entity, for which it relies upon for its existence.

As with a weak entity, a weak relationship is denoted by a diamond, with a double line outline.

<b>Mandatory (Total) & Optional (Partial) Participation:</b>

Entities within the ERD participate in the adjoining relationship between themselves and other entities. However that participation can either be mandatory (Total) or optional (Partial).

The type of participation an entity has within a relationship will correlate with the business rule that describes the relationship. 

Mandatory participation means that the entity has no option but to participate in the relationship. For example in the customer / order relationship, an order <u>must</u> be placed by a customer. Therefore a customer record must exist i.e. have mandatory/total participation, for an order to be placed. 

In this example an order cannot exist without a customer, making the order entity a weak entity of the customer entity, and the relationship a weak relationship. This means that the order entity is also involved in mandatory participation. 

Optional or partial participation means that an entity may or may not participate in a relationship. An example of this would be in teh employee manages a department relationship. An employee must manage a department within a business or organisation, however an employee may be a manager of a department, but not all the employees with manage, making this optional participation. 

<b>Generalisation & Specialisation:</b>

Generalisation is an approach used in creating an ERD that can help with understanding the entities and break down the complexity. It is viewed as a bottom up approach, by which we mean that two entities can combine to form to form a higher level entity above the two below it. 

Our team determined that this approach was necessary for our game ERD, and as a result we formed an 'account' entity' that sat above the two types of accounts that exists in the database, those being 'player' and 'administrator'.

Specialisation on the other hand is the exact opposite of generalisation, being a top down approach. In our example above we could have quite easily started with the entity 'account', and the team did discuss this early on in the ERD development. If this had been the case and we went down this route, we could have the created entity of 'account' and then formed two account sub-groups being 'player' and 'administrator'.

Our work in this area can be seen in the following snapshot of our Conceptual ERD:

<img src="/assets/images/GSisation.png" alt="Example Generalisation Specialisation"><br>

<b>Database Design Legend - Symbols:</b>

<object data="/assets/docs/ERD_Symbol_Legend.pdf" type="application/pdf" width="100%" height="625px">
  <p>Download Game of Tiles <a href="assets/docs/ERD_Symbol_Legend.pdf">Documentation</a></p>
</object><br>

<b><u>WHY</u></b>

Developing our understanding of the more complex structures of the ERD allows us to better understand how the database will be designed and how it will function. 

The added complexity, whilst being more difficult to create and get your head around initial, has the advantage of making the elements with the ERD clearer. By specifying exactly what is expected from each entity, whether it relates to other entities for its existence or what the relationship will look like helps us to build a mental picture of the game. 

There are further benefits to the increased detail within the diagram, particular for user groups that have a stake within the system. Business users for example are able to understand and start to picture how the system will work and identify problems that may arise from an operational point of view, as well as identify opportunities available from a business perspective.

Likewise those same opportunities are available to the technical and development teams. Furthermore the level of detail and clarity within the ERD will help to either reduce or eliminate errors during the build process.  

<b><u>HOW</u></b>

This week has built on my base level of understanding of the Conceptual model ERD. Having those foundations in place from DAT502 has helped support the understanding process.

Creating the ERD Legend was, I think the most helpful exercise. Not only did my research help to support my understanding of the rules available, I was also able to understand some of the more difficult concepts by looking at the various examples used, particularly surrounding participation and generalisation. 

As a non-gamer I struggled to 'see' the game at first. I couldn't visualise how it might look. However having carried out the exercises so far I now have a very good understanding and picture of the principles of the game, what the business rules are and what the basic structure of the database will look like.   

<b><u>Game of Tile Documentation</u></b>

<i>This document has been updated in line with the new ERD.</i>

Updated details include:

- Business Rules
- Data Dictionary 

<object data="/assets/docs/GoT_ERD.pdf" type="application/pdf" width="100%" height="800px">
  <p>Download Game of Tiles <a href="assets/docs/GoT_ERD.pdf">Documentation</a></p>
</object>












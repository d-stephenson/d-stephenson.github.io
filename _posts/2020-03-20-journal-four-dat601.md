---
layout: post
title:  "Journal #Four [DAT601]"
author: d-stephenson
categories: [ DAT601, Journal, Database Design & Administration ]
image: assets/images/j4header.PNG
featured: true
hidden: true
---
<i>Comparing the Conceptual Model with the Relational Model</i>

JOURNAL #FOUR [DAT601]

Learning Summary<br>

<b>GOING FROM CONCEPTUAL TO LOGICAL...[AND BACK AGAIN!]</b>

<u>The Relational Model</u>

Class sessions discussed the move from the Conceptional Model to the Relational (Logical) Model, and the rules and constraints that govern the process.

The Relational Model was developed in 1970 by Codd. The main difference between the Conceptual Model and Relational Model is that the Conceptional Model is entity specific, whereas the Relational Model is table specific, this can be viewed in the diagram above. 

The tables in the Relational Model have a specific number of columns, but an unlimited number of rows, or Tuples. A set of Tuples is a record. The columns are the attributes and each attribute must have a domain.

<b><u>WHAT</u></b>

<b>Making a Comparison</b>

<table>
  <tr>
    <th>Conceptual</th>
    <th>Relational</th>
  </tr>
  <tr>
    <td>Represents a group of objects called entities and identifies the relationships between them</td>
    <td>Represents a group of tables and defines the relationships between them</td>
  </tr>
  <tr>
    <td>Data is categorised as Entity set, Relationship and Attribute</td>
    <td>Data is categorised as Domain, Attributes and Tuples</td>
  </tr>
  <tr>
    <td>Easier to understand the relationships</td>
    <td>Can be more difficult to define relation between the tables</td>
  </tr>
  <tr>
    <td>Includes cardinality</td>
    <td>Does not include cardinality</td>
  </tr>
</table><br> 

<b>Rules when moving to the Relational Model</b>

<u>ENTITIES</u> 
- An entity type becomes a table and generally keeps the same name
- Entities contain an Attribute or Attributes that make up the Primary Key (PK), if there is more then one attribute that makes up the PK this is a Composite Key (CK)
- Weak entities contain the Foreign Key (FK) of their parent entity 

<img src="/assets/images/entityconceptualtorelational.PNG" alt="Entities and Attributes - Conceptual to Relational"><br>

<u>ATTRIBUTES
- Attributes become columns within the table
- The key attribute of the entity in the Conceptual Model may likely become the Primary Key (PK) in the Relational Model
- Multi-valued Attributes become tables, the parent entity will then become a Foreign Key (FK) in the table

<u>RELATIONSHIPS</u>  
- Relationships with attributes will become tables, this is because in the relational model there are no relationships
- In one-to-one relationships the PK of one of the entities will become the FK of the other, the decision as to which one is the problem of the designer
- In a one-to-many relationship the 'many entity' takes the PK from the 'one entity' as a FK
- In order to resolve the many-to-may relationship a join table must be created, this table includes both PKs for the entities it joins together which are represented as FKs, which become the Composite Key (CK) of the table

<img src="/assets/images/relationshipconceptualtorelational.PNG" alt="Relationships - Conceptual to Relational"><br>

<u>PARTICIPATION</u> 
- As a rule the PK on the mandatory participation side will become the foreign key on the optional participation side 

<u>SUPERCLASS/SUBCLASS</u> 
- There is not one, singular solution when dealing with Superclass and Subclass. There are three potential solutions to the problem:
<table>
  <tr>
    <th>Solution 1</th>
    <th>Solution 2</th>
    <th>Solution 3</th>
  </tr>
  <tr>
    <td>The superclass becomes a table in the relational diagram that has the attributes that are shared by all subclasses, then each subclass becomes a table containing their unique attributes</td>
    <td>Completely remove the superclass from the relational diagram, instead each subclass becomes a table with all common attributes plus their own unique attributes</td>
    <td>The superclass becomes a table that holds all common attributes and the unique attributes of each subclass</td>
  </tr>
</table><br>

<b>Crows Foot</b>

Crows Foot notation is a data modelling technique used within the Relational Modelling Diagram. It was created by Gordon Everest and named after the fork in the cardinality of the many-to-many relationship, like the toes of a crows foot. 

In crows foot, cardinality represents the maximum number of instances that a entity is associated with its related entity. This is indicated by 1 or Many. Modality is the opposite and represents the minimum number of occurrences. This is indicated by a 0 or 1. 

Crows Foot is represented in the following legend: 

<img src="/assets/images/crowfootlegend.PNG" alt="Crows Foot Legend"><br>

<b><u>WHY</u></b>

The logical modelling diagram is developed to both improve the system and how it is visualised. The relational model details the events that take place and lists the data required. There is a further benefit in producing the relational diagram in that it builds the foundations for the creation of the Physical diagram. 

Logical diagrams can often be used to allow for a better understanding of the database by the non-technical business team. This is extremely beneficial to the development team as it allows them to include the business team in the process, this can be extremely useful as it allows the business team to route out errors made in the assumptions, and identify any shortcomings within the database design.

<b><u>HOW</u></b>

The process of going from Conceptual to Relational can in some ways be quite straightforward. A lot of system visualisation has been achieved and therefore it capable of providing a far greater understanding of what the business outcome which is an asset shared amongst the teams involved.

The key is to follow the rules as outlined above and understand where decisions have to be made as to which route to follow. This is especially important with the more abstract elements such as multi-valued attributes, relationships which contain their own attributes and the move from a relationships structure into Primary Keys and Foreign Keys. On a whole however the rule structure is logical to follow. 

<b><u>Milestone 1 - Conceptual Updates</u></b>

At lot of effort has been put in this week to tighten the Conceptual Model. Changes have, as a result, been made to the documentation including Business Rules and the Data Dictionary and will be included in the report submission and not posted to these blogs. 













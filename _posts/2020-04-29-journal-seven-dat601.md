---
layout: post
title:  "Journal #Seven [DAT601]"
author: d-stephenson
categories: [ DAT601, Journal, Database Design & Administration ]
image: assets/images/NaLER.png
featured: true
hidden: true
---
<i>Natural Language</i>

JOURNAL #SEVEN [DAT601]

Learning Summary<br>

<b>ANALYSING NaLER</b>

<b><u>WHAT</u></b>

<u>A Brief Introduction</u>

The design and development of database system commonly utilises the entity relationship (ER) model. In order to produce a successfully database it is vital that the information being relayed to all users and stakeholders of the system is clearly understood and can be analysed. 

In order to aid the understanding amongst all user groups a method can be deployed known as Natural Language for ER (NaLER). NaLER offers users involved in system development a way of viewing and interpreting information and comparing models developed in the design process.

<b>The NaLER Method</b>

The NaLER development method was created for students at Massey University, New Zealand. Its purpose was to allow the students taking the course to judge whether the models they developed, made the statements that they originally conceived. NaLER was being used as an effective tool for evaluating entity relationship diagrams (ERD).

<b><u>WHY</u></b>

NaLER helps to resolve some of the drawbacks inherent to the diagrams created at the conceptual and relational stages, not all users will understand the symbols and annotations used in the diagramming technique. 

Users without an understanding or familiarity of the diagrams will likely revert to using natural language in order to correctly interpret what they are studying. For the diagramming to be intuitive the syntax used must be understood and this will not be the case for all users. 

What appears straightforward to a database designer will not always be so for a business user or client. It is a useful tool for allowing changes to be made, it can be the case that the first assumed diagram design will produce a database that will work for the end user. Without the assumptions being challenged the database designer has no clear direction, the business users providing the information from a ground level do not necessarily understand what they are looking at when reviewing the diagrams.

The NaLER method can also be hugely advantageous to a database designer by providing a natural language interpretation of the data structure. The designer can create an ERD based on an understanding of what the statement is intending to rely upon. A benefit of using the NaLER approach, which more closely resembles real world scenarios, means any uncertainty can be easily raised and clarified. The designer can also use this language as a comparison tool for the diagrams they create, they can more clearly understand the implications of the representations they are making within the diagram.

<b><u>HOW</u></b>

The method is generally split into 6 steps:

<u>Step 1 – Establish the conventions used in the diagram and document</u>

This step is used to provide clarity on what notation was used in the diagramming technique. The designer would be required to construct an appropriate legend if one were not provided. This would be needed to define how the diagram was being interpreted and to record any instances of inconsistency in the diagram.

<u>Step 2 – Check the syntax</u>

The benefits of checking work in progress is obvious in any development process and the systems development cycle is no different. This step allows a designer to check the syntax in the diagram, including any checks against assumption made in step 1 and to ensure the statements are correct and completed in full. 

Once this has step has been carried out the designer can record any changes that they may have made.  

<u>Step 3 – Dealing with entities</u>

This step is carried out with the diagram meeting at least first normal form (1NF).

A designer should begin by writing a sentence for the attribute that acts as the primary key (PK), the format of the sentence should be structured as follows:

Each Entity-name is uniquely identified by Primary Key

For example, “Each Vessel is uniquely identified by VesselTypeID.”

What this allows a designer to do is to understand and validate what the entity represents. So, in the example given above we can remove confusion by changing the entity from Vessel to VesselType.

Next begin to write sentences for all the entity attributes that is not either a PK or a foreign key (FK). This should be carried out using the structure as follows:

One Entity-name identified by PK must have one attribute name

For example, “Each Vessel Type identified by VesselTypeID must have one Vessel Type name.”

In the example it is clear a vessel type would have a name, however what if a given entity did not need a name attribute and the field was nullable. In the above example we would change must to may.

Finally, a designer will need to write a sentence for any relationships which are binary. Recurring binary relationships are also carried out utilising the structure as follows:

One Entity-name1 identified by PK optionality relationship-name cardinality Entity-name2 identified by Foreign Key

For example, “One Vessel Type identified by VesselTypeID must have one or more Seamen identified by (VesselTypeID, SeamenID).”

<u>Step 4 – Enter real world sentence examples for the second and third processes in Step 3</u>

The idea behind this step is to take real world examples from the diagram and place them into sentences that are factually correct. This allows users and stakeholders to relate the diagram statements to factual examples. 

For example:
Vessel 008738 has the name “U.S.S. John F. Kennedy”
Vessel 008738 has seaman 673301, 699934, 300891

The steps outlined above are often enough to allow a user to understand most of the information included in the relational model. 

<u>Step 5A – Where an entity is part of a ternary or greater, many-to-many relationship and has a composite name</u>

It is important that in this step and in step 5B that follows, that the designer focusses on the meaning of the relationship and how it interacts with the entities. The structure is as follows:

One Entity-name1 identified by PK1 optionality relationship-name1 cardinality Entity-name2 identified by PK2 relationship-name2 cardinality Entity-name3 identified by PK3

For example, “One Vessel Type identified by VesselTypeID must have one or more Seamen identified by SeamenID that uses one or more Tools identified by ToolID.”

It is important to note that the entities are those that participate in the relationship, PK will be FK in the resolving entity, any sentences already written for the entities can be discarded, the second and third process in step 3 along with step 4 should be carried out for those entities with attributes that are in addition to the PK.

<u>Step 5B – Where an entity is part of a ternary or greater, many-to-many relationship and has a clear identifier and singular attribute key</u>

One Entity-name1 identified by PK1 must relationship-name1 one Entity-name2 identified by FK1 relationship-name2 one Entity-name3 identified by FK2 and relationship-name3 one Entity-name4 identified by FK3

For example, One Invoice identified by InvoiceID must be made by one Salesperson identified by SalespersonID for one Customer identified by CustomerID and for one Order identified by OrderID

In this step all processes must be followed, and the first entity name must be the resolving entity. There may be a requirement to change the wording in order for the relationship to be correctly interpreted by all users.

<u>Step 6 – Create a NaLER description writing the sentences that correlate to the diagram model and provide examples where required for clarity</u>

This final step involves listing all the sentences including any changes where necessary to make the relationship clearer to understand.

An example sentence listing format for an ERD would look as follows:<br><br>
S1: Each Vessel is uniquely identified by one VesselID<br>
S2: One Vessel (VesselID) must has one mission<br>
S3: One Vessel (VesselID) must has one VesselName<br>
S4: One Vessel (VesselID) must have one or more Seamen (VesselID, SeamanID)<br>
S5: Each Seaman is uniquely identified by one VesselID, SeamanID<br>
S6: One Seaman (VesselID, SeamanID) must have one Bunk<br>
S7: One Seaman (VesselID, SeamanID) must be stationed on one Vessel (VesselID)<br>
S8: One Seaman (VesselID, SeamanID) must be belong to one Department (DepartmentID)<br>

<u>Conclusion<u>

In conclusion NaLER can be used as a tool to support the understanding of the diagrams provided. When utilised properly it can benefit all users and stakeholders by making them comfortable enough to draw their own conclusion and as a result question the understanding of the designer for the benefit of the database.







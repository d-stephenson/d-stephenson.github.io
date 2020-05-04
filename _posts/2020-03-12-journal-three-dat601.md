---
layout: post
title:  "Journal #Three [DAT601]"
author: d-stephenson
categories: [ DAT601, Journal, Database Design & Administration ]
image: assets/images/conceptualDiagramV.2.1.PNG
featured: true
hidden: true
---
<i>Conceptual ERD development process - created by Team Excellence</i>

JOURNAL #THREE [DAT601]

Learning Summary<br>

<b>ENHANCED ENTITY-RELATIONSHIP MODELLING</b>

This week looked at some of the final layers of complexity to be introduced into the ERD. Specifically this surrounded the further rules and constraints of Specialisation and Generalisation and how they relate to Superclass and Subclass.

In addition we reviewed disjoint and overlap, a method used in Generalisation that relates to Total and Partial participation and most importantly for me, deals with the issue surrounding the lack of '0'(zero) in Chens Notation.  

<b><u>WHAT</u></b>

<b>Superclass & Subclass:</b>

I discussed Generalisation and Specialisation in my last Journal so won't repeat it here, other then to define Superclass and Subclass in the context of the principle.

<b>Superclass</b> - Can be defined as an entity type that sits at a high level within the Conceptual ERD, it is a more general representation of the entity type.

<b>Subclass</b> - Can be defined as an entity type that sits at the lower levels within the Conceptual ERD, it is a more specific representation of the entity type and will make up multiple subclasses.

An example of this would be Military Naval Ships, the Entity <i>Military Naval Ships</i> would be the superclass, and the subclass would be the separate classes of ships defined by their purpose, such as <i>Aircraft Carrier, Destroyer, Frigate, etc.</i>

There are four important rules to note when dealing with superclasses and subclasses:

1. A subclass will inherit all the attributes from its superclasses. 
2. The subclass can have more then one superclass and it will inherit the attributes from all the superclasses.
3. The subclass can define its own attributes in addition to the ones inherited.
4. The subclass will also inherit the relationship sets in which the higher-level entity superclass participates.

This process of making a superclass from a group of subclasses is called Generalisation, a bottom up approach, and vice verser the process of making subclasses from superclasses is called Specialisation, a top down approach.

Sorry, I am aware that was a lot of the word <i>classes</i>!!!<br>

<img src="/assets/images/sdj3-2.PNG" alt="Generalisation Specialisation Approach"><br>

<b>Generalisation/Specialisation - Membership Constraints:</b>

<b>Predicate-defined subclass</b> <i>(Also referred to as Condition-defined)</i> - In this scenario we look to determine the entities to become a member of the subclass, we do this by putting a condition on an attributes value within the superclass. 

As an example a <i>Military Naval Ship</i> entity has a attribute of <i>Class</i>, the membership condition of the <i>Aircraft Carrier</i> subclass by the condition <i>Class = Aircraft Carrier</i>.

This is therefore the defining predicate of the subclass.

<b>Attribute-defined specialisation</b> - In this scenario the membership condition of all the subclasses, must be on the <b>same attribute</b> of the superclass entity. 

This is the defining attribute of the specialisation. Therefore if all the entities have the same attribute value, they all belong to the same sub-class.

<b>User-defined subclass</b> - In this scenario their is no requirement for a condition to be in place, instead the membership will be determined by the users of the database. 

This means that there is no automatic condition to be defined, it will simply be specified by the user.

<b>Disjoint and Overlap - Disjoint Constraints:</b>

<b>Disjoint</b> - is represented by a <b><i>d</i></b> in the circle (as shown in the following diagram).

Disjoint within the ERD means that the superclass entity can be a member of up to one of the subclasses. So a Military Naval Ship can only be one of the class, either an Aircraft Carrier, or Frigate or Destroyer.

<b>Overlap</b> - is represented by a <b><i>o</i></b> in the circle (replacing the <b><i>d</i></b> in the following diagram).

If the ERD is represented by an overlap it means that the entity can be a member of more than one subclass, or in deed all the subclasses.

<b>How Disjoint and Overlap works with participation - Completeness Constraints:</b>

Including participation into the mix leads to four additional constraints when dealing with specialisation:

1. Disjoint, Total Participation - The superclass must be a member of one and no more then one subclass, the subclass cannot be NULL e.g. A <i>Military Naval Ship</i> must have a <i>Class</i> but only one <i>Class</i>, this is mandatory. An Aircraft Carrier cannot be a Frigate, and vice verser. 

2. Disjoint, Partial Participation - The superclass has optional subclasses but can be a member of none e.g. A <i>Military Naval Ship</i> may not yet have a <i>Class</i> if say it is a prototype still in construction. This is where we get 0 (zero) or NULL back in Chens Notation. 

3. Overlap, Total Participation - Must be a member of more than one or all subclasses, cannot be NULL. 

4. Overlap, Partial Participation - Can be a member of more than one or all subclasses, can also be NULL. 

<b>Example of Extended ERD:</b>

<img src="/assets/images/sdj3.PNG" alt="Specialisation Diagram"><br>

<b><u>WHY</u></b>

The added level of complexity introduced to the ERD this week has the added benefit of increasing its flexibility. 

For example the Completeness Constraints also us to create all the possible real world scenarios which must be accounted for if the finished diagram is going to yield the desired results and understanding of both the business team and the technical team. 

I can forsee an added benefit of this level of detail within the Conceptual ERD being in supporting the Normalisation process which will come later in the development life cycle. Although Conceptual ERD and Normalisation live in different areas of database development one can inform the other. 

<b><u>HOW</u></b>

A lot of what we've been looking at has been rules and constraints based. Having a clear understanding of how we implement those rules and constraints within the Conceptual ERD means that the diagram created is accurate (<i>as much as possible at this stage</i>) and useful as a resource by all business and technical users that have a stake in the development.

How much effort is put into creating a detailed and accurate picture of the database at this stage, through the use of the Conceptual ERD will ultimately lead to less errors in development, reduces the rik of misunderstandings and improving the system output. A business case can also be made for the time invested in the Conceptual ERD, with benefits included reduced development times, less requirements for changes or additions during development and ultimately a lower build cost.

<b><u>Game of Tile - Attributes Data Dictionary</u></b>

Further work carried out this week on 'Game of Tiles' has been the creation of the Attributes Data Dictionary as follows. 

<object data="/assets/docs/GoT_DD.pdf" type="application/pdf" width="100%" height="800px">
  <p>Attributes Data Dictionary<a href="/assets/docs/GoT_DD.pdf"></a></p>
</object>












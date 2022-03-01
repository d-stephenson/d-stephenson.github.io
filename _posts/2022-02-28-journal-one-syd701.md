---
layout: post
title:  "Journal #One [SYD701] - The Difficulty with Software" 
author: Dale Stephenson
categories: [ SYD701, Journal, Systems Development Methodologies ]
image: assets/images/syd701-j1
featured: true
hidden: true
---
<i>The Difficulty with Software</i>

JOURNAL #ONE [SYD701]

<h2>The Difficulty with Software</h2>

<h3>What makes good software difficult - <i>A Critical Analysis</i></h3>
 
Software development is still emerging, and it is not governed by a concrete set of rules and procedures that can be found, for example, in construction or manufacturing. Software is often custom-built and does not exist on its own, combining many elements that create the whole system. Although frameworks do exist a lot of software is unproven and must be tested to ensure the array of possible inputs, outputs, states and dependencies impact each other as expected.
 
Testing is often rushed, meaning the software is delivered to stakeholders having experienced limited user input, as a consequence, this increases the chance of failure. Problems can, on the other hand, come directly from users and stakeholders, who often don't know what they want. Uncertainty stemming from requirements gathering has the potential to lead to a large number of changes and change management processes can be insufficient at managing these changes. In software development, the agile methodology is deployed in an attempt to mitigate the risks involved in change.
 
Software development is affected by many external constraints:
 
- Hardware
- Integration
- Regulatory
- Legacy systems and formats
- Performance issues
- Scalability
 
Consider a web application, a business stakeholder will not want to lose customers because the software application does not function correctly on <i>Firefox</i> or <i>Safari</i>. The seemingly simple requirement to support multiple browsers inevitably increases complexity and the testing process.
 
Given that the barrier to entry into software is quite low, namely that it is easy to learn how to write code, there is a significant gap between writing code and delivering good software systems. Good software, therefore, requires top-class coders to deliver systems quicker, cheaper and with fewer defects.

<h3>No Silver Bullet—Essence and Accident in Software Engineering by Frederick P. Brooks, Jr. - <i>A Critical Review</i></h3>
 
The complexity of software development is a consequence of the essential tasks that makes it so difficult to achieve with a high degree of quality, these tasks cannot be avoided as collectively they are intended to solve the business or technical problem. Essential tasks are the development of the structures that construct the entire software system, being the functions that meet the business requirements, without them the end product will not succeed and will be deemed a failure.
 
Accidental tasks are also difficult, however, these are artificial barriers that happen to be in place, created by constraints inherent to the programming languages that map onto machine languages. Not only are these tasks not related to solving the problem directly, but there have also been significant gains with regards to speed and space constraints as a result of better-designed computer hardware and programming languages.
 
These gains can be thought of as an anomaly. Computer hardware development and integration have progressed at a pace greater than any other technology, a fact that gives the appearance of relatively slow progress with software development. This may have resulted in lofty expectations of software development that is both unfounded and unfair. 
 
The industry is at the point where reducing accidental tasks further will not result in any significant improvement in the difficulty experienced with software development, and this is the key difference between accidental and essential tasks. To reduce the difficulties in software development the focus must move to essential tasks, which has not benefitted from the same order of improvement. Software is, by its nature, a conceptual construct that requires detailed specifications, design and testing, all difficult elements to execute when ensuring requirements are met errors mitigated. Unless this changes, gains from improving the essential tasks will not experience the gains witnessed with accidental tasks.
 
<h4>Complexity</h4>
 
Software systems are made up of many complex parts with no two necessarily being alike, this allows them to have a large number of states that makes them difficult to conceive, communicate amongst teams, test and scale, which requires increasing numbers of elements to do so whilst also ensuring that the complexity inherent to scaling is not linear. Furthermore, as discussed, any attempt to remove the complexity removes the essential elements that make the software system, the complexity is, therefore, necessary whilst also being the cause of product failure, increased costs and delays.
 
<h4>Conformity</h4>
 
Software systems must conform to the systems it interacts with, these have often existed for longer than the software itself and can differ across interfaces and time, a software redesign will not be capable of simplifying the process of conformance. It may also be the case that the software must conform because it is the best solution for the physical system to which it is being applied.  
 
<h4>Changeability</h4>
 
Software is incredibly malleable and easy to change, of course, this leads to all software experiencing change. Two reasons lead to software change, (1) beneficial software often gets used for new use cases beyond the original purpose, users and stakeholders will demand new features and functionality to meet these new use cases, and (2) the software is extended beyond its original planned life cycle meaning it must conform to new technology hardware and business opportunities.
 
<h4>Invisibility</h4>
 
Software is difficult to visualise and often requires numerous graphical depictions, such as control flows, data flows, time sequencing and other diagrams that can be produced using UML, for example. These visualisation tools are not always hierarchical or planar but are a disparate set of visualisations stacked on top of one another. Despite these diagramming tools, the software is still difficult for humans to visualise conceptually, which increases communication and design process problems.

<h3>Chapter 1: The Joys (and Woes) of the Craft, <i>The Mythical Man-Month</i> (1974) by Frederick P. Brooks - <i>A Critical Review</i></h3>
 
<i>Q: Did anything in the section surprise you or cause you to think about software differently? What and why?</i>
 
What is most surprising is that seemingly nothing has fundamentally changed with the significant passage of time. The technology industry is often perceived to be at the forefront of modern developed societies and post-industrial economies, and no doubt there have been significant increases in processing power and data storage capacity, however, little appears to have fundamentally changed in how software is built, despite the changes in programming languages and richness of the features and functionality that is now possible.
 
<i>Q: Do you disagree with Fred Brooks on anything? Why?</i>
 
At first, I disagreed with several comparisons made by the author, for instance, those made between the programmer and the poet and the creative aspect of programming. On re-reading the passage I find it more difficult to disagree, not because my views have changed, but because the author has chosen his words very carefully.
 
One caveat to the above statement, is that the author starts the passage with:

> "Why is programming fun?"

I might have started with:

> "Is programming fun?"
 
<i>Q: Is his perspective from 50 or so years ago still relevant? Or have there been changes since 1974 which would render his observations obsolete? Why?</i>
 
I agree with his statement that indicates the software industry is still looking for the next best thing, which does not appear to be based on technological advancement or great commercial application. Perhaps instead, there needs to be a paradigm shift towards seeking solutions that have longevity, although the complexity with software leads to a somewhat pessimistic outlook.

<div style="background-color: #f6f6f6; padding: 1rem; border-radius: 10px 20px;"> 
    <i>References</i>
</div>
<br>
CSCI 3308—Fall 2006—Homework 1 Answers. (n.d.). Retrieved February 27, 2022, from [https://home.cs.colorado.edu/~kena/classes/3308/f06/reference/answers/hw01.html](https://home.cs.colorado.edu/~kena/classes/3308/f06/reference/answers/hw01.html)

What are essential and accidental complexity? (n.d.). Quora. Retrieved February 27, 2022, from [https://www.quora.com/What-are-essential-and-accidental-complexity](https://www.quora.com/What-are-essential-and-accidental-complexity)
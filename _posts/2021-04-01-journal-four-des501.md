---
layout: post
title:  "Journal #Four [DES501] - Systems Development Life Cycle" 
author: Dale Stephenson
categories: [ DES501, Journal, Design and Development Concepts ]
image: assets/images/DES501-J4.jpeg
featured: true
hidden: true
---
<i>Systems Development Life Cycle</i>

JOURNAL #FOUR [DES501]

<h2>Systems Development Life Cycle</h2>

The Systems Development Life Cycle (SDLC) is used by software engineers and development teams to plan, structure and control the development process. 

The SDLC was introduced as a standardised methodology to respond to the growing complexity within software development. It is an approach that sought to correct the practice of programmers, when being asked by businesses and organisations to resolve an issue or carry out a procedure, giving little thought to stakeholder or user needs and requirements. Developers don’t need to look back too far to see the effects of not adopting an SDLC approach.

The complexity of modern systems and the delivery of a successful project requires the collaboration of teams to work together and manage the development across the teams, which is accomplished by the several phases of the SDLC: 

 <table style="width:100%">
  <tr>
    <th>Phase</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>1</td>
    <td>Systems Planning</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Systems Analysis & Requirements</td>
  </tr>
    <tr>
    <td>3</td>
    <td>Systems Design</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Systems Development</td>
  </tr>
    <tr>
    <td>5</td>
    <td>Systems Integration</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Systems Implementation</td>
  </tr>
  <tr>
    <td>7</td>
    <td>Systems Operation</td>
  </tr>
</table> <br>

The SDLC supports various models that are industry recognised, these include:

<h4>Waterfall Model</h4>

The waterfall model is often viewed as a more traditional approach to systems development and as such has largely been replaced by other methodologies. The approach is linear in its implementation, meaning each phase of the SDLC must be completed before the next one begins, with a review often conducted at the end of each completed phase to determine if the project has remained on the right track.

<h4>Iterative Model</h4>

The iterative approach splits the SDLC into smaller more easily manageable iterations, these iterations pass through the life cycle phases so that a working prototype is developed far sooner in the development process. This is particularly useful in cases where requirements are clearly understood and there is pressure to release a product to market in a short time-frame. There are obvious cost benefits to this approach, for example, the flexibility, testing, and debugging of these smaller iterations is easier and combined reduce the development risk.

<h4>Spiral Model</h4>

The spiral model is split into four sections and each revolution of the spiral is a separate iteration, each iteration represents a set of requirements that must be analysed by a systems analyst and developed. The development is conducted through the use of prototyping, with the final stage utilising an operational prototype for design analysis, the production of code, and the required implementation testing. 

<h4>Prototype Model</h4>

The prototype model adopts a different approach which aimed to overcome some of the limitations to the waterfall method, namely that an understanding of requirements is gained through the construction of a system prototype. The approach allows stakeholders and users to examine the prototype to help understand its features and provide valuable feedback, it also allows for the detection of errors and risks very early in the development process.  

<h4>V-Model</h4>

The V-Shape model essentially extends the waterfall method but incorporates testing at each stage of development. The ‘V’ stands for verification or validation, establishing a corresponding test phase to each stage of the SDLC. As with the waterfall model, this is a rigid approach to systems development, a proceeding stage cannot be started until validation of the preceding stage is complete. 

<h4>Agile Model</h4>

The agile approach to software development has become universally popular in software development, partly because it has great flexibility that allows teams to adapt quickly as business or functional requirements change, this is important in the current fast-changing commercial environment.

There are several approaches to agile:

- Rational unified process
- Scrum
- Crystal clear
- Extreme programming

<h2>DevOps Life Cycle</h2>

The aim of DevOps is to shorten the development time of systems, this includes the delivery of feature updates and fixes that align with the objectives of the business. The approach is intended to produce software that is of a superior quality that is more reliable for users and stakeholders whilst reducing the development time.

The DevOps Life Cycle encompasses various phases:

- Continuous Development 
- Continuous Integration 
- Continuous Testing
- Continuous Deployment 
- Continuous Monitoring 

<h4>Continuous Development</h4>

This phase involves software planning, deciding on the projects vision and the early stages of coding the application. The planning stage does not require any specific DevOps tools, however, the code written by the developers will require the use of version control tools. This 'Source Code Management' has many choices of industry recognised tools including:

- Git
- JIRA
- SVN
- Mercurial

These tools support the desire of development teams to collaborate, communicate, and produce quality software - ultimately they help ensure success when deploying a DevOps approach for projects.

<h4>Continuous Integration</h4>

Continuous integration is a practice deployed by software developers where they increase the frequency of commit changes to the source code, this could be daily or weekly depending on requirements. Commits are built and used to detect problems and aid with:

- code review
- unit and integration testing
- packaging

Any developed code that supports new functionality will be integrated continuously with the existing code. The integration must occur smoothly with the systems to ensure end-users don't suffer disruption to service.

<h4>Continuous Testing</h4>

System testing is performed continuously to discover bugs that might disrupt the user experience or leave the app vulnerable to attacks from threat actors. Tools can be deployed to aid testing and to automate the process, this allows the testing of multiple code-bases to ensure that functionality flaws are identified and rectified. 

Automation reduces the effort involved in executing tests and allows them to be performed in a shorter time frame. Also, automation tools can produce reports that can be used to evaluate test cases that have failed. Test environments such as Docker Containers can be used to support this process. 

<h4>Continuous Deployment</h4>

Continuous deployment is a software development method that takes code and puts it into the hands of the end-user as quickly as possible. Once developers are satisfied with the testing process and have confidence that the code is free from bugs and errors, the software can be deployed automatically into the production environment. 

Many development teams that utilise this method will often only release small code changes, the hope is that if something unexpected occurs it is far easier to roll back and uncover the issue. To ensure continuous development is successful, the system testing should be robust to maintain a high level of trust in the process. 

<h4>Continuous Monitoring</h4>

This phase is where system performance is continuously monitored. Information relating to performance is recorded and processed to ensure that functionality is operating as expected. This phase provides an opportunity to identify and resolve low memory issues or server connection problems.

Determining the root cause of issues through continuous monitoring assists teams to maintain the availability and security of the system, which means that fixes can be applied as soon as they are detected. This phase is often supported by the operations team and end-users, who will often be the first to identify application problems.

<i>References</i>

DevOps Lifecycle: Everything About DevOps Lifecycle Phases. (2019, June 27). Edureka. https://www.edureka.co/blog/devops-lifecycle/

Introduction to the systems development lifecycle. (2016, May 5). Arrk Group. https://www.arrkgroup.com/thought-leadership/introduction-to-the-systems-development-lifecycle/

SDLC: Seven Phases of the System Development Life Cycle. (n.d.). Retrieved March 27, 2021, from https://www.innovativearchitects.com/KnowledgeCenter/basic-IT-systems/system-development-life-cycle.aspx

Staff Writer. (n.d.). Comparison of Various Software Development Life Cycle. ITProPortal. Retrieved March 27, 2021, from https://www.itproportal.com/2010/07/04/comparison-various-software-development-life-cycle/

What Is Continuous Deployment? Everything You Need to Know - DZone DevOps. (n.d.). Dzone.Com. Retrieved April 1, 2021, from https://dzone.com/articles/what-is-continuous-deployment-everything-you-need
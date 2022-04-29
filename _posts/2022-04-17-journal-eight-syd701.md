---
layout: post
title:  "Journal #Eight [SYD701] - Software Development Methodologies - Overview" 
author: Dale Stephenson
categories: [ SYD701, Journal, Systems Development Methodologies ]
image: assets/images/syd701-j8.jpg
featured: true
hidden: true
---
<i>Software Development Methodologies - Overview</i>

JOURNAL #EIGHT [SYD701]

<h2>Deploying Software Development Methodologies</h2>
  
Software development methodologies have been created to manage software development projects, addressing issues that include, but are not limited to:
 
- Features for inclusion 
- Release periods
- Allocation of work
- Relevant testing
 
It is important to understand that no one methodology is a fit for all situations, even methodologies that have fallen out of fashion still have a place. In practice, the situation can become less structured than the chosen methodology suggests, with organisations varying the management of software development between projects, or using a combination of several to suit their needs and requirements. Choosing the right approach is critical for success and can have a significant impact on:
 
- Meeting costs and deadlines
- Client satisfaction
- The robustness of the software 
- Minimise expenses where failure occurs
 
<h3>Types of Methodologies</h3>
 
The following list reveals the extent to which solutions have been developed to provide a solution to practical software development, to enable it to meet requirements and improve success:
 
- Waterfall 
- Agile family:
    ○ SCRUM
	○ Dynamic Systems Development Model (DSDM) 
	○ Rapid Application Development (RAD)
	○ Extreme Programming (XP)
	○ Feature-Driven Development (FDD)
	○ Internet-Speed Development
- Evo
- Unified Process family:
	○ Rational Unified Process (RUP)
	○ Open Unified Process (OpenUP)
	○ Essential Unified Process (EssUP) 
	○ Agile Unified Process
	○ Enterprise Unified Process
- PRINCE2 (PRojects IN Controlled Environments 2) 
- Project Management Body of Knowledge (PMBOK)
- Capability Maturity Model Integration (CMMI)
- Microsoft Solutions Framework (MSF)
- Crystal Methods Methodology
- Joint Application Design (JAD) 
- Lean Development (LD)
- Spiral Model
- Systems Development Life Cycle (SDLC) 
 
The complexity, ease of modifying code and cascading effect of software development means that small mistakes have a large impact, this is not as common in other project fields such as construction. This makes independent unit and functional testing essential to:
 
- Correct behaviour
- Integrate security
- Ensure performance standards
- Build robustness 
- Maintain compliance 
- Ensure useability 
- Test for compatibility 
 
There is a significant focus on test-driven development (TDD) with many of these methodologies. This helps software teams to ensure sections of code work as intended. Key tests must be documented in advance in the design specification. Effective testing and documentation are essential to allow teams to make frequent version releases with confidence.
 
Table 1 highlights the emphasis given to various methodologies, the key ranges from very high (VH) to very low (VL).
 
<table>
  <tr>
    <th>Method</th>
    <th>Deadline Emphasis</th>
    <th>Cost Emphasis</th>
    <th>Quality Emphasis</th>
    <th>Project Size</th>
    <th>Release Frequency</th>
    <th>Planning Emphasis</th>
    <th>Coordination Tightness</th>
    <th>Additional Information</th>
  </tr>
  <tr>
    <td>LD</td>
    <td>H</td>
    <td>H</td>
    <td>VL</td>
    <td>S</td>
    <td>H</td>
    <td>L</td>
    <td>L</td>
    <td></td>
  </tr>
  <tr>
    <td>RAD</td>
    <td>H</td>
    <td>H</td>
    <td>VL</td>
    <td>S</td>
    <td>H</td>
    <td>L</td>
    <td>L</td>
    <td></td>
  </tr>
  <tr>
    <td>DSDM</td>
    <td>H</td>
    <td>H</td>
    <td>M</td>
    <td>S</td>
    <td>H</td>
    <td>M</td>
    <td>L</td>
    <td></td>
  </tr>
  <tr>
    <td>Internet-Speed Dev</td>
    <td>H</td>
    <td>H</td>
    <td>L</td>
    <td>S</td>
    <td>VH</td>
    <td>M</td>
    <td>L</td>
    <td></td>
  </tr>
  <tr>
    <td>SCRUM</td>
    <td>H</td>
    <td>H</td>
    <td>M</td>
    <td>M</td>
    <td>H</td>
    <td>M</td>
    <td>M</td>
    <td></td>
  </tr>
  <tr>
    <td>FDD</td>
    <td>M</td>
    <td>M</td>
    <td>M</td>
    <td>M</td>
    <td>M</td>
    <td>H</td>
    <td>H</td>
    <td></td>
  </tr>
  <tr>
    <td>Agile Unified Process</td>
    <td>M</td>
    <td>M</td>
    <td>M</td>
    <td>M</td>
    <td>M</td>
    <td>H</td>
    <td>H</td>
    <td></td>
  </tr>
  <tr>
    <td>Evo</td>
    <td>M</td>
    <td>M</td>
    <td>M</td>
    <td>M</td>
    <td>M</td>
    <td>H</td>
    <td>H</td>
    <td></td>
  </tr>
  <tr>
    <td>MSF</td>
    <td>L</td>
    <td>H</td>
    <td>H</td>
    <td>L</td>
    <td>L</td>
    <td>H</td>
    <td>H</td>
    <td></td>
  </tr>
  <tr>
    <td>Open UP</td>
    <td>L</td>
    <td>L</td>
    <td>H</td>
    <td>S</td>
    <td>L</td>
    <td>H</td>
    <td>H</td>
    <td></td>
  </tr>
  <tr>
    <td>XP</td>
    <td>H</td>
    <td>L</td>
    <td>VH</td>
    <td>M</td>
    <td>M</td>
    <td>H</td>
    <td>H</td>
    <td>Product quality emphasis </td>
  </tr>
  <tr>
    <td>Crystal Methods</td>
    <td>L</td>
    <td>L</td>
    <td>VH</td>
    <td>L</td>
    <td>L</td>
    <td>H</td>
    <td>H</td>
    <td>Team member utilisation</td>
  </tr>
  <tr>
    <td>Spiral</td>
    <td>L</td>
    <td>L</td>
    <td>H</td>
    <td>L</td>
    <td>H</td>
    <td>H</td>
    <td>H</td>
    <td>Experimental Projects</td>
  </tr>
  <tr>
    <td>PRINCE2</td>
    <td>L</td>
    <td>H</td>
    <td>H</td>
    <td>L</td>
    <td>L</td>
    <td>M</td>
    <td>M</td>
    <td>Focus on process</td>
  </tr>
  <tr>
    <td>JAD</td>
    <td></td>
    <td>H</td>
    <td></td>
    <td></td>
    <td></td>
    <td>H</td>
    <td>H</td>
    <td>Requirements Gathering</td>
  </tr>
  <tr>
    <td>Waterfall</td>
    <td>L</td>
    <td>L</td>
    <td>H</td>
    <td>L</td>
    <td>L</td>
    <td>H</td>
    <td>H</td>
    <td>High cost of rework</td>
  </tr>
  <tr>
    <td>PMBOK</td>
    <td>L</td>
    <td>L</td>
    <td>H</td>
    <td>L</td>
    <td>L</td>
    <td>H</td>
    <td>H</td>
    <td>Standards Compliance</td>
  </tr>
  <tr>
    <td>RUP</td>
    <td>L</td>
    <td>L</td>
    <td>VH</td>
    <td>VL</td>
    <td>L</td>
    <td>H</td>
    <td>H</td>
    <td>Documentation, Training, Certificates </td>
  </tr>
  <tr>
    <td>CMMI</td>
    <td>L</td>
    <td>L</td>
    <td>VH</td>
    <td>L</td>
    <td>L</td>
    <td>H</td>
    <td>H</td>
    <td>Process improvement</td>
  </tr>
  <tr>
    <td>SDLC</td>
    <td>VL</td>
    <td>VL</td>
    <td>VH</td>
    <td>VL</td>
    <td>VL</td>
    <td>VH</td>
    <td>VH</td>
    <td>Formalised process</td>
  </tr>  
  <tr>
    <td>Enterpride Unified</td>
    <td>VL</td>
    <td>VL</td>
    <td>H</td>
    <td>VL</td>
    <td>VL</td>
    <td>VH</td>
    <td>VH</td>
    <td>Long-term projects</td>
  </tr>
</table>
<i>Table 1: Comparison of the various software development methodologies</i>
 
<h3>Common Reasons for Failure</h3>
 
When deciding on the right methodology, project leaders should consider which process is likely to cause the least pain and accomplish the various tasks on time and within budget. Failure to do so often leads to the following reasons software projects fail:
 
- Inability to effectively manage changing requirements, leading to cost and time overruns 
- Feature creep, adding more and more functionality that delays releases and rushing the testing process
- Underestimating the work involved or the number of unknown components required
- Lack of funding, choosing a methodology that places high emphasis on fixed costs projects can mitigate this risk 
- Inexperienced programmers can be eager but will be making mistakes on the job
- Insufficient market research and knowledge leads to software that is released too soon, too late or marketed incorrectly
 
<h3>An Analysis of Common Methodologies</h3> 
 
<h4>Waterfall Model</h4>
 
The waterfall model is often viewed as a more traditional approach to systems development, it is an approach that has been largely replaced by other methodologies. The approach is linear in its implementation, meaning each phase of the SDLC must be completed before the next one begins, with a review often conducted at the end of each completed phase to determine if the project has remained on track.
 
Although the waterfall method has largely been replaced, it does offer some benefits to development teams, namely that it is a simple method to understand with each phase distinct from the other and completed independently. The downside of this approach is that a working system is not developed until the end of the life cycle, which comes with significant risk and uncertainty for both developers and stakeholders. However, where there are very clear project requirements, particularly with smaller projects, the waterfall approach can be suitable.
 
<h4>Iterative Model</h4>
 
The iterative approach splits the SDLC into smaller more easily manageable iterations, these iterations pass through the life cycle phases for a working prototype to be developed far sooner in the development process. This is particularly useful where requirements are clearly understood and there is pressure to release the product to market in a short timeframe, Additionally, there are obvious cost benefits to the approach's flexibility, and testing and debugging of these smaller iterations is easier, which combine to reduce the development risk.
 
There are, however, problems with this methodology, life cycle phases often don’t overlap meaning requirements gathering can occur after development has begun, which can lead to architecture problems in later iterations.
 
<h4>Spiral Model</h4>
 
The spiral model is split into four sections, and each revolution of the spiral is a separate iteration with each iteration representing a set of requirements that must be analysed by a systems analyst. The development is conducted through the use of prototyping, with the final stage utilising an operational prototype for design analysis, the production of code, and implementation testing. The spirals four sections are as follows:
 
<b>Stage 1</b>
 
- Requirements agreed between business actors and developers
- Agreement as to the priority of requirements
 
<b>Stage 2</b>
 
- Exploration of technical possibilities and potential risks § Creation of prototypes by developers
- Business actors actively assess and review prototypes
 
<b>Stage 3</b>
 
- Assess the strengths and weaknesses of the prototypes and their ability to meet requirements
- Agreement as to the scope and design of the system to begin development of an operational prototype
- Development and testing of the system completed by the project team
 
<b>Stage 4</b>
 
- Software is released and implemented
- The release could be either a complete solution or incremental
 
The spiral model incorporates a significant amount of risk analysis making it beneficial for large, critical projects, this can often mean higher costs due to the requirement for specialised expertise in risk management.
 
<h4>Prototype Model</h4>
 
The prototype model adopts a different approach that aims to overcome some of the limitations of the waterfall method, namely that an understanding of requirements is gained through the construction of a system prototype. The approach allows stakeholders and users to examine the prototype to help understand the features and provide valuable feedback, it also allows for the detection of errors and risks very early in the development process.
 
Adopting this approach does not eradicate the potential for risk or errors as the method increases overall system complexity, meaning part of development includes repairing errors that are unavoidable due to the way it is being built. There are several techniques used for development:
 
<b>Throwaway:</b> The prototypes are discarded
<b>Evolutionary:</b> Prototypes evolve and become the final system
<b>Incremental:</b> The final system is a combination of separate prototypes
<b>Extreme:</b> Breaks development into three phases, static HTML pages, fully functioning and implementation
 
<h4>V-Model</h4>
 
The V-Shape model essentially extends the waterfall method but incorporates testing at each stage of development. The ‘V’ stands for verification or validation, establishing the corresponding test phase to each stage of the SDLC. As with the waterfall model, this is a rigid approach to systems development, a proceeding stage cannot be started until validation of the preceding stage is complete.
 
There are certain project scenarios where this methodology might be considered, such as developments that require a high level of accuracy and where the requirements are clearly defined. The development team would also need to incorporate qualified testers that are available to support the development process. Advantages and disadvantages of the method overlap with the waterfall approach.
 
<h4>Agile Model</h4>
 
The agile approach to software development has become universally popular, partly because it has great flexibility that allows teams to adapt quickly as business or functional requirements change, this is important in the current fast-changing commercial environment.
 
- There are several approaches to the agile method:
- Rational unified process 
- SCRUM
- Crystal clear
- Extreme programming
 
The agile methodology is best thought of as a set of values and principles that help teams work more efficiently. Deploying an agile framework for software development can mean following different practices and using various tools that help teams make decisions. This allows the decision-making process to result in better software development.
 
The agile concept seeks to assign value to certain items over others, to help developers carry out the development. These values are listed with a right and left side, valuing:

- Individuals and the interaction between individuals more than the tools and processes used to achieve a task or set of tasks
- Working software over comprehensive documentation
- Collaborating with customers over negotiating contracts
- An ability to respond to change over following a plan
 
The approach emphasises feature-driven, adaptative and dynamic systems development that were united in the Agile manifesto created in 2001, which listed 12 principles:
 
1. Satisfying the customer is the highest priority, achieved by early and continuous software delivery
2. Invite change throughout the development, particularly when advantageous to the customer's competitiveness
3. Deliver working software quickly, in as little as a few weeks or months
4. Work with business users and stakeholders daily
5. Develop the project around people that are motivated, providing the support and
environment to accomplish the job
6. Communicate information efficiently and effectively through face-to-face interactions
7. The best way to measure progress is through software that works
8. Stakeholders, developers, and users should be able to maintain a constant pace
throughout the development
9. Strive for a high degree of good design and technical excellence
10. Maximise the amount of work not done for greater simplicity
11. Create teams that can self-organise and produce the best requirements, designs, and
architecture
12. Through reflection, regularly adjust behaviour to become more effective
 
The agile approach is not the ‘practices’ the team use, the practices are a result of the team’s values and principles. This means that what works for one team won’t necessarily work for another, and why a team uses a practice is more important than what practices they use. Good agile teams will change and refine practices as the development progresses.
 
The agile approach can make it difficult to estimate a final cost and time frame projection as a result of change being a key methodology feature. It also demands a team that consists of professionals who are client-focused, whilst managing stakeholder and user requirements that might conflict with each other and existing systems that must be integrated.

<div style="background-color: #f6f6f6; padding: 1rem; border-radius: 10px 20px;"> 
    <i>References</i>
</div>
<br>
Introduction to the systems development lifecycle. (2016, May 5). Arrk Group.
[https://www.arrkgroup.com/thought-leadership/introduction-to-the-systems-development-lifecycle/](https://www.arrkgroup.com/thought-leadership/introduction-to-the-systems-development-lifecycle/)

Young, D. C. (2013). Software Development Methodologies.
---
layout: post
title:  "Journal #Twelve [PRJ701] - Looking Ahead" 
author: Dale Stephenson
categories: [ PRJ701, Journal, Project ]
image: assets/images/prj701-j12.jpg
featured: true
hidden: true
---
<i>Looking Ahead</i>

JOURNAL #TWELVE [PRJ701]

<h2>Looking Ahead</h2>
 
<h3>Data Team Sprint Demo</h3>
 
There were two key themes from the demo meeting marking the end of the fortnightly sprint:
 
1. Resolving the ongoing data validation issues and completing the automation in the Tableau dashboard and;
2. Progressing to the next stage of the project 
 
<h4>Issue Resolution</h4>
 
The data validation covers two areas, firstly clarifying the team understanding of the extract and load process currently being performed by <i>Stitch</i>. A determination needs to be made as to whether it currently identifies <i>only</i> new records created and updates the data warehouse with those records, or whether it is capable of identifying changes made to existing records in the sales application. A test deal has been created in the sales application and this will be used to determine the extents to which <i>Stitch</i> performs the updates. Several solutions are in consideration, should the application be found to <b>not</b> meet these technical requirements.
 
Secondly, the data warehouse requires changes to meet the requirements of business stakeholders regarding the recurring revenue. It was understood that the currency was 'locked in' at the point of sale, however, this is not the case. The finance and sales operation teams 'lock in' the currency rate at the start of each month, the recurring revenue must be converted to the currency at the month it is recognised against and not the currency at the outset of the deal.
 
The issues with <i>Tableau</i> that have been discussed in [Journal Ten](https://d-stephenson.github.io/prj701/journal/project/2021/10/04/journal-ten-prj701.html) have now been resolved. Unfortunately, this was not in time for the demo meeting. The extended free trial of <i>Tableau</i> ended on the morning of the demo and this was unresolved in time for the sprint. However, once the licence was activated and the desktop version made available, the remaining work that couldn't be carried out due to the limitations of the cloud version could be completed. Many of the unresolved issues were simple fixes and included low tech requirements such as branding, two key technical areas have been resolved, one satisfactorily, and the other that may require contact with <i>Tableau</i> support.
 
The first issue was the creation of alerts, although this is exclusively a cloud integration it appears a licence was required to activate the function. An alerts worksheet has been created to handle these business requirements. Currently, this is being tested against monthly revenue, when it reaches key milestones an alert notification is sent by email. Once the team is comfortable with this output, other alerts can be discussed with stakeholders and incorporated into the worksheets. Multiple alert sheets may be required depending on the sensitivity of the data, consideration will have to be made to <i>general users</i>, <i>users by department</i>, or <i>management level users</i>.
 
The second issue was with the revenue split between direct and partner generated, the total of this split, the total targets, and the percentage achieved. The worksheet splits the total targets (retained as total figures) into the same format as the actual revenue, even though a target split is not present in the data set, the percentage achieved column produced the same results. The <i>Tableau</i> documentation indicated that in the desktop version unwanted columns could be hidden, this did not solve the issue and hiding the target columns also hid the actual revenue columns. The only way to solve this in the interim was to create these results in a separate worksheet and join them in the dashboard, this is not an ideal solution and the hope is <i>Tableau</i> support might have a solution. A further thought is it may be a consequence of blending the data sources directly in <i>Tableau</i>, once the target data is ingested into the data warehouse it may results in it being an easy fix.
 
In any event, the sales and revenue dashboard is complete and automated requiring no further input by the technical or business members of the team. Once the currency conversion rate against recurring revenue is resolved the dashboard will display accurate and near real-time data.
 
<h4>Integrating <i>Halp</i> with <i>Jira Service Management</i> and <i>Slack</i></h4>
 
Although uncommon to add a new item to an existing sprint, there was a revisit to a test performed during the security sprints concerning the SOC 2 audit. There is a desire to simplify the submission of data requests across the company. One solution is to use <i>Slack</i>, however, it would be difficult gaining meaningful metrics from the conversation history. It was suggested that <i>Halp Conversational Ticketing</i> be tested as a <i>Slack</i> integration to replicate the forms already created in <i>Jira</i>, thereby keeping it in the existing conversational ecosystem that most users are familiar. <i>Halp</i> is an <i>Atlassian</i> product, simple integration was anticipated as a result, however, the setup of the tickets is somewhat convoluted and, much like <i>Jira</i> (JSM), it requires several processes before the tickets are ready to deploy. The first step requires the creation of a 'recipe' that sets the fields relating to the ticket from JSM, in addition to any associated rules that are set. Once this is done the ticket needs to be created and built around the 'recipe' before being linked to a secure channel in <i>Slack</i>.
 
<center><img src="/assets/images/prj-j12-Halp-Integration.png" alt="Halp integration with Slack"></center>
<br>
The integration is run on a two-week trial, at which point a determination will be made whether to proceed. An assessment will be made based on the uptake by users and the services ability to improve the quantity and quality of data requests.
 
<h4>Goals</h4>
 
The high-level goals for the coming sprint focus on moving the project forward a step. The priority is to create a dashboard in <i>Tableau</i> that can act as a source of truth for the currency conversion for each region the company operates. <i>Snowflake</i> offers integrations through the marketplace that can perform this activity. An initial assessment indicates it is likely to be an expensive solution, further research will be conducted to find a solution the meets the technical and budgetary requirements of the project.
 
The focus will also move to the production data, specifically how this can be integrated into the data warehouse and matched with financial averages as they relate to the creative team members. The intention for this stage of the project is to produce data granularity at the individual deal level for <i>Gross Profit</i> figures. The potential for business insights and to answer business questions across the company will be greatly increased and invaluable as a result of the successful outcome of this step of the project.
 
Finally, stakeholders would prefer to not only have the current deal status stored in the data warehouse but a history of the change in status of a deal. This will require several date fields incorporating into the <i>fact</i> table that log the dates the status of a deal changed, against the status the deal moved to. The current deal status can be determined by the date values if the process flow of a deal is one-way and in one direction only. If a deal can be moved back and forward between statuses this could become more complex to resolve. 

<div style="background-color: #f6f6f6; padding: 1rem; border-radius: 10px 20px;"> 
    <i>References</i>
</div>
<br>
Atlassian. (n.d.). Halp Conversational Ticketing for Slack and Microsoft Teams. Atlassian. Retrieved October 14, 2021, from [https://www.atlassian.com/software/halp](https://www.atlassian.com/software/halp)

How the Jira Slack integration works—Halp Support Docs. (n.d.). Retrieved October 14, 2021, from [https://plz.halp.com/article/1ns7jrn7tt-how-the-jira-slack-integration-works](https://plz.halp.com/article/1ns7jrn7tt-how-the-jira-slack-integration-works)
---
layout: post
title:  "Journal #Three [PRJ701] - Kick-Off" 
author: Dale Stephenson
categories: [ PRJ701, Journal, Project ]
image: assets/images/prj701-j3.jpg
featured: true
hidden: true
---
<i>Kick-Off</i>

JOURNAL #THREE [PRJ701]

<h2>Kick-Off</h2>

<h3>Data Team Kick-Off</h3>
 
The 'Data Team Kick-Off' marked the formalisation of the team collective efforts to progress towards meeting the requirements of stakeholders and the organisational departments. The SCRUM methodology will be deployed practically and is defined by the following:
 
- Fortnightly sprints ending mid-week
- Daily stand-ups
- Fortnightly demo meeting to occur post sprints
- Allowance for retrospective and further stakeholder planning 
 
Jira Service Manager (JSM) has been utilised to create the backlog and to inform the sprints, JSM will also be used to create a roadmap for the project. It will be important to record and log the questions that are being asked by stakeholders and departments, work will proceed based on the urgency of the data that can be analysed.
 
The initial focus will be to query production data to establish gross profit and gross margin by understanding the production time in hours and the production cost, i.e. cost of sales. This data will come from multiple applications and spreadsheets.
 
<h3>Snowflake</h3>
 
A virtual meeting was held with members of Snowflake's sales and engineering team based in New Zealand. The following information should not be considered as minutes of that meeting to protect company confidentiality but includes key details that will inform the practical aspects of the project.
 
- Deploying dbt with Snowflake is simpler and more user friendly than AWS Glue 
- Excellent integration of Snowflake with GitHub

Security features include:

- Security by default
- Encryption in rest and transit
- SSO with Google and other well-known services 
- Authentication with MFA
- IP restriction 
- Business-critical subscription includes the option to use Private Link
- Integrations secured with credentials or key pairs (preferred)

Role-based admin access:

- SYSADMIN - for databases, schemas and data queries
- SECURITY ADMIN - for roles and permissions

It is recommended that these roles are independent of one another, however, users can switch between them

Charges and fees:

- Charges relate to storage and compute time (length of compute), it is more affordable therefore to batch insert data versus single record insert
- Inserts and queries alike are charged the same based on compute time 
- Documentation useful for, amongst other features, set-up and continuous loading
- Loading data from Postgres can be achieved through scripts that download the data to an AWS S3 bucket and loaded into Snowflake, alternatives include SaaS solutions such as Stitch that include benefits such as alerts but are charged separately 
- A new feature to investigate is 'Snowpipe - Serverless Ingestion'
 
<h3>Data Analytics Tools Analysis</h3>
 
A preliminary analysis has been conducted of three industry-leading data analytics tools, there is a significant number more that are both noteworthily and award-winning. Research of the products offered included online review and comparison sites in addition to testing the products using the following metrics:
 
- Ease of integration with SQL databases and application
- Set-up and deployment time
- Ability to create meaningful data using SQL and replication using the GUI environment 
- Dashboard and results visualisation, both within a secure environment and for public publication
- Quantity and quality of the features available particularly regarding the ability to visualise data   
- Security and privacy features with consideration to GDPR 

<center><object data="/assets/docs/prj-j3-1-DataAnalyticsComparison-Table.pdf" type="application/pdf" width="100%" height="625px">
  <p>Data Analytics Comparison Table <a href="/assets/docs/prj-j3-1-DataAnalyticsComparison-Table.pdf">Documentation</a></p>
</object></center><br>

<center><img src="/assets/images/prj-j3-2-DataAnalyticsComparison-Chart.png" alt="Data Analytics Comparison Chart"></center><br>
 
<h4>Conclusion</h4>

It was ultimately decided that Tableau was the preferred option despite it being the most expensive product. The vast array of features, relative ease of use in comparison to Metabase, the visualisation options and security have been the determining factors in the decision making process. Power BI was the 'wild card' in this comparison and was feature rich with excellent security, whereas Metabase overall was considered sufficient, it was unable to meet requirements to an acceptable level. 
 
<h3>Data Pipeline</h3>
 
The following diagram provides a high-level representation of the existing data pipeline.

<center><img src="/assets/images/prj-j3-3-DataPipeline.png" alt="High level Data Pipeline"></center><br>

<div style="background-color: #f6f6f6; padding: 1rem; border-radius: 10px 20px;"> 
    <i>References</i>
</div>
<br>
AWS Glue—Managed ETL Service—Amazon Web Services. (n.d.). Amazon Web Services, Inc. Retrieved August 14, 2021, from [https://aws.amazon.com/glue/](https://aws.amazon.com/glue/)

AWS PrivateLink – Amazon Web Services. (n.d.). Amazon Web Services, Inc. Retrieved August 14, 2021, from [https://aws.amazon.com/privatelink/](https://aws.amazon.com/privatelink/)

Dbt. (n.d.). Transform Data in Your Warehouse. Retrieved August 14, 2021, from [https://www.getdbt.com/](https://www.getdbt.com/)

Metabase vs Microsoft Power BI 2021—Feature and Pricing Comparison on Capterra. (n.d.). Retrieved August 14, 2021, from [https://www.capterra.com/business-intelligence-software/compare/176651-176586/Metabase-vs-Power-BI](https://www.capterra.com/business-intelligence-software/compare/176651-176586/Metabase-vs-Power-BI)

Stitch: Simple, extensible ETL built for data teams. (n.d.). Stitch. Retrieved August 14, 2021, from [https://www.stitchdata.com/](https://www.stitchdata.com/)

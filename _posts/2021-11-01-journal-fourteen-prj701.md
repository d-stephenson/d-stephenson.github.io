---
layout: post
title:  "Journal #Fourteen [PRJ701] - Project Conclusion" 
author: Dale Stephenson
categories: [ PRJ701, Journal, Project ]
image: assets/images/prj701-j14.jpg
featured: true
hidden: true
---
<i>Project Conclusion</i>

JOURNAL #FOURTEEN [PRJ701]

<h2>Project Conclusion</h2>

<h3>Data Team Sprint Demo</h3>
 
It’s fitting that this journal series is concluding with the reporting of a Sprint Demo in which the presentation of the final production data, and corresponding data visualisations in <i>Tableau</i>, was showcased to stakeholders. Although the PRJ701 project ends here, the work continues. There is still plenty the team aims to achieve over the next quarter and first half of next year, some of the immediate sprint items for the next fortnight are as follows:
 
1. Create a staging environment for Tableau, now it is capable of being used by stakeholders it is important that any testing is not performed on the production instance
2. Build upon the sales representative performance dashboard, including an increased number of metrics without having to produce a separate dashboard for each sales representative i.e. use filtering to lock down information based on the user account 
3. Create and implement naming conventions in <i>[dbt](https://www.getdbt.com/)</i> and <i>[Tableau](https://www.tableau.com)</i>, and document the structure 
4. Complete the remaining stakeholder interviews globally to provide direction for the team over the next quarter and beyond
 
<h4>Staging and Production <i>Tableau</i> Environment</h4>
 
Prior to the scheduled sprint demo the data visualisation was connected to the production data which will allow it to be used, and relied upon, by the business stakeholders. The migration from development to production data required changes to the IP address-based security permissions. The IP address for <i>Tableau</i> Cloud had been whitelisted, however, the desktop instance connects to the data through the local network. This is less than desirable from a security standpoint, but necessary as data connections can only be created in the <i>Tableau</i> desktop instance. There are additional benefits to using <i>Tableau</i> desktop, it includes more features and functionality, it is a faster method of creating a visualisation, and worksheets can be tested before publishing to the cloud instance.
 
Uptime and accuracy must be considered as a result of the production release, any further testing and upgrades now need to be performed in a staging sandbox environment to reduce the risk that technical errors affect larger groups of system users. This staging environment will allow the technical team to develop the service in isolation from the rest of the project team, changes can be presented in the demo meetings and validated before being made live in the production environment.
 
Preliminary research indicates that <i>Tableau Server</i> licensing allows for a single production environment and a further two pre-production environments. However, the pipeline deploys <i>Tableau Desktop</i>, which does not appear to have this feature. In effect, the desktop instance is acting as the staging environment, with the cloud instance being production. This does lead to problems, unvalidated changes could be published accidentally, causing unintended errors with the cloud production instance.
 
At this stage the only option appears to be the replication of the current production version in the desktop instance, publishing it to the cloud with permissions restricting access to the environment to only those members of the project team involved in development. Testing can be performed in this environment completely separate from the production environment, with changes moved across and version-controlled to ensure the validity of the data, and retain the reliability of the production environment.
 
It might be preferable to establish a connection from the development data into the staging sandbox environment, isolating it entirely from the production environment. This will require further consideration, despite the development data environment reflecting the production environment, it is updated daily not being part of the data stream, which might delay production implementation. Conversely, a <>Tableau</i> staging environment that is connected to the development environment would allow the technical team to assess how changes to the data warehouse schema might affect the production instance of the data visualisations. The trade-off will need to be considered, ultimately a decision may be made to implement two staging environments connected to both <code>development</code> and <code>production</code> data.
 
<h4>Sales Representative Performance Analytics</h4>
 
Several visualisations are capable of being produced from the growing data set in <i>[Snowflake](https://www.snowflake.com/)</i>, specifically surrounding the performance of sales representatives. Work in this area will also get the team closer to achieving the <i>Gross Profit</i> by <i>Deal</i> objective. The intention is to create a dashboard that is formatted to match the standards realised with the sales and revenue dashboard. This will, however, be slightly more complex. The data will cover a large number of sales representatives and will contain information that is classified as private. In this case, management stakeholders will want access to the complete data set and the design and structural layout of the charts must allow for this, whilst also being capable of being broken down to the individual sales representative level.
 
Currently, data charts for the sales representatives are created manually and displayed separately, being duplicated for each individual sales representative, this is not a scalable solution going forward. The dashboard must be capable of automatically adding new sales representatives when they are employed, and removing them from the data set should they leave the company. This can be performed with row-level security as discussed in [Journal Thirteen](https://d-stephenson.github.io/prj701/journal/project/2021/10/25/journal-thirteen-prj701.html). Further research and testing of the business intelligence visualisations will be necessary before a solution can be presented and a decision made.
 
<h4>Naming Conventions</h4>
 
The implementation and documentation of logical naming conventions across the data pipeline are necessary to future-proof the work, ensuring it can be easily referenced at a later date. A significant number of the calculations and parameters are repeatable and a suitable naming structure can make these intuitive to use and easier to deploy by other team members, making sharing and collaboration far simpler. The intention with the naming standards is to be consistent and explicit, and will utilise <code>camel case</code>.
 
The naming conventions applied in <i>Tableau</i> extends to worksheets and dashboards, including colour coding to tabs to identify those that have been published to the cloud, those that are retained in the desktop instance only, and those that are undergoing testing. The naming conventions are as follows:
 
- <code>date.</code> = calculations that relate to dates included automatic date selections
- <code>calc.</code> = calculation of an aggregated value
- <code>ws.</code> = identifies a worksheet
- <code>db.</code> = identifies a dashboard 
 
 <i>Tableau</i> includes a feature that allows calculations to be organised into groups which can further help locate generated calculations, these will be grouped by relations.
 
<i>dbt</i>, which performs the transformation of the data set, produce a style model that can be used as a naming guide. A file and naming structure will be generated based on this model that fits into three categories:
 
- Staging
- Marts
- Base/Intermediate 
 
The naming and field convention utilises <code>snake_case</code>, with names that are based on the business terminology as opposed to the source terminology. The structure implemented is as follows:
 
- Models should have primary keys named as <code>< object >_id</code> making it easy to identify the <i>id</i> referenced
- Columns that are timestamps should be named <code>< event >_at</code> for UTC or include the time zone if a different one is used, such as <code>< event >_at_pt</code> for pacific time
- Booleans should be named with the prefix <code>is_</code> or <code>has_</code>
- Fields that contain revenue should be in decimal currency, for example <code><event>19.99</code>, in instances where decimal currency is not used this should be indicated as follows <code>price_in_cents</code>
- Maintain consistency across models where possible, for example, keys relating to a <code>sales person</code> table should be named <code>salesperson_id</code> instead of <code>user_id</code>
- Reserve words should be avoided when naming columns
- Models for base/staging should order the fields into categories with identifiers first and timestamps at the end
 
<h4>Stakeholder Interviews</h4>
 
Part of the wider systems analysis and design process has included interviews with stakeholders globally, this has begun and is likely to take approximately 4 weeks to complete. Further interviews will be scheduled as required.
 
It is clear from the interviews that have taken place so far that there is a lot of information that stakeholders are looking for that the team did not anticipate, there is also a high degree of overlap, which helps the team to pinpoint a path to focus future efforts. Despite the overlap the scope of the information is broad, extending from Gross Profit at the deal level to gaining insights across the entire lifecycle of a deal, including time in production, the number of revisions, and amount of direct intervention by sales representatives etc. The urgency to gain these business insights and the complexity and granularity level differs from team to team, with the production department having the largest requirements list.
 
Source data is available that can support business insights capable of answering some of these questions, however, it is unclear at this stage how the deal lifecycle can be tracked to the granularity level indicated. This is the challenge that the data team will face in the coming quarter and early part of next year.
 
<h3>Poster Evening</h3>
 
The focus for the remaining section of this project will be on the recreation of the data pipeline to present at the poster evening. The intention is to display some of the tools deployed and showcase them digitally so they can be manipulated and interacted with in real-time.
 
Due to the confidentiality of the data involved, a test data set will be deployed that acts as a close facsimile to the workplace data. The data warehouse schema will deploy a fact constellation model that will be integrated with a <i>Tableau</i> instance. The intention is to carry out this work in an iterative manner, producing the greatest output to showcase at the poster evening. Given the time frame and availability of the free trial periods offered by these service providers, the priority will focus first on deploying the data warehouse and integration with the business intelligence tool.
 
Once a stable instance of the data warehouse is available and visualisation created, time permitting, other data integrations will be established with APIs to ingest similar data that has been included in the workplace pipeline. This may include connections with online spreadsheets or REST-based <code>JSON</code> APIs. As stated, a lot of what can be accomplished here will depend on the time available, constraints on the length of time of the free trials remaining in place for the poster evening, and the complexity of performing the process individually.

<div style="background-color: #f6f6f6; padding: 1rem; border-radius: 10px 20px;"> 
    <i>References</i>
</div>
<br>
Best Practices for Published Data Sources. (n.d.). Retrieved October 27, 2021, from [https://help.tableau.com/current/pro/desktop/en-us/publish_datasources_about.htm](https://help.tableau.com/current/pro/desktop/en-us/publish_datasources_about.htm)

Corp. (2021). dbt Labs. [https://github.com/dbt-labs/corp/blob/f26309a374ebc7b2bac9833c3fd004ceffdf08cb/dbt_style_guide.md](https://github.com/dbt-labs/corp/blob/f26309a374ebc7b2bac9833c3fd004ceffdf08cb/dbt_style_guide.md) (Original work published 2016)

Development Sandboxes: An Agile Core Practice. (n.d.). Retrieved October 27, 2021, from [http://www.agiledata.org/essays/sandboxes.html](http://www.agiledata.org/essays/sandboxes.html)

How we structure our dbt projects—Modeling. (2019, May 10). Dbt Community Discourse. [https://discourse.getdbt.com/t/how-we-structure-our-dbt-projects/355](https://discourse.getdbt.com/t/how-we-structure-our-dbt-projects/355)

Manage User Visibility. (n.d.). Retrieved October 27, 2021, from [https://help.tableau.com/current/online/en-us/user_visibility.htm](https://help.tableau.com/current/online/en-us/user_visibility.htm)

Tableau Naming Conventions: Our Best Advice for Calcs, Sheets & More. (2021, April 9). InterWorks. [https://interworks.com/blog/2021/04/09/tableau-naming-conventions-our-best-advice-for-calcs-sheets-more/](https://interworks.com/blog/2021/04/09/tableau-naming-conventions-our-best-advice-for-calcs-sheets-more/)

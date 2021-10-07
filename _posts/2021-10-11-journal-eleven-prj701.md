---
layout: post
title:  "Journal #Eleven [PRJ701] - Creating Business Intelligence" 
author: Dale Stephenson
categories: [ PRJ701, Journal, Project ]
image: assets/images/prj701-j11.jpg
featured: true
hidden: true
---
<i>Creating Business Intelligence</i>

JOURNAL #ELEVEN [PRJ701]

<h2>Creating Business Intelligence</h2>
 
<h3>Data Validation Progress</h3>
 
The benefit of the validation process against the data ingested into the data warehouse is the confidence to press ahead with meaningful business intelligence in Tableau. A shift back to the business requirements is necessary to determine how these can best be met, whilst also pursuing technical priorities such as system automation. Automation has been the main focus area, however, it is recognised that this conflicts with the stakeholder desire to manipulate the data.
 
This conflict is best illustrated with the current development of the dashboard design, which is an automated view that provides a snapshot of the near real-time, current monthly and quarterly information. However, the current dashboard design does not provide an ability to select different months or quarters, hindering their ability to self serve to meet their needs. There are several options to satisfy these requirements, which will require further testing of the features.
 
A point to note is that the data validation is not yet complete. There remain minor discrepancies that are still being discovered, the adage of <i>"as one problem is solved it raises another"</i> is certainly true in this case. For instance, resolving recurring revenue split over the correct months contains currency value errors in relation to the monthly currency exchange rate, resulting in a small percentage difference in total revenue that has been noticed by the financial stakeholders. To ensure trust in the accuracy of the data this will need to be resolved. Allocating the currency conversion rate for the date the recurring revenue was recognised, and not the currency conversion rate at the time of the deal, will resolve this issue.
 
<h3>Security & Privacy</h3>
 
Tableau has been chosen as the preferred software solution, pending licence agreements and cost. This has prompted several organisation controls that will allow the team to meet the company's commitment to GDPR and requirements as part of the SOC 2 Type-II audit. Two tasks are necessary, firstly a <i>Vendor Risk Assessment</i> and secondly, entries into the <i>SaaS Risk Register</i> are required. These tasks are both performed in <a href="https://www.atlassian.com/software/jira/service-management">Atlassian Jira Service Management</a>.
 
As part of this audit log process and to meet the security and organisational controls in place, an investigation of the vendor is required that includes:
 
- Any security accreditation held by the vendor
- The geolocation of the Vendor, considering support time, native languages, and GDPR for the storage of data
- Identify any regulatory risks the vendor may create for the company
- Identify any reputation risk that might occur by using the vendor
- Review data protection policies and values held by the vendor
- The scope of the integrations with other applications
- Whether the vendor meets the primary purpose of deployment
- Whether the vendor has a status page
- The level and professionalism of the customer service offered
- Testimonials of existing users and companies
- The pricing structure to mitigate and lock-in periods, exit penalties or unused credits
- Any trial period offered and to what extent it is available
 
Once the <i>Vendor Risk Assessment</i> is complete and a vendor chosen, risks can be identified and completed in the <i>SaaS Risk Register</i>. The risk register records:
 
- The company account holders
- A description of the application and its scope within the organisation
- A description of the risk or risks identified
- Calculate the probability of the risk occurring
- Calculate the impact of the risk should it occur
- Describe in detail any mitigation tools or controls that can minimise the chance of the risk occurring
- Develop a response plan that meets the companies incident response program
- Copies of any documents including but not limited to security audit reports, privacy compliance statements and white papers
 
<h3>Tableau Development</h3>
 
<h4>Blending Data Sources</h4>
 
Development has begun on meeting the requirements of the individual levels goals for this sprint, primarily <i>monthly revenue split by month for the current quarter by region</i>. These figures need to be totalled and compared against targets, with a calculation created to display the percentage achieved. Target figures are not yet ingested into the data warehouse, which requires a connection to be made between the Google Sheet and ETL platform Stitch. Creating a connection has proven unsuccessful resulting from deprecated features in Stitch, in the interim a connection has been made directly between Google Sheets and Tableau.
 
This has resulted in two problems having been recognised. Firstly Tableau, like Stitch, is not capable of connecting with data in shared organisational Google Drives, a copy must be created and stored in a private user Google Drive to establish the connection. Secondly, because the data is stored in a separate location it requires blending with the existing data from the data warehouse. Tableau offers several ways to do this, through the establishment of <i>relationships</i>, <i>joins</i>, or <i>blends</i>. Attempts were made to blend the data, during this process Tableau queries the data and aggregates the results to an appropriate level, because of this the data is never truly combined which isn't an ideal solution.
 
After a period of false starts, it was realised that the target data was not formatted in a way that Tableau could establish relationships that existed in the data set. Defining the relationship is the preferred method as it allowed for the highest degree of flexibility and adaptability from the structure. The solution was to revert to the spreadsheet and format the table so it offered the same level of granularity that is established in the data warehouse. This allowed for the creation of relationships not only on the dates but also on the region. This involved a process of increasing the data redundancy in the same way it is typically performed for a data warehouse dimensional schema. The process involved in data blending can be found <a href="https://help.tableau.com/current/pro/desktop/en-us/multiple_connections.htm">here</a>.
 
<h4>Revenue by Month for Quarter</h4>
 
Once the targets were available in Tableau they could be compared against the actual figures to date, the dragging and dropping of dimension attributes and fact measurements made this process simple for the total quarterly figure. The inclusion of months for the given quarter has proved more challenging. When these are added to the table using the attributes, the worksheet produces a monthly split of the <i>sales target</i>, only provided as a total quarterly figure by region. The <i>percentage achieved</i> results are split in this way. The documentation provided some calculations that might work as followed, these were tested and ultimately unsuccessful.
 
<code style="margin-left: 30px;">
IF DATETRUNC('quarter',[Revenue Recognised At])=DATETRUNC('quarter',TODAY())
<br>AND DATETRUNC('month', [Revenue Recognised At])=DATETRUNC('month',TODAY())
<br>THEN [Revenue cur] END
</code>
 
<code style="margin-left: 30px;">
IF DATETRUNC('quarter', [Date])=DATETRUNC('quarter',TODAY())
<br>THEN [total_monthly_target] END
</code>
 
Further research indicated these fields could be hidden from view, which seemed like an appropriately simple solution when compared with some of the complicated suggestions that were attempted. This feature was, however, unavailable in the cloud version, the desktop version being unavailable due to the free trial expiring. A meeting was held with the account representative where this was discussed, it was confirmed that the cloud version lacks the features to perform some of the functions asked of it. Fortunately, once the licence is established some of the problems faced should be resolved as a consequence of the added functionality, this extends to the issues identified with alerts and notifications.
 
<h4>Automation and Manipulation</h4>
 
Automation of the dashboard is complete except for displaying the months for the current quarter, this relies on the <i>Quarter Key</i> from the <code>dim_dates</code> table in the data warehouse. Additionally, the inclusion of the current month as a detail of the worksheet defined with <code>month(today())</code>, impacts the table columns in the worksheet, meaning this dimension cannot be used for the title. Further work is necessary to resolve these issues, however, reading the documentation indicates the best solution would be to create the <i>title</i> in a separate worksheet and added to the table in the dashboard.
 
Dashboard automation is very much a technical requirement, this is something the tech members of the team want to implement, recognising that it allows the data analyst to focus their efforts elsewhere. At present this conflicts with the business requirement to allow stakeholders to filter the data themselves to view the visualisation by <i>year</i>, <i>quarter</i>, <i>month</i>, <i>region</i> etc. The benefit of an interdisciplinary Scrum team is that these requirements can be shared in real-time before any final production version is ready to be demoed. Work has already begun on a dashboard that allows these users to filter the visualisation based on the date dimension table. The steps deployed are available <a href="https://help.tableau.com/current/pro/desktop/en-us/multiple_connections.htm">here</a>.  
 
The intention is to recreate a couple of visualisations first to test how these work against the filters, and add new filters to test the results. Ultimately, the goal is to automate the dashboard so that it displays all relevant data for the current <i>quarter</i> and <i>month</i>, therefore meeting both requirements.

<div style="background-color: #f6f6f6; padding: 1rem; border-radius: 10px 20px;"> 
    <i>References</i>
</div>
<br>
Blend Your Data. (n.d.). Retrieved October 7, 2021, from [https://help.tableau.com/current/pro/desktop/en-us/multiple_connections.htm](https://help.tableau.com/current/pro/desktop/en-us/multiple_connections.htm)

Date Calculations in Tableau. (n.d.). Retrieved October 7, 2021, from [https://dash-intel.com/tableau/date_calculations_tableau.php](https://dash-intel.com/tableau/date_calculations_tableau.php)

Group Your Data. (n.d.). Retrieved October 7, 2021, from [https://help.tableau.com/current/pro/desktop/en-us/sortgroup_groups_creating.htm](https://help.tableau.com/current/pro/desktop/en-us/sortgroup_groups_creating.htm)

How to create dynamic titles that change based on filter selections in Tableau—YouTube. (n.d.). Retrieved October 7, 2021, from [https://www.youtube.com/watch?v=4NWCQzyz7C8](https://www.youtube.com/watch?v=4NWCQzyz7C8)

How to Display Total of Each Bar on Stacked Bar Graph - Tableau Software. (n.d.). Retrieved October 7, 2021, from [https://kb.tableau.com/articles/howto/How-to-Display-Total-of-Each-Bar-on-Stacked-Bar-Graph](https://kb.tableau.com/articles/howto/How-to-Display-Total-of-Each-Bar-on-Stacked-Bar-Graph)

Organize and Customize Fields in the Data Pane. (n.d.). Retrieved October 7, 2021, from [https://help.tableau.com/current/pro/desktop/en-us/datafields_dwfeatures.htm](https://help.tableau.com/current/pro/desktop/en-us/datafields_dwfeatures.htm)

Tableau 201: How to Change Date Aggregation Using Parameters. (2015, March 2). Evolytics. [https://evolytics.com/blog/tableau-201-change-date-aggregation-using-parameters/](https://evolytics.com/blog/tableau-201-change-date-aggregation-using-parameters/)
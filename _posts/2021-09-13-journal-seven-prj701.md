---
layout: post
title:  "Journal #Seven [PRJ701] - Main Data Tracking & Regulation" 
author: Dale Stephenson
categories: [ PRJ701, Journal, Project ]
image: assets/images/prj701-j7.jpg
featured: true
hidden: true
---
<i>Data Tracking & Regulation</i>

JOURNAL #SEVEN [PRJ701]

<h2>Data Tracking & Regulation</h2>
 
<h3>Data Requests Tracking Framework</h3>
 
Daily standup discussions have revealed a need to track data requests from across business units. Although the more significant stakeholder requirements have ultimately led to the commissioning of the project, there are multiple department heads across regions and departments that have data needs. These needs might be better served through custom data analytics generated from the data warehouse.
 
Two questions had to be answered before a framework could be deployed:
 
Which business unit or units would benefit the most from the process and regularly use the service?
What tools are available that could be deployed to provide the service?
 
Due to the interdisciplinary nature of the data team, it was clear that the significant majority of requests for data related to sales and revenue information, meaning this department was going to benefit from the service in the first instance. The current ad-hoc method of collecting these requests across multiple communication channels was not sufficient to gain meaningful insights into the type of data necessary to service the company's demands.
 
Several options were touted as being an effective means of receiving requests, including a dedicated communications channel through Slack or other service providers, or utilise Jira Service Manager (JSM) that is already deployed and used across the technology and employee management areas of the business.
 
JSM was chosen as the preferred solution to log these requests. A follow-up meeting was arranged to understand the data to be collected and the employees that make these types of requests and would therefore require access to the service portal in JSM. The request form needed not to unduly put off users from submitting requests resulting in them reverting to old habits, it was decided that the form would include the following:
 
- The user making the request, this would be auto-completed through login
- The business question or summary of the data requirements 
- A more detailed description where necessary 
- The start date of the data request
- The end date of the data request
- The business region the data should cover
 
JSM allows the team to keep a record of requests and look for trends that might assist the development of the data warehouse and the type and degree of information that is made available to business stakeholders.  
 
<h3>Regulatory Compliance for Risk Mitigation</h3>
 
<h4>The Project from a Regulatory Viewpoint</h4>

Ultimately what we are aiming to accomplish with the project is further processing of data that is likely to include personally identifiable information (PII). Any such processing of data raises regulatory concerns for organisations that have an authentic interest in the security and privacy of the data they store concerning their clients, partners, employees and contractors. The principles inherent to the General Data Protection Regulations (GDPR) are:
 
1. Lawfulness, fairness, and transparency
2. Purpose limitation
3. Data minimization
4. Accuracy
5. Storage limitation
6. Integrity and confidentiality
7. Accountability 
 
Understandable, GDPR has had a significant impact on the technology sector, the platforms and emerging technologies that businesses and organisations deploy, and the business and technical decisions they make. The risk of non-compliance can lead to regulatory action from EU authorities whose reach extends from oversight to significant fines, both of which have the potential to cause reputation damage. Large firms such as Google, Facebook and Amazon have all updates their policies and procedures to meet the demands of the regulations.
 
What has emerged is a need for IT professionals to be aware of the GDPR. It is no longer the case that these matters can be confined to those employees and stakeholders charged with corporate governance. The regulations refer to this in their designation of a Data Protection Officer (DPO). The scope of this role is limited to public authorities or organisations whose core data processes meet the definitions outlined in the article. A DPO is not a requirement for all businesses, however, an organisation may decide it is in their best interests. There are key activities inherent to the formation of this role that show a merging of technological and regulatory expertise. DPOs should have a strong background in privacy and security as well as IT programming, infrastructure and information systems auditing.  
 
Consideration must be made to the GDPR across the organisation concerning large scale projects that have the potential to pose a 'high risk' to data subjects PII or personal data.
 
Compliance with GDPR in respect of large scale projects is conducted with a Data Protection Impact Assessment (DPIA), which exists under Article 35 of the GDPR and is part of the overarching principle of 'protection by design'. The purpose of the assessment is to account for the nature, scope, context and purpose of data processing where the rights and freedoms of data subjects are at significant risk as a result of an organisation deploying new technologies.
 
<h4>Data Processing</h4>
 
Before we look at the steps involved in conducting a DPIA, it is important to understand the legal bases for processing personal data to ensure compliance with the principle of lawful, fair, and transparent processing. Data processing is outlined in Article 6 of the GDPR and outlines six legal bases for the processing of PII and personal data:
 
1. Consent from the data subject 
2. To perform contractual obligations
3. There is a legitimate interest 
4. It is of vital interest 
5. There is a legal requirement
6. It is of public interest 
 
Organisations must map their data so they are aware and have a good understanding of the legal justification of its collection and processing.
 
<h4>Triggers</h4>
 
Several conditions would trigger a DPIA as follows:
 
- When deploying new technologies
- If the location or behaviour of data subjects is being tracked
- If a publicly accessible location is being monitored systematically on a large scale
- If special category data as defined under Article 9 is being processed
- If data relating to children is being processed
- If the processing of data could lead to physical harm is leaked following a data breach
- If the processing of data is used for automated decisions about data subjects that could lead to legal consequences 
 
The GDPR does not specify the use of a DPIA for these processes alone, it is reasonable therefore for organisations to consider conducting a DPIA to mitigate risk and limit any liability in the event a data breach triggers regulatory intervention. Assessments can be performed as part of wider data security and privacy standards and best practices.
 
<h4>Compliance</h4>
 
To comply with the requirements of the Article a DPIA should contain the following elements:
 
- The data controllers legitimate interest in the collection and processing of the data 
- A systematic description of the planned processing operations and the purpose of processing
- An assessment concerning the purposes of the processing, specifically assessing the necessity and proportionality of the project
- An assessment concerning the data subjects, the impact on their rights and freedoms
 
It is important to understand these elements so that measures, safeguards and mechanisms can be formulated and implemented to mitigate the risk. Documenting these steps is essential to ensure businesses and organisations can demonstrate compliance if necessary.
 
<h4>Initiate</h4>
 
If a determination is made that a DPIA is required then it must be carried out before any data processing takes place, it would be preferable to conduct an assessment during the planning stages of the project.
 
At all times the DPIA should be completed in consultation with the organisation's Data Protection Officer (DPO) if one exists and the stakeholders that have an interest in the project outcome.  
 
A template DPIA has been created by the UK’s Information Commissioner’s Office (ICO) and can be found <a href="https://gdpr.eu/wp-content/uploads/2019/03/dpia-template-v1.pdf" target="_blank">here</a>.

<div style="background-color: #f6f6f6; padding: 1rem; border-radius: 10px 20px;"> 
    <i>References</i>
</div>
<br>

Art. 9 GDPR – Processing of special categories of personal data. (n.d.). General Data Protection Regulation (GDPR). Retrieved September 8, 2021, from [https://gdpr-info.eu/art-9-gdpr/](https://gdpr-info.eu/art-9-gdpr/)

Art. 37 GDPR – Designation of the data protection officer. (n.d.). General Data Protection Regulation (GDPR). Retrieved September 9, 2021, from [https://gdpr-info.eu/art-37-gdpr/](https://gdpr-info.eu/art-37-gdpr/)

Atlassian. (n.d.). Jira Service Management - A new take on ITSM software. Atlassian. Retrieved September 8, 2021, from [https://www.atlassian.com/software/jira/service-management](https://www.atlassian.com/software/jira/service-management)

Data Protection Impact Assessment (DPIA). (2018, August 9). GDPR.Eu. [https://gdpr.eu/data-protection-impact-assessment-template/](https://gdpr.eu/data-protection-impact-assessment-template/)

He Li, Lu Yu & Wu He (2019) The Impact of GDPR on Global Technology Development, Journal of Global Information Technology Management, 22:1, 1-6, DOI: 10.1080/1097198X.2019.1569186 

Hinely, M. (2018, August 23). 6 Legal Bases for Processing Personal Data: GDPR Fundamentals - Video. KirkpatrickPrice Home. [https://kirkpatrickprice.com/video/gdpr-fundamentals-legal-basis-for-processing/](https://kirkpatrickprice.com/video/gdpr-fundamentals-legal-basis-for-processing/)

OneTrust. (n.d.). Understanding the 7 Principles of the GDPR - Blog. OneTrust. Retrieved September 9, 2021, from [https://www.onetrust.com/blog/gdpr-principles/](https://www.onetrust.com/blog/gdpr-principles/)
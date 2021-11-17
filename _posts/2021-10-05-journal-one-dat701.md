---
layout: post
title:  "Journal #One [DAT701] - Data Warehouse Design" 
author: Dale Stephenson
categories: [ DAT701, Journal, Enterprise Database Solutions ]
image: assets/images/dat701-j1.jpg
featured: true
hidden: true
---
<i>Data Warehouse Design</i>

JOURNAL #ONE [DAT701]

<h2>Data Warehouse Design</h2>

<h3>Dimensional Model</h3>

The developed data warehouse model is designed to meet the business requirements highlighted in Assignment 1 and utilises the methodology outlined by Moody et al. (2000) for the transforming of entity relational databases to dimensional data warehouses. The steps taken are described by Moody et al. (2000), which includes the classification of entities, the identification of hierarchies, and the aggregation of transactional data to form the dimensional model. Two design schemas have been considered and explored, a star schema and a fact constellation schema.

The benefit of deploying a dimensional schema for an enterprise data warehouse is the ability for end-users, particularly non-technical users, to produce business-level analytics and reporting (Moody et al., 2000). This is commonly deployed with user-friendly querying and business intelligence tools such as Power BI, these systems require no knowledge of SQL or other technical coding languages. Dimensional model databases are considered read-only and designed for data retrieval for analytics. Updates are normally performed with a batch extract, transform and load (ETL) (Moody et al., 2000). ETL is best performed during system downtime, preferably overnight so they do not affect query performance. Entities are classified into three categories as outlined in Table 1.
 
<table style="width:100%; table-layout: fixed;">
  <tr>
    <th style="padding:1%; vertical-align:top; text-align:center">Transaction</th>
    <th style="padding:1%; vertical-align:top; text-align:center">Component</th>
    <th style="padding:1%; vertical-align:top; text-align:center">Classification</th>
  </tr>
  <tr>
    <td style="padding:1%; vertical-align:top">Transaction entities are records relating to particular events that occur, such as sales orders, travel bookings, salary payments etc. These are the events that will be analysed by stakeholders to gain greater business insight.<br>

These entities are known as measures or quantities and will be identified by dollar figures or weights, for example. These entities are contained within the fact tables. Consideration should be made to those transaction entities that are capable of answering the business questions.</td>
    <td style="padding:1%; vertical-align:top">Component entities enable transaction entities to be described through direct one-to-many relationships. These answer the who, what, when, where, how, and why.<br>

Dimension tables are formed based on the component entities and can include the salesperson (who), the product (what), the location (where), and the period (when).</td>
    <td style="padding:1%; vertical-align:top">Classification entities are directly or transitively functionally dependent on component entities through one-to-many relationships.<br>

Classification entities may be collapsed into component entities to form dimension tables through their embedded hierarchy. FinanceDB contains classification entities such as Segment and Country that can be collapsed into the component, Region entity. Likewise, ProductCost is a classification of Product that can be collapsed into a DimProduct table.</td>
  </tr>
  <tr>
    <td style="padding:1%; vertical-align:top">- <i>SalesOrderLineItem</i></td>
    <td style="padding:1%; vertical-align:top">- <i>Promotion</i></td>
    <td style="padding:1%; vertical-align:top">- <i>ProductCost</i></td>
  </tr>
  <tr>
    <td style="padding:1%; vertical-align:top">- <i>SalesOrder</i></td>
    <td style="padding:1%; vertical-align:top">- <i>Product</i></td>
    <td style="padding:1%; vertical-align:top">- <i>Region</i></td>
  </tr>
  <tr>
    <td style="padding:1%; vertical-align:top"></td>
    <td style="padding:1%; vertical-align:top">- <i>SalesRegion</i></td>
    <td style="padding:1%; vertical-align:top">- <i>Country</i></td>
  </tr>
  <tr>
    <td style="padding:1%; vertical-align:top"></td>
    <td style="padding:1%; vertical-align:top">- <i>SalesPerson</i></td>
    <td style="padding:1%; vertical-align:top">- <i>Segment</i></td>
  </tr>
  <tr>
    <td style="padding:1%; vertical-align:top"></td>
    <td style="padding:1%; vertical-align:top"></td>
    <td style="padding:1%; vertical-align:top">- <i>SalesKPI</i></td>
  </tr>
</table>
<center>
    <i><b>Table 1</b> Entity Classifications for the FinanceDB database</i>
</center><br>

The classifications form a precedence hierarchy with transaction entities forming the highest precedence, through to classification entities, and ending with component entities as the lowest precedence. Entities are capable of being classified as either component or classification, where this is the case, the entity should be classified in the classification category. When entities do not fit into the hierarchical structure they are not capable of being included in the schema.
The following is the process deployed to identify the hierarchies:
- Product > Promotion > SalesOrderLineItem
    > Product is the parent of Promotion<br>
    > Promotion is the child of Product<br>
    > SalesOrderLineItem and Promotion are descendants of Product<br>
    > Product and Promotion are ancestors of SalesOrderLineItem
- Product > SalesOrderLineItem
- Product > Product Cost
- Country > Product Cost
- Country > Region > SalesRegion > SalesOrder > SalesOrderLineItem
    > Country is the parent of Region<br>
    > Region is the child of Country<br>
    > SalesOrderLineItem, SalesOrder, SalesRegion and Region are descendants of Country<br>
    > Country, Region, SalesRegion and SalesOrder are ancestors of SalesOrderLineItem
- Segment > Region > SalesRegion > SalesOrder > SalesOrderLineItem
    > Country is the parent of Segment<br>
    > Segment is the child of Country<br>
    > SalesOrderLineItem, SalesOrder, SalesRegion and Region are descendants of Segment<br>
    > Segment, Region, SalesRegion and SalesOrder are ancestors of SalesOrderLineItem
- SalesPerson > SalesKPI
- SalesPerson > SalesRegion > SalesOrder > SalesOrderLineItem
    > SalesPerson is the parent of SalesRegion<br>
    > SalesRegion is the child of SalesPerson<br>
    > SalesOrderLineItem, SalesOrder, SalesRegion are descendants of SalesPerson<br> 
    > SalesPerson, SalesRegion and SalesOrder are ancestors of SalesOrderLineItem
- SalesPerson > SalesOrder > SalesOrderLineItem
    > SalesPerson is the parent of SalesOrder<br>
    > SalesOrder is the child of SalesPerson<br>
    > SalesOrderLineItem and SalesOrder are descendants of SalesPerson<br> 
    > SalesPerson and SalesOrder are ancestors of SalesOrderLineItem

Entities at the bottom of the hierarchy are referred to as minimal, entities at the top of the hierarchy are referred to as maximal. The FinanceDB OLTP database contains four maximal entities and three minimal entities that are listed in Table 2.

<table style="width:100%">
  <tr>
    <th>Maximal Entities</th>
    <th>Quantity</th>
    <th>Minimal Entities</th>
    <th>Quantity</th>
  </tr>
  <tr>
    <td>Product</td>
    <td>3</td>
    <td>SalesKPI</td>
    <td>1</td>
  </tr>
  <tr>
    <td>Country</td>
    <td>2</td>
    <td>ProductCost</td>
    <td>2</td>
  </tr>
  <tr>
    <td>Segment</td>
    <td>1</td>
    <td>SalesOrderLineItem</td>
    <td>6</td>
  </tr>
  <tr>
    <td>SalesPerson</td>
    <td>3</td>
    <td></td>
    <td></td>
  </tr>
</table>
<center>
    <i><b>Table 2</b> Maximal and Minimal Entities for FinanceDB database</i>
</center><br>

The hierarchical structure can be used to collapse lower-level entities into higher-level entities. Lower-level entities in the FinanceDB relational tables can be collapsed as follows:

- ProductCost into Product
- Promotion into Product
- Country Into Region
- Segment into Region
- SalesKPI into SalesPerson
- SalesOrderLineItem into SalesOrder

The higher-level entity receives the attributes of the collapsed table resulting in transitive dependency redundancy. This is a form of denormalisation that violates Codd's third normal form concerning database schema design.

Additional entities can be created that contain summarised data in the schema design. The new entity stores aggregate attributes selected from the entity source, which is then grouped using a further subset of attributes. In the FinanceDB OLTP database, an entity could be created that summarises product sales by region. The table will total the sales by region, allowing for the average quantity and price to be aggregated for sales in each given region for a given time, using the date dimension. It is important to note that the data cannot be reconstructed, meaning information is lost as a result of the aggregation.

<h3>Dimensional Schema Design</h3>

The initial design consideration was a dimensional model that consisted of a star schema, a single fact table surrounded by the dimension tables. The key of the fact table is formed through the combination of foreign keys created through the relationships with the component entities. Initially, all dimensions were included in the schema to create a model that was future-proofed, with Promotion acting as a classification entity and not a component entity. Consideration was made as to the category type of the Promotion table, and certainly, an argument can be made either way given the ambiguity. However, the model states that should an entity be capable of being classified as either a classification entity or a component entity, then the classification entity will prevail.

Ultimately, a fact constellation table was chosen that was better able to support the sales performance business process and the sales order business process, and the corresponding granularity level required to drill down and provide the detail necessary to answer the business questions.

- <b>DimDate</b> New table generated specifically for the dimensional schema
- <b>DimSalesPerson</b> [SalesYear, SalesKPI] <i>SalesPersonID, FirstName, LastName, Gender, HireDate, DayOfBirth, DaysOfLeave, DaysOfSickLeave</i>
- <b>DimSalesLocation</b> [Country/Segment > Region] <i>RegionID, CountryID, SegmentID, Country, Segment</i>
- <b>DimProduct</b> [Product > Product Cost] <i>ProductID, Product Name, PromotionYear, Discount, ManufacturingPrice, RRP</i>
- <b>FactSalePerformance</b> [SalesKPI > SalesOrder > SalesOrderLineItem]
- <b>FactSaleOrder</b> [SalesOrder > SalesOrderLineItem] <i>SalesOrderID, UnitsSold, SalePrice</i>

Figure 1 shows the initial star schema design. The developed fact constellation schema version 3.2 is shown in Figure 2 in its late-stage iteration. Primary keys have not been enforced on the dimensional schema. The primary keys have been taken from the OLTP database for the dimension tables and act as foreign key references in the fact tables. The reason for this decision is that multiple entries of the same entity are present as a result of the hierarchical structure, collapsing lower classification entities into their component entity.

Two paths have been identified for the DimDate table, the first was to treat this like the other dimension tables and insert the dates directly from the OLTP database. The second option was to research options for a more comprehensive DimDate table that included a finer grain of date related information. Several options were tested, with the final solution offering a suitable trade-off for the data set in FinanceDB, whilst giving consideration to future-proofing of the data warehouse. The date range of this table has been set from the first indicated data entry into FinanceDB and finishes on the last day of 2030. The greater level of detail in the date table allows for increased flexibility for a non- technical user of the business intelligence system.

<h3>Star Schema – Draft Dimensional Model</h3>

<center>
    <img src="/assets/images/dat701-j-SS.png" alt="Star Schema">
</center>

<center>
    <i><b>Figure 1</b> First Iteration – Investigating Draft Star Schema Implementation</i>
</center><br>

<h3>Fact Constellation Schema – Final Dimensional Model</h3>

<center>
    <img src="/assets/images/dat701-j-FCS.png" alt="Fact Constellation Schema">
</center>

<center>
    <i><b>Figure 2</b> Final Iteration – Fact Constellation Schema Implementation</i>
</center><br>

<div style="background-color: #f6f6f6; padding: 1rem; border-radius: 10px 20px;"> 
    <i>References</i>
</div>
<br>
Moody, D. L., & Kortink, M. A. R. (2000). From Enterprise Models to Dimensional Models: A Methodology for Data Warehouse and Data Mart Design. Proceedings of the International Workshop on Design and Management of Data Warehouses (DMDW’2000).

Multidimensional Warehouse (MDW). (n.d.). [Pstopic]. Retrieved October 17, 2021, from [https://docs.oracle.com/cd/E41507_01/epm91pbr3/eng/epm/penw/concept_MultidimensionalWarehouseMDW-9912e0.html](https://docs.oracle.com/cd/E41507_01/epm91pbr3/eng/epm/penw/concept_MultidimensionalWarehouseMDW-9912e0.html)

Surrogate Key in Data Warehouse, What, When and Why. (n.d.). Data Integration Solutions. Retrieved October 17, 2021, from [http://www.disoln.org/2013/11/Surrogate-Key-in-Data-Warehouse-What-When-Why-and-Why-Not.html](http://www.disoln.org/2013/11/Surrogate-Key-in-Data-Warehouse-What-When-Why-and-Why-Not.html)

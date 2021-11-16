---
layout: post
title:  "Journal #Four [DAT701] - Indexing & Views" 
author: Dale Stephenson
categories: [ DAT701, Journal, Enterprise Database Solutions ]
image: assets/images/dat701-j4.jpg
featured: true
hidden: true
---
<i>Indexing & Views</i>

JOURNAL #FOUR [DAT701]

<h2>Indexing & Views</h2>

<h3>Indexes</h3>

To support the views that have been created to answer the business questions, further indexes have been considered in addition to those created in the DDL. These non-clustered indexes are specifically designed to target columns required by the views.

The view relating to the fact table sales performance is performed in zero seconds, meaning that addition non-clustered indexing is not necessary at this stage. However, to support scalability a non-clustered index was created on the table to support this view in recognition of business growth over time. The non-clustered index groups the <i>DateKey</i>, <i>SalesPersonID</i>, and <i>RegionID</i>, and uses <code>include</code> in the statement for the <i>AnnualSalesPrice</i> and <i>AnnualPerformance</i>. The index had no impact on the load time of the select statement. Should the records in the table grow over time, further testing should take place, particularly if the performance decreases.

<center>
    <img src="/assets/images/dat701-j-iv1.png" alt="Indexing created for view 1">
</center>

<center>
<pre><code>
    -- Indexing for View 1

    exec sp_helpindex FactSalePerformance;
    go

    drop index if exists ix_fsp_view1 on FactSalePerformance;
    go

    create nonclustered index ix_fsp_view1
        on FactSalePerformance
            (DateKey asc, SalesPersonID, RegionID) include (AnnualSalesPrice, AnnualPerformance)
        with (data_compression = row);
    go
</code></pre>
</center>

 The view against the fact table sale order is more taxing on the system resources, requiring 20 seconds to complete the query and generating over 1 million records as observed in Figure 20. A non-clustered index was created in addition to the clustered and non-clustered index performed in the DDL, this grouped <i>DateKey</i> and <i>SalesOrderID</i>, and was tested with several columns in the index and utilising <code>include</code> for the columns. The results were less than impressive, with most attempts producing the same 14-second result, or increasing the load time to as much as 16-seconds.

<center>
<pre><code>
    -- Indexing for View 2

    exec sp_helpindex FactSaleOrder;
    go

    drop index if exists ix_fso_view2 on FactSaleOrder;
    go

    create nonclustered index ix_fso_view2
        on FactSaleOrder
            (DateKey, SalesOrderID) -- include (TotalSalesPrice, TotalCost, TotalRRP)
        with (data_compression = row);;
    go
</code></pre>
</center>

<center>
    <i><b>Figure 19</b> Indexing created for view 2</i>
</center>

<center>
    <img src="/assets/images/dat701-j-iv1.png" alt="Query completion time">
</center>

<center>
    <i><b>Figure 20</b> Query completion time</i>
</center>

The results experienced in this test were not unexpected, given that the index strategy deployed in the DDL is sufficient given the size of the data set. The index strategy that has been deployed surrounds the creation of clustered indexes on the single-column primary keys in the dimension tables, which work in conjunction with the table partitioning meaning that given the tables are not considered very large by data warehousing standards, > 100k rows or even large, ~100k rows, a performance improvement has not been realised.

The fact tables can be classified as very large tables, therefore the strategy follows the recognised practice that includes the creation of a clustered index on the <i>DateKey</i>, and a non-clustered index on the relationship keys that act as foreign keys to the dimension tables, these have previously been defined in the DDL. Based on the testing of these earlier indexes, in conjunction with the table partitioning on the <i>DateKey</i>, indications are that these are sufficient to produce the query run times currently experienced.

<h3>Views</h3>

The two views created in the data warehouse have been specifically chosen to produce different information relating to separate business processes, the first view relating to sales performance and the second to sales orders. The view relating to sales orders contains all the necessary information to produce a dashboard in Power BI that satisfies the query produced in section C of Assignment 1.

These views will be used to produce data visualisations by the data analyst in Power BI. By restricting the data available to these views, the data warehouse developer can provide a greater level of security by restricting access to the other data contained in the tables.

<center>
<pre><code>
    -- >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

    -- Reporting Views

    -- Reporting View 1 | Total Yearly KPI by Sales Rep, Country, & Segment

    drop view Sales_Performance;
    go

    create view Sales_Performance as
        select distinct
            YearCalendar,
            concat(FirstName, ' ', LastName) as SalesRepresentative,
            CountryName,
            SegmentName,
            TotalAnnualKPI,
            AnnualSalesPrice,
            AnnualPerformance
        from FactSalePerformance fsp
            inner join DimDate dd on fsp.DateKey = dd.DateKey
            inner join DimSalesPerson sp on fsp.SalesPersonID = sp.SalesPersonID
            inner join DimSalesLocation sl on fsp.RegionID = sl.RegionID;
    go

    select * from Sales_Performance
    order by
        YearCalendar,
        SalesRepresentative desc,
        CountryName desc,
        SegmentName desc;
</code></pre>
</center>
<center>
    <i><b>Figure 21</b> View 1 for total yearly KPI by Sales Representative, Country, and Segment on Fact Sale Performance</i>
</center>

<center>
<pre><code>
    -- Reporting View 2 | Yearly Sales Orders by Sales Representative

    drop view Sales_Orders;
    go

    create view Sales_Orders as
        select
            year(FullDate) as Year,
            MonthNameOfYear,
            MonthNumberOfYear,
            YearCalendar,
            SalesOrderID,
            concat(FirstName, ' ', LastName) as SalesRepresentative,
            TotalSalesPrice,
            TotalCost,
            GrossProfit,
            TotalRRP,
            TotalItems,
            Margin,
            PercentageDiscount
        from FactSaleOrder fso
            inner join DimDate dd on fso.DateKey = dd.DateKey
            inner join DimSalesPerson sp on fso.SalesPersonID = sp.SalesPersonID
            inner join DimSalesLocation sl on fso.RegionID = sl.RegionID;

    go

    select * from Sales_Orders
    order by
        Year,
        SalesOrderID,
        SalesRepresentative;
</code></pre>
</center>
<center>
    <i><b>Figure 22</b> View 2 for yearly sales orders on Fact Sale Order</i>
</center>

The execution plan was considered against both fact table views throughout the development process. A trade-off was necessary between the need to perform the aggregations across the tables in the OLTP database and the level of granularity required in the fact tables, with the desire to ensure optimum performance. The higher cost areas of the queries were expected, being with the aggregations and the inner joins. The queries and the common table expression have been designed to mitigate the effect on performance and run times.

<div style="background-color: #f6f6f6; padding: 1rem; border-radius: 10px 20px;"> 
    <i>References</i>
</div>
<br>

Systems, C. (n.d.). SQL Server: Data Warehouse Indexing Strategy. Catapult Systems. Retrieved November 6, 2021, from [https://www.catapultsystems.com/blogs/sql-server-data-warehouse-indexing-strategy/](https://www.catapultsystems.com/blogs/sql-server-data-warehouse-indexing-strategy/)


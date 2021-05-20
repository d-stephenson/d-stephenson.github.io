---
layout: post
title:  "Journal #Eight [DAT602] - Control Flow" 
author: Dale Stephenson
categories: [ DAT602, Journal, Database Application Development ]
image: assets/images/DAT602-J8.jpeg
featured: true
hidden: true
---
<i>Control Flow</i>

JOURNAL #EIGHT [DAT602]

<h2>Control Flow</h2>

<h3>Control Flow Functions</h3>
 
There are several functions available in SQL that allow logic to be added to queries, this can be done without using the procedural code. Control flow functions return a value for each row that is processed, the values returned are a result of an evaluated comparison. Control flow functions can be utilised in the following clauses:
 
- SELECT
- WHERE
- ORDER BY
- GROUP BY
 
Control flow functions allow MySQL uses to add IF - THEN - ELSE logic by utilising the following control flow functions:
 
<h4>CASE Operator</h4>
 
In a THEN branch, the function returns the corresponding result if the condition in the WHEN branch is satisfied, if it is not satisfied, the result in the ELSE branch is returned.
 
<b>CASE example 1:</b>

<code> 
SELECT ProductID, StockAmount,<br>
CASE<br>
    WHEN StockAmount > 10 THEN "Stock is sufficient"<br>
    WHEN StockAmount = 10 THEN "Re-order stock"<br>
    ELSE "Stock is very low, urgent re-order"<br>
END<br>
FROM tblStockDetails;<br>
</code>
 
<b>CASE example 2:</b>

<code> 
SELECT ManufacturerID, Town, Postcode<br>
FROM tblManufacturer<br>
ORDER BY<br>
(CASE<br>
    WHEN Town IS NULL THEN Postcode<br>
    ELSE Town<br>
END); // returns ManufacturerID ordered by Town unless Town is NULL in which case ordered by Postcode<br>
</code>
 
<h4>IF/ELSE Construct</h4>
 
A value will be returned as a result of a given condition.
 
<b>IF example:</b>
 
<code>
SELECT ProductID, StockAmount,<br>
IF(StockAmount > 10, 'More', 'Less')<br>
FROM tblStockDetails; // returns 'More' if the condition is true and 'Less' if the condition is 'False'<br>
</code>
 
<h4>IFNULL</h4>
 
The first argument will be returned if it is not NULL, if it is NULL then the second argument is returned.
 
<b>IFNULL example:</b>
 
SELECT IFNULL(NULL, 10); <i>returns 10</i><br>
<i>Please note the above code is not indented correctly for the purpose of this journal</i>
 
<h4>NULLIF</h4>
 
Returns NULL if the first argument equals the second argument, if it does not equal the second argument then it will return the first argument.
 
<b>NULLIF example:</b>

<code> 
SELECT NULLIF(25, 25); // returns NULL<br>
SELECT NULLIF(15, 25); // returns 15<br>
SELECT NULLIF(15, 5); // returns 15<br>
</code>

<i>References</i>
 
MySQL Control Flow Functions Overview. (n.d.). MySQL Tutorial. Retrieved April 22, 2021, from [https://www.mysqltutorial.org/mysql-control-flow-functions/](https://www.mysqltutorial.org/mysql-control-flow-functions/)
 
Use MySQL Control Flow Functions—CASE, IF, IFNULL, and NULLIF. (n.d.). Retrieved April 22, 2021, from [https://www.geeksengine.com/database/single-row-functions/control-flow-functions.php](https://www.geeksengine.com/database/single-row-functions/control-flow-functions.php)
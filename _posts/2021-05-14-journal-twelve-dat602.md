---
layout: post
title:  "Journal #Twelve [DAT602] - Language Integrated Query (LINQ)" 
author: Dale Stephenson
categories: [ DAT602, Journal, Database Application Development ]
image: assets/images/DAT602-J12.jpeg
featured: true
hidden: true
---
<i>Language Integrated Query (LINQ)</i>

JOURNAL #TWELVE [DAT602]

<h2>Language Integrated Query (LINQ) (C#)</h2>

Language Integrated Query (LINQ) is being deployed in the Visual Studio programming environment utilising C# to access the game database, which calls queries using structured query language (SQL).
 
Deploying LINQ to SQL maps the data model of the relational database to an object model, which can be expressed in the programming language. When the Visual Studio application is run, LINQ to SQL translates the language-integrated queries into SQL and sends them from the object model to the database, so they can be executed. The database runs the SQL and returns an output, LINQ to SQL translates the output to objects that then work in the programming language environment.
 
In Visual Studio, developers often use the Object Relational Designer, this allows for the implementation of the features of LINQ to SQL within the user interface.
 
<h3>Query Expressions</h3>
 
Query expressions are the most visible element of the language integration that forms LINQ. These are written in a declarative query syntax that can be used to perform filtering, ordering, and grouping operations on data held within a database. Because of the basic query expression patterns used in the SQL database, only minimal coding is required.
 
The project requirements state that the LINQ queries be written in C# in the Visual Studio environment, which is used with Microsoft SQL Server but can also be applied to third party implementations such as the MySQL InnoDB database used for the game development.
 
<h3>Features of LINQ query expression</h3>
 
- Used to query and manipulate data, such as retrieving data and producing an eXtensible Markup Language (XML) stream as an output
- Easy to develop because it shares familiar C# constructs
- The query is only executed when it is iterated over, for example, with a <code>foreach</code> loop statement 
- When using a <code>foreach</code> loop, the query executes on the data source to return the result
- In most instances, query syntax is more readable and concise, so it is easily understood by other developers
- No requirement for developers to learn a new query language for each data source type or format
- Reduced code when compared with traditional approaches
- Objects are type-checked at compile time
- Data can be retrieved in different shapes 
 
<h3>LINQ Query Syntax</h3>
 
LINQ is a powerful tool used by developers to query different data sources utilising either C# or Visual Basic. LINQ query can be written in two ways, to IEnumerable collection or IQueryable data sources.
 
<b>1. Query Syntax or Query Expressions Syntax:</b>
 
Query syntax uses similar construction as the SQL used against the database, it starts with the <code>FROM</code> keyword and concludes with the <code>SELECT</code> keyword. Query syntax is shown in the following example:
 
<code>
// Example LINQ query syntax C#

    var result = from p in newList
        where p.Includes("Players")
        select p;
</code>
 
<b>2. Method Syntax or Method Extension Syntax:</b>
 
Method syntax utilises extension methods in the static class, Enumerable or Queryable. This is a similar to the extension method call of any class in the program, converting the query syntax into method syntax at the time of compiling. Method syntax is shown in the following example:
 
<code>
// Example LINQ method syntax C#

    var result = newList.Where(p => p.Includes("Players"));
</code>

<i>References</i>

BillWagner. (n.d.-a). Data Transformations with LINQ (C#). Retrieved May 20, 2021, from [https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/data-transformations-with-linq](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/data-transformations-with-linq)

BillWagner. (n.d.-b). Language-Integrated Query (LINQ) (C#). Retrieved May 20, 2021, from [https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/)

LINQ Method Syntax. (n.d.). Retrieved May 20, 2021, from [https://www.tutorialsteacher.com/linq/linq-method-syntax](https://www.tutorialsteacher.com/linq/linq-method-syntax)

LINQ Tutorials from Basics to Advanced. (n.d.). Retrieved May 20, 2021, from [https://www.tutorialsteacher.com/linq/linq-tutorials](https://www.tutorialsteacher.com/linq/linq-tutorials)

stevestein. (n.d.). LINQ to SQL - ADO.NET. Retrieved May 20, 2021, from [https://docs.microsoft.com/en-us/dotnet/framework/data/adonet/sql/linq/](https://docs.microsoft.com/en-us/dotnet/framework/data/adonet/sql/linq/)

What is LINQ. (n.d.). Retrieved May 20, 2021, from [https://www.tutorialsteacher.com/linq/what-is-linq](https://www.tutorialsteacher.com/linq/what-is-linq)

What is XML. (n.d.). Retrieved May 20, 2021, from [https://www.w3schools.com/whatis/whatis_xml.asp](https://www.w3schools.com/whatis/whatis_xml.asp)

Why LINQ? (n.d.). Retrieved May 20, 2021, from [https://www.tutorialsteacher.com/linq/why-linq](https://www.tutorialsteacher.com/linq/why-linq)

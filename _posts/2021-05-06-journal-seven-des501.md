---
layout: post
title:  "Journal #Seven [DES501] - Web Design: HTML, CCS, Grids" 
author: Dale Stephenson
categories: [ DES501, Journal, Design and Development Concepts ]
image: assets/images/DES501-J7.jpeg
featured: true
hidden: true
---
<i>Web Design: HTML, CCS, Grids</i>

JOURNAL #SEVEN [DES501]

<h2>Web Design: HTML, CCS, Grids</h2>
 
The following HTML and CSS form part of the exercise projects available on [Dash](https://dash.generalassemb.ly/projects). Project 1 and 2 have been completed and screenshots are located in this journal.
 
<h3>HTML</h3>
 
<table style="width:100%">
  <tr>
    <th>HTML</th>
    <th>Description</th>
  </tr>
  <tr valign="top">
    <td><code>< !DOCTYPE html ></code></td>
    <td>This declaration provides information to the browser about the<br>
     document type.</td>
  </tr>
  <tr valign="top">
    <td><code>< head ></code></td>
    <td>This is a container element for data about the document, this<br>
     metadata is not displayed on the web page.</td>
  </tr>
  <tr valign="top">
    <td><code>< title ></code></td>
    <td>This element contains the title of the web page and is displayed<br>
     in the title bar of the web browser.</td>
  </tr>
  <tr valign="top">
    <td><code>< style ></code></td>
    <td>This is a tag that is used for the style information (CSS) for<br>
     the web page content in the body.</td>
  </tr>
  <tr valign="top">
    <td><code>< body ></code></td>
    <td>This is used to define the body of the document, it contains<br>
     all the visible web page contents such as images, paragraphs, tables,<br>
      links, etc.</td>
  </tr>
  <tr valign="top">
    <td><code>< h1 ></code></td>
    <td>Defines a large heading on the web page, extends to < h7 >.</td>
  </tr>
  <tr valign="top">
    <td><code>< p ></code></td>
    <td>Defines a paragraph on the web page. </td>
  </tr>
  <tr valign="top">
    <td><code>< article ></code></td>
    <td>Defines self-contained content that is independent from other<br>
     content in the body.</td>
  </tr>
  <tr valign="top">
    <td><code>< img src =" " ></code></td>
    <td>This allows for a image to be embedded on a web page.</td>
  </tr>
  <tr valign="top">
    <td><code>< input type ></code></td>
    <td>Used to define an input field, these can be numerous types including<br>
     "button", "text", "email", "radio", etc.</td>
  </tr>
  <tr valign="top">
    <td><code>< placeholder ></code></td>
    <td>Used to give a hint as to the expected value of an input being<br>
     passed into a field.</td>
  </tr>
  <tr valign="top">
    <td><code>< link href=" " rel=" " ></code></td>
    <td>Provides a link that imports a style sheet to the html document.</td>
  </tr>
  <tr valign="top">
    <td><code>< button ></code></td>
    <td>Creates a visible button on the web page. </td>
  </tr>
  <tr valign="top">
    <td><code>< ul ></code></td>
    <td>Creates an unordered, bulleted list.</td>
  </tr>
  <tr valign="top">
    <td><code>< li ></code></td>
    <td>Used in conjunction with the ul tag to form the unordered list.</td>
  </tr></table>
<br>
 
<h3>CSS Properties</h3>
 
<table style="width:100%">
  <tr valign="top">
    <th>CSS</th>
    <th>Description</th>
  </tr>
  <tr valign="top">
    <td><code>text-align: center;</code></td>
    <td>Sets the alignment of text on the horizontal axis, <br>
    can be right, left, justified or centered.</td>
  </tr>
  <tr valign="top">
    <td><code>background-color: white;</code></td>
    <td>This property that sets the background colour of an element, <br>
    including border and padding, but excludes the margin.</td>
  </tr>
  <tr valign="top">
    <td><code>background-size: cover;</code></td>
    <td>This property is used to specify the size of background images.</td>
  </tr>
  <tr valign="top">
    <td><code>color: black;</code></td>
    <td>This is used to specific predefined colours, that can be described <br>
    in this example or RGB, HSL, RGBA, HEX, etc.</td>
  </tr>
  <tr valign="top">
    <td><code>font-family: helvetica;</code></td>
    <td> The property is used to specify the font within an element, several <br>
    font names can be included and used as a fallback if the browser doesn't <br>
    support the first font.</td>
  </tr>
  <tr valign="top">
    <td><code>padding: 100px;</code></td>
    <td>The padding property is used to pad the space between the content and<br>
     its border. This property has four values for top, right, bottom, left, <br>
     in that order.</td>
  </tr>
  <tr valign="top">
    <td><code>display: block;</code></td>
    <td>This property is used to specify an elements display property.</td>
  </tr>
  <tr valign="top">
    <td><code>font-size: 40px;</code></td>
    <td>Used to set the size of the text, this should not be used to make <br>
    adjustments to text size to make it headings.</td>
  </tr>
  <tr valign="top">
    <td><code>background: url(" ");</code></td>
    <td>Sets an image as the web page background.</td>
  </tr>
  <tr valign="top">
    <td><code>margin: 40px 0px 0px 0px;</code></td>
    <td>This property is used to set an elements margins, the four values<br>
     include top, right, bottom, and left, in that order.</td>
  </tr>
  <tr valign="top">
    <td><code>border: 7px solid white;</code></td>
    <td>This is used to specify a border width and colour.</td>
  </tr>
  <tr valign="top">
    <td><code>border-radius: 20px;</code></td>
    <td>This property is used to define the radius of the corners of an <br>
    element.</td>
  </tr>
  <tr valign="top">
    <td><code>max-width: 500px;</code></td>
    <td>This allows the element to support smaller browser windows, it is<br>
    useful to make the element compatible with smaller devices.</td>
  </tr>
  <tr valign="top">
    <td><code>@media</code></td>
    <td>This is a rule in CSS that is used in media queries that allows different <br>
    styles to apply to different media types or devices. This is particularly<br>
    useful to deliver tailored style sheets for responsive web pages.</td>
  </tr>
  </table>
  <br>
 
<h3>CSS Grids</h3>
 
CSS grid layouts are used to create two-dimensional grids to format web pages into their major areas and smaller interfaces.
 
Grids are made up of horizontal and vertical intersecting lines that create columns and rows on a web page. This makes it easier for web designers to design web pages without having to manage floats and the positioning of elements that make up the page content.
 
Grids in CCS have various features such as:
 
<b>Fixed & flexible track sizes:</b> Creation of grids with track sizes that<br> 
are fixed, pixels can be used to define the layout. Flexible sizes can be<br>
 created using percentages or the "fr" unit.
 
<b>Item placement:</b> Items can be placed accurately into their location.
 
<b>Content held in additional tracks:</b> Ability to add rows and columns to<br>
 add other features such as columns that fit inside a container.
 
<b>Alignment control:</b> Ability to control the alignment of content after<br>
 it is placed inside a grid.
 
<b>Overlapping content control:</b> Numerous items can be placed in a grid and<br>
 they can partially overlap one another, the layering can be controlled with<br>
  the z-index property.<br>
 
<h3>Activity Screenshots</h3>
 
The following are screenshots of the HTML and CSS activities in Dash:<br>
 
<b>Project 1: Build a personal website</b><br>

<center><img src="/assets/images/DES501_PRJ1.png" alt="HTML and CSS Dash project 1"></center><br>
 
<b>Project 2: Build a responsive blog theme</b><br>

<center><img src="/assets/images/DES501_PRJ2.png" alt="HTML and CSS Dash project 2"></center><br>
 
<i>References</i><br>
 
Basic Concepts of grid layout - CSS: Cascading Style Sheets - MDN. (n.d.). Retrieved May 6, 2021, from [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Basic_Concepts_of_Grid_Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Basic_Concepts_of_Grid_Layout)<br>
 
Learn to code HTML, CSS, and JavaScript with Dash. (n.d.). Retrieved May 6, 2021, from [https://dash.generalassemb.ly/projects](https://dash.generalassemb.ly/projects)<br>
 
W3Schools Online Web Tutorials. (n.d.). Retrieved May 6, 2021, from [https://www.w3schools.com/default.asp](https://www.w3schools.com/default.asp)
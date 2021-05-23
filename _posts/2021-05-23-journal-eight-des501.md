---
layout: post
title:  "Journal #Eight [DES501] - CSS Length Units" 
author: Dale Stephenson
categories: [ DES01, Journal, Design and Development Concepts ]
image: assets/images/DES501-J8.jpeg
featured: true
hidden: true
---
<i>CSS Length Units</i>

JOURNAL #Eight [DES501]

<h2>CSS Length Units</h2>
 
There are several ways to express lengths in CSS, lengths are important due to the numerous properties that take length values including <code>width</code>, <code>margin</code> and <code>padding</code>. The units used for expressing lengths are split into two distinct types, <i>absolute</i> and <i>relative</i>. Length units are declared as a number followed by the unit type, several of the types available in CSS allow the for input of negative lengths.
 
The length units available to web designers are described as follows:
 
<h3>Absolute Lengths</h3>
 
Absolute lengths are fixed units and are always expressed as the size that is defined, because of this they are not recommended for screen display due to the varying screen sizes from desktops to laptops, tablets and phones. They are best used where the output medium is known such as print layouts, which is where <i>pt</i> and <i>pc</i> units originate.
 
There are instances where <i>px</i> can be useful, such as cases where text must be aligned next to images, or if the text needs to be very sharp, 1px will guarantee that the text looks sharp on-screen.
 
<table style="width:100%">
  <tr>
    <th>Unit</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td>cm</td>
    <td>centimeter length</td>
    <td><code>line-height: 1cm;</code></td>
  </tr>
  <tr>
    <td>mm</td>
    <td>millimeter length</td>
    <td><code>font-size: 5mm;</code></td>
  </tr>
    <tr>
    <td>in</td>
    <td>inch length <i>1in = 96px</i></td>
    <td><code>line-height: 0.5in;</code></td>
  </tr>
    <tr>
    <td>px</td>
    <td>pixels <i>1px = 1/96th of 1in</i></td>
    <td><code>font-size: 15px;</code></td>
  </tr>
    <tr>
    <td>pt</td>
    <td>points <i>1pt = 1/72th of 1in</i></td>
    <td><code>font-size: 15pt;</code></td>
  </tr>
    <tr>
    <td>pc</td>
    <td>picas <i>1pc = 12pt</i></td>
    <td><code>h1 {font-size: 4.5pc;}</code></td>
  </tr>
 </table>
 <br>
<h3>Relative Lengths</h3>
 
Relative lengths are relative to other length properties, they are unit specifications that scale between various rendering mediums, which makes them better for websites that are accessed on a variety of screen sizes.
 
Font sizes are best when using the <i>em</i> length unit, to set the font size to the default size of the screen. This means that the size of the font sits comfortably on the device screen, for example <code>H2 {font-size: 3em}</code> is 3 times the size of the defined font of the <code>body</code> text.
 
<table style="width:100%">
  <tr>
    <th>Unit</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr valign="top" padding="5px" background="#000000">
    <td>em</td>
    <td>Length unit that is relative to the elements<br> font size, so 5em is 5 times the current font size</td>
    <td><code>
        div {<br>
        font-size: 30px;<br>
        border: 1px solid black;<br>
        }<br>
        <br>
        span {<br>
        font-size: 0.5em;<br>
        }
</code></td>
  </tr>
  <tr valign="top" padding="5px">
    <td>ex</td>
    <td>Length unit that is relative to the x-height of<br> the current font size, this is rarely used</td>
    <td><code>
        div {<br>
        font-size: 30px;<br>
        border: 1px solid black;<br>
        }<br>
        <br>
        span {<br>
        font-size: 1ex;<br>
        }
</code></td>
  </tr>
  <tr valign="top" padding="5px">
    <td>ch</td>
    <td>Length unit that is relative to the width of<br> the "0"</td>
    <td><code>
        body {<br>
        font-size:16px;<br>
        }<br>
        <br>
        div {<br>
        font-size: 3ch;<br>
        border: 1px solid black;<br>
        }<br>
</code></td>
  </tr>
  <tr valign="top" padding="5px">
    <td>rem</td>
    <td>Length unit that is relative to the font-size of<br> the root element</td>
    <td><code>
        html {<br>
        font-size:16px;<br>
        }<br>
        <br>
        div {<br>
        font-size: 3rem;<br>
        border: 1px solid black;<br>
        }
</code></td>
  </tr>
  <tr valign="top" padding="5px">
    <td>vw</td>
    <td>Length unit that is relative to 1% of the <br>viewport width</td>
    <td><code>
        h1 {<br>
        font-size: 20vw;<br>
        }
</code></td>
  </tr>
  <tr valign="top" padding="5px">
    <td>vh</td>
    <td>Length unit that is relative to 1% of the <br>viewport height</td>
    <td><code>
        h1 {<br>
        font-size: 20vh;<br>
        }
</code></td>
  </tr>
  <tr valign="top" padding="5px">
    <td>vmin</td>
    <td>Length unit that is relative to 1% of the smaller<br> dimension of the viewport</td>
    <td><code>
        h1 {<br>
        font-size: 15vmin;<br>
        }
</code></td>
  </tr>
  <tr valign="top" padding="5px">
    <td>vmax</td>
    <td>Length unit that is relative to 1% of the larger<br> dimension of the viewport</td>
    <td><code>
        h1 {<br>
        font-size: 15vmax;<br>
        }
</code></td>
  </tr>
  <tr valign="top" padding="5px">
    <td>%</td>
    <td>Length unit that is relative to the parent<br> element</td>
    <td><code>
        body {<br>
        font-size:16px;<br>
        }<br>
        <br>
        div {<br>
        font-size: 150%;<br>
        border: 1px solid black;<br>
        }
</code></td>
  </tr>
 </table>
 
<i>References</i>
 
CSS: em, px, pt, cm, in…. (n.d.). Retrieved May 23, 2021, from [https://www.w3.org/Style/Examples/007/units.en.html](https://www.w3.org/Style/Examples/007/units.en.html)
 
CSS Units. (n.d.). Retrieved May 23, 2021, from [https://www.w3schools.com/CSSref/css_units.asp](https://www.w3schools.com/CSSref/css_units.asp)
---
layout: post
title:      "All About CSS"
date:       2021-01-17 16:56:07 -0500
permalink:  all_about_css
---


In the past five months I've learned how to code in a variety of different languages through Flatiron, but one very important language was never in the forefront of our discussions... CSS. As one of the big three languages that make up the frontend developer's toolkit, I took it upon myself to do an intro of CSS that can hopefully help other prospective coders start their design-oriented journey. I like to think of CSS as the clothing that the website puts on. It's not required to get a website up and running, but you'll get a lot of weird stares without it. Now let's jump in and get started!

CSS works hand-in-hand with HTML, as it targets specific elements to set their styling rules. At it's core, CSS is a rule-based language, as it specifies rules for how certain parts of the application will look. Syntax-wise, CSS uses a selector and then curly braces with its rules placed inside. Here is a basic example of CSS structure:

```
p {
color: blue;
font-size: 4em;
font-style: italic;
}
```

In this example, the selector is "p", denoting the p element in HTML. A selector selects the HTML element(s) we are targeting for styling. The curly braces contain declarations that take the form of property-value pairs. In the previous example, "color" is the property of the element being changed, and "blue" is the value for that property being set. This is the basic format for all CSS styles, normally found in CSS stylesheets that get linked to the application. While there are three ways to add CSS styling, linking CSS in the head of the document is the most usual way, as seen below:

`<link rel="stylesheet" href="styles.css">`

One of the great things about CSS is the array of selectors available to us. This allows us to target any element that we need. The use of classes and ids added to HTML elements are used for CSS targeting. Below is a handy table detailing some oft used selectors:

| Selector | Explanation |
| ---------  | ------------- |
| li | selects all li elements |
| li.special | selects all li elements with class "special" |
| li#first | selects li element with id "first" |
| ul li | selects li elements that are nested inside a ul element |
| h4 + p | targets p elements that are directly after an h4 element |
| a:visited | targets links that have been visited |

You can find even more selectors [here](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#selectors). You can also combine selectors to narrow down your target list. An example of this would be `h1 + ol li#first`, which reading right to left would mean, "target li element with an id of 'first' that is inside an ol that is directly after an h1 element". 

Now that we understand the basics of CSS, infinite possibilities await for you to explore! Advanced selectors, flexbox grids, animations, and other CSS tools we didn't cover are just a simple google search away from expanding your programming abilities tenfold. CSS is a wonderful tool to create unique web apps and customize pages exactly as you want them. To learn more, [MDN's CSS page](https://developer.mozilla.org/en-US/docs/Learn/CSS) is a great place to start. Now get out there and start designing!

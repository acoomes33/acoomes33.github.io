---
layout: post
title:      "A Drink a Day Keeps the Debugging at Bay"
date:       2020-11-21 22:46:23 +0000
permalink:  a_drink_a_day_keeps_the_debugging_at_bay
---


Ah Javascript, what an interesting few weeks it's been learning the ins and outs of the oft used language. Besides being an integral part of front-end programming along with HTML and CSS, it is also by far the most complex of the three. While there are parallels between Ruby and JS along with many other similarly structured languages, Javascript has a lot of unique attributes that has made it both invigorating and frustrating to fully grasp. Building my Mixaholic drinking app helped me work on some of the special cases that arise when working with JS, and allowed me to create features that I had been waiting to add in other previous projects.

While dealing with Javascript and a backend Rails API, the three pillars that are DOM manipulation, server communication, and recognizing Javascript events came together to create my app. Along the way, things like scope and context led to some long debugging episodes. One particular bug that came up was the famous lost context bug, where everbody's favorite keyword, `this` led to some peculiar outcomes. In one part of my app, I wanted to filter the created drinks by the most recently created ones, in which I used a "click" event listener in order to re-render my drinks on the page. In order to do this however, I needed to use my `renderDrinks()` function that required me to use the `this` keyword to retrieve my App instance. But in order to get the right context in my` newestDrinksList()` function, I needed to find a way to reach the "lost context". This is where creating it as an arrow function came in handy, as they do not create their own context, so I was able to pass in my App instance as `this` without a hitch. So my eventListener ended up looking like this, 

`dateNewestButton.addEventListener("click", this.newestDrinksList);`.

I was then able to call `this.renderDrinks()` at the end of my function and get the desired outcome.

Another problem that arose was the use of nested attributes when creating a new drink. The trick is the use this line of code in the rails Drink model, as well as restructuring the data being sent back as "ingredients_attributes" rather than just "ingredients", 

`accepts_nested_attributes_for :ingredients, :allow_destroy => true, reject_if: proc {|ing| ing['description'].blank?}` 

These two tricks helped to properly set up my connection between my backend and frontend. I also used a handy dynamic "Add Ingredient" button to add an ingredient input if more ingredients were needed. This functionality is something I would've liked to have implemented in past projects, and now I am able to! Wow, JS rocks!

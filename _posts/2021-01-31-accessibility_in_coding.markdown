---
layout: post
title:      "Accessibility in Coding"
date:       2021-01-31 19:32:09 -0500
permalink:  accessibility_in_coding
---


People across the world are accessing the web online, with billions of web sessions everyday. Inside these dizzying amounts of online interactions, there are many different ways that the internet is being accessed. Of course we can look at the difference between mobile and desktop browsing and how to build out platforms that work seamlessly with both, but there are other, more niche and uncommon ways the internet is being accessed. We as developers have to take these possibilities into consideration when designing apps and websites that billions of people use daily. Groups like the deaf community and blind community have to be taken into consideration in order to meet the needs that they require to properly use the web. A multitude of other disabilities exist as well, and as programmers it is our duty to make sure that everybody is included in the fun. We'll talk about some of the ways we can create accessibility for these communities below.

Some basic considerations are listed below: 

* Associate labels to form element using the "for" attribute set to the id of the element
* Include "alt" attribute for every image, especially important for those with visual impairments
* Indicate primary language using the "lang" attribute
* Use HTML mark-ups to convery meaning and structure (ex. `nav`, `aside` elements, "role" attributes)
* Help users avoid and correct mistakes through alerts, error messages, and detailed instructions
* Write responsive code adaptive to different technologies ( e.g. handle different zoom states and viewport styles)
* Ensure interactive elements are keyboard accessible (keyboard navigation vs. mouse)


As you can see, there are a dizzying array of ways to access the web. Developers need to take these edge cases into account when creating interactive apps and webpages so everybody can access it if they want.


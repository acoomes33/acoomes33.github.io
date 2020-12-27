---
layout: post
title:      "Functional Programming, Explained"
date:       2020-12-27 23:42:29 +0000
permalink:  functional_programming_explained
---


As we worked through our intensive course at Flatiron, we learned about many cutting-edge industry practices and technologies. When it came to our coding structures and overall organization, Object-Oriented Programming was the overwhelming majority of what we used in our projects. Centered around the idea of "objects" and the use of classes, we were able to create fully functional front and back-end projects with clean, efficient, and organized code. However, Functional Programming is being used in the tech industry more and more, with its easy-to-understand and side-effect reducing benefits becoming huge boons to developers.

Functional Programming at its root uses pure functions, immutability, and avoids shared state and side-effects in order to keep functions as reusable as possible. Pure functions are functions that will always return the same result when the same exact arguments are used, without any side effects to the program itself or its data. They are analogous to mathematical functions, in the way that y = x + 10 will always return 15 for y if x=5. Now, of course you can't compose a full program without some impure functions like fetching data or receiving user input, but a vast majority can be pure and thus limit bugs in your code.

Some definitions below might be helpful in understanding FP and the benefits of using this paradigm:

* Immutability - Cannot be changed after creation. An immutable object is an object that cannot be modified.
* Side Effects - Any application state change observable outside the function that isn't the return value (e.g. modifying a global variable, writing to the screen, etc.)
* Shared State - Any variable, object, or memory space that is shared in a certain scope, like a global scope.

Lets compare an example of a pure function versus an impure function using JavaScript:

```
// Pure Function

function divide(a,b) {
    return a / b;
  }
	
	// Impure Function
	
	function doSomething(a) {
	console.log('creating a side effect', a)
	}
```

The first function fits the criteria as it contains no side effects, as well as returning the same result when given the same arguments. Calling divide(1,2) will always return 1/2 no matter what. The same cannot be said for the second function. Firstly, it doesn't contain a return value, which is a tell-tale sign of an impure function. If a function doesn't return anything, it must either be causing side effects in the program, or doing nothing, which is not ideal. In this case, it contains a side effect of logging something on the console. Now that we have a clearer picture of what functional programming is, here are some tips in using FP in JavaScript.

* Object.freeze allows for immutability (e.g. `const ob = Object.freeze({ foo: "bar"})`)
* Use non-destructive methods like .concat, .slice, and .filter rather than destructive methods like .splice, .pop, and .push

With its easy-to-use and debugging advantages, it's no wonder why Functional Programming is increasingly being used by companies as the go-to paradigm for structuring their code. It can be a little dense when coming across the concept for the first time, with its mathematical inclinations and complex components, but it can open up vast possibilities for developers once a little experience is added and a more complete understanding is reached. Hopefully this article has cleared up some questions and created some intrigue into the topic, as it has broad industry use in the present and in the future.







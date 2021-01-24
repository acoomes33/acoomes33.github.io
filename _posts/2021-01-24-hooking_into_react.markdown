---
layout: post
title:      "Hooking Into React"
date:       2021-01-24 22:01:31 +0000
permalink:  hooking_into_react
---


With every iteration of a technology, innovation and streamlined processes are created. React is no exception to this rule. One big addition came in React 16.8, the use of **hooks**. Hooks were implemented to solve seemingly unconnected problems caused by the use of classes in react. Hooks allow you to create entire applications with functional components, without the use of state constructors, componentDidMount, and other lifecycle methods available to class components. They are also backwards-compatible, which is very useful to programmers that are wondering if they should update previously written code or not. Before hooks, it was hard to reuse stateful logic between components, but with hoos you can extract stateful logic from a component so it can be reused. In short, it helps make less complex and more understandable React components.

Now, how might we set our state in a "stateless" functional component you may ask. Well, here is where the **useState** hook comes into play. Below, you can see how this hook is used: 

```
function Example() {
    const [likes, setLikes] = useState(0);
		const [shares, setShares] = useState(0);
		
		return (
		  <div>
		    <p> This post has {likes} likes</p>
				<button onClick={() => setLikes(likes + 1)}> Like </button>
			</div>
			);
		}
```

If we look at the second line, you can see how useState is implemented. The useState hook returns a pair, the current state value (likes) and a function that updates the state (setLikes). This takes the place of state and seState in class components. The argument for useState is the initial state, which we have set to 0. As you can see, you can also declare multiple state variables by using the useState hook as many times as you need. Now, you may be wondering how you can replace lifecycle methods without using classes. Well, there is a hook for that job too!

One of the great things about hooks is that they can DRY up your code and bundle linked behaviors together. You can see this in the **useEffect** hook. This hook takes the place of componentDidMount, componentDidUpdate, and componentWillUnmount all in one! Here is a comparison below using a pseudocoded setInterval fetch request:

```
    componentDidMount() {
		    this.getWeather = setInterval( fetchWeather, 1000)
				}
		
		componentWillUnmount() {
		   clearInterval(this.getWeather)
			 }
```

```
   useEffect(() => this.getWeather = setInterval( fetchWeather, 1000)
	    return function cleanup() { clearInterval(this.getWeather) 
			}
```

Both of these code blocks does the same thing, but useEffect links related behavior and takes up half the space. The first  function passed the hook is the 'effect' we want to perform. This equates to componentdidMount **and** componentDidUpdate. As you can see, it also returns a function. This corresponds to the componentWillUnmount lifecycle method. 

These are just the most common hooks available to use. You can also build your own custom hooks to fill any need you have. To properly use hooks however, there are a few rules to follow.

1. Only Call Hooks at the Top Level - **not** inside loops, conditions, or nested functions
2. Only Call Hooks from React Functions - **don't** call hooks from regular JS functions

Follow these rules and you will be well on your way to creating functional react apps with easier to understand code and less bugs. Feel free to explore around with hooks and their multiple uses, and you can always update previous projects if needed. If you want to learn more about hooks, [Reactjs.org](https://reactjs.org/docs/hooks-intro.html) has some great tutorials that can answer any more questions you may have.

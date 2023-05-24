---
title: "Understanding useEffect and dependencies array in React"
datePublished: Wed May 24 2023 08:51:31 GMT+0000 (Coordinated Universal Time)
cuid: cli1guhzf000g09l98ip319bn
slug: understanding-useeffect-and-dependencies-array-in-react
tags: reactjs, nextjs, react-hooks, useeffect

---

I made a simple react app in CodeSandbox to demonstrate the different usage of `useEffect` below.

Note that the app is using Chakra UI for styling but it's not relevant in this article.

%[https://codesandbox.io/s/useeffect-demo-lgi9b8] 

The app can do 3 things.

1. Change the color of the background with the "Change Background" button.
    
2. Increment or decrement the number by using the +/- button.
    
3. Change the text color of "Hello" using the "Change Hello" button.
    

The app has 3 states using `useState`

* number
    
* bg (store background color)
    
* color (store text color for "hello")
    

Now let's get into the demonstration.

# 1\. `useEffect` without dependency array

```javascript
useEffect(() => {
    setNumber(number + 10);
});
```

If you uncomment the first useEffect, you can see that the number is getting bigger and bigger infinitely.

That's because useEffect without dependency array runs on every render.

Let me show you what happens here chronologically.

1. The app renders and initialize the `number` with the value of 1.
    
2. `useEffect` will run the code `setNumber(number + 10)`.
    
3. This will then trigger the component to re-render since we've updated the state of this component – the `number` state.
    
4. And when the component re-renders, useEffect will run again, and we're back at step 2.
    

So useEffect with no dependency arrays will run on every render.

# 2\. `useEffect` with empty dependency array.

```javascript
useEffect(() => {
    setNumber(number + 10);
}, []);
```

Now let's comment the first useEffect and uncomment the second one.

Notice how the number is now 11 instead of infinitely getting bigger.

This is because when `useEffect` is declared with an empty dependency array, it will only run once – which is during the first render.

You can click on the other button to see what happens.

The number will only change if you click on the +/- button only. `Change Background` and `Change Hello` does nothing to the number.

Chronologically what happens is:

1. The app renders and initialize the `number` with the value of 1.
    
2. `useEffect` will run the code `setNumber(number + 10)`, which makes the number 11 now.
    
3. At this point, the component does re-render but `useEffect` does not run on the second render because of the dependency array.
    

Remember: **useEffect with an empty dependency array will only run on the first render.**

# 3\. `useEffect` with 1 variable in the dependency array.

```javascript
useEffect(() => {
    setNumber(number + 10);
}, [bg]);
```

Now if you add `bg` into that dependency array, the same thing will happen as before.

But now if you click on the `Change Background` button, the background color will change but so does the number.

And notice that the number is incremented by 10, not by 1.

What happens here is the `useEffect` will run just like how it was when the array was empty.

But when you add `bg` into the array, it will also run whenever you update the value of `bg`.

It's like the `useEffect` is listening to the value of `bg` for any changes, and if it's updated, it will run the code.

# 4\. `useEffect` with 2 (or more) variables in the dependencies array.

```javascript
useEffect(() => {
    setNumber(number + 10);
}, [bg, color]);
```

Again, on the first render, it will be the same as the 2nd and the 3rd case.

Also, if you click on the `Change Background` button, same behavior is still there.

The difference now is the number will also be incremented if you click on the `Change Hello` button.

At this point, I think you'll understand why that is the case.

The `useEffect` here still listen for changes in the value of `bg` but it also listens for `color` now.

That is why when you click on the `Change Hello`, the number is added by 10. Same reason as the previous case.

You can also try to remove `bg` in the array and see what happens.

# Conclusion

I hope now you understand how `useEffect` and dependencies array works.

To summarize

```javascript
// runs on every render
useEffect(() => {
    setNumber(number + 10);
});

// run once (only on the first render)
useEffect(() => {
    setNumber(number + 10);
}, []);

// runs on first render and anytime value of bg is updated
useEffect(() => {
    setNumber(number + 10);
}, [bg]);

// runs on first render and anytime value of bg and color is updated
useEffect(() => {
    setNumber(number + 10);
}, [bg, color]);
```
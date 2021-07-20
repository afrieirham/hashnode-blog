## What is Artificial Neural Network?

# How _Human_ works.

So let's first look at how we, as a human, make decisions.

Usually, we will gather as many information as possible first before we a decision is made.

When deciding what movie to watch, we usually decide it based on
- reviews
- past experience (watched movies)
- friends' opinions

The key is, *gather as much data as we can*.

Then, based on all of those data, we decide which information is more important.

Say, if I trust the reviews more than my friends' opinions, I will add some sort of _"priority"_ based on the reviews.

If the review tells me that it's a 2/10 and my friends tell me that it's a 100/10,

And because I trust the reviews **MORE** than I trust my friends, I decided not to watch the movie.

This concept of gathering data, prioritize which one is more important, and decide based on that, is exactly how ANN works.

But with numbers, and mathematics – because "robots".

# How ANN works.

![](https://pbs.twimg.com/media/Des5V0YV4AAthe5.jpg)

ANN works by getting the input data and filter it through each hidden layer by using mathematical formula to predict the output.

Essentially the same as our decision making algorithm.

Say you wanna build a machine that can recognize some written numbers.

Of course it is easy for us to do it but for a machine to recognize the written word, or in this case, numbers, is **hard**.

![](https://pbs.twimg.com/media/Des5Wu5UcAAhvVL.jpg:small)
Based on this photo, we can easily tell which number is which.

- 2 is 2
- 3 is 3
- 0 is 0

Effortlessly, because we recognize them. No matter how weird the handwriting is. Even if we have never seen it before, because we recognize patterns.

But to give a machine to do the same thing, they'll need to learn it first.

This is where ANN takes place.

And we are going to use the supervised learning method, as an example.

# How machines _learn_

First, we need data. **Lots of data.**

In this case, we are going to take each individual pixel value of the image.

If you have no idea about what I'm saying, it is basically a value in hexadecimal to represent the color.

But in this case, we're going to make it simple.

***
If it's white, the value will be 1.

If it's black, the value will be 0.

And anything else from off-white to dark gray will be valued within that range.

Off white might be 0.12.

Dark gray might be 0.86.
***

You get the idea.

And let's say this image is 10 by 10 pixels wide. So we have a total of 100 inputs.

Each carrying its own value. 

And then we are going to feed it to the input layer, in this case, it's 100 different values. 

Thus 100 green circles, or called _nodes_.
![](https://pbs.twimg.com/media/Des5XrPUcAAT0iS.jpg:small)

Let's say that the first hidden layer is responsible to recognize whether it is a **line**, **a curve**, or **a loop**.

Thus, there'll be 3 nodes in the first hidden layer.

The input value will be calculated with a mathematical formula here.

Usually the nodes will add all of the inputs and adjust it using a sigmoid function to make it within the range of 0 to 1 again.

![](https://pbs.twimg.com/media/Des5YeRU0AAsZgU.jpg)

So for example the summation of all 100 value of colours that we got before is 10,

Then 10 will be inserted into the sigmoid function and the output will be within 0 to 1. Say it's 0.2

That is for a single node in the hidden layer, we have to do it for all the other nodes too.

![](https://pbs.twimg.com/media/Des5Y_zU0AAEl3q.jpg:large)

You may be thinking.

"All of it will be the same because the input are all the same"

And yes, you are right.

But, there's more.

As I said before, the first hidden layer is responsible to predict whether it is a line, a curve, or a loop right?

If all of the formula and the inputs are the same, how on earth can you get a different output value?

Well, introducing "bias value", a number in which, it will be added to each summation.

And each node has a different bias value.

For example, the first node of the hidden layer's bias value is -10.

Second is 40
Third is 100

Now the output will be different.

The summation of all input was 10 before, now by adding the bias value, it will be different.

- Node 1: 10 + (-10) = 0
- Node 2: 10 + 40 = 50
- Node 3: 10 + 100 = 110

You're welcome.

And ohh, before I forget, do you see all of those lines connecting the nodes from input layer to nodes from the hidden layer.

Yes, all of them. EVERY. SINGLE. ONE.

Carries a different values, that'll be multiplied with the input data.

For example, 
- Input 1: 0.2
- Input 2: 0.5
- Input 3: 0.7

Each line will alter the value of each input and effect the summation of all the inputs.

Here's the value at each line:
- Line 1: 4
- Line 2: 2
- Line 3: 3

The input value now will be different.

Respective input after altered,
- Input 1: 0.2 x 4 = 0.8
- Input 2: 0.5 x 2 = 1.0
- Input 3: 0.7 x 3 = 2.1

Now as you can see, the value will be massively altered due to the bias value of each node and alteration value from each line.

Maybe it is hard to understand it for now because I didn't organize my flow correctly.

# Recap

- The value of each pixel on our image of a handwritten value is retrieved.
- Our image is 10 by 10 pixels, it means that we have a total of 100 input.
- Each value is within the range of 0 to 1.
- Each node has its own bias value.
- Each line has its own value.

***

Now we have a completely different value for each node on the hidden layer after going through the mathematical formula;

Altered by the value from each line
Altered by the bias value in each node

Congratulations, we have just passed the first hidden layer.

There's like thousands more because the number of hidden layers depends on the goal we are trying to achieve.

But say for our handwritten number recognition, there are only 2 hidden layers.

We need to keep doing the math until we reach the output layer before we can even get the result.

![](https://pbs.twimg.com/media/Des3kVcVQAAakeb.jpg:small)

But thank god this is all done by a machine so it is pretty fast.

But wait, what if the prediction is not correct?

Simple answer, 
we need to change the value of the bias value and the value of each line.

How do we know which one to change you ask?

Well, that's the complicated answer. And that is actually the part where the machine actually learns.

Do you wonder, how does the machine even know that it gives the wrong answer?
Or how do they know which value to change?
How does the change affect the output?

If yes, then good. If no, then try to think about it.

Again I am sorry, that part needs another post. It is way too complicated and I think even this post needs time to be understood. 

But good luck.

If you are confused with my explanation, you can watch the video below. It helps to make you understand better.

%[https://www.youtube.com/watch?v=ILsA4nyG7I0]
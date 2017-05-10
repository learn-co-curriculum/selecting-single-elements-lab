## Selecting Elements Lab

### Introduction

Welcome to your first lab! Please read this entire readme. We'll try to only include information to help you. This way, we won't waste your time and will allow you to get to the coding as fast as possible.

We are going to continue with our search engine that pulls identifying information from Wikipedia. As you remember, Aardvark created a chatbot such that when a user asked a question, the program would look to Wikipedia to pull related information about the question topic.


### Your task
In the last section, we pulled the first category information as a way to categorize the topic. In this lab, we'll use the information we learned to pull the first image in the article, an image of Ada Lovelace, a relevant link from the first paragraph, and a few other items.

### The rules of the lab

Ok, let's explain how to pass this lab, and stick this bad boy on your refrigerator for all the world to see.

<iframe height='826' scrolling='no' title='lovelace-lab' src='//codepen.io/joemburgess/embed/bqLqwL/?height=826&theme-id=dark&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/joemburgess/pen/bqLqwL/'>lovelace-lab</a> by Joe Burgess (<a href='http://codepen.io/joemburgess'>@joemburgess</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

Go ahead and select the JS tab and you'll see some Javascript code

```javascript
// Write your code here :)
// 1. Write code to select the Ada Lovelace Image here
	var firstImage = document.querySelector('body')
	// if you select the first image, then the src attribute should equal the url on the line below
	var isFirstAnswerCorrect = (firstImage.src == "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a4/Ada_Lovelace_portrait.jpg/220px-Ada_Lovelace_portrait.jpg")
	// so then the line above will evaluate to a true or false value
	console.log("is the first answer correct? " + isFirstAnswerCorrect)
	// In the above line, we print out to the console whether it is a true or false statement
// 2. Select the first link in the first paragraph
	var mathematicianLink = document.querySelector('p a')
	var isSecondAnswerCorrect = (mathematicianLink.href == "https://s.codepen.io/wiki/Mathematician")
	console.log("is the second answer correct? " + isSecondAnswerCorrect)
// 3. Select the text of the first link in the first paragraph
	var linkText = document.querySelector('body')
	let isThirdAnswerCorrect = linkText.text == 'mathematician'
	console.log("is the third answer correct? " + isThirdAnswerCorrect)
// 4. Select the Ada Lovelace Header
	var header = document.querySelector('body')
	var isFourthAnswerCorrect = header.innerHTML == "Ada Lovelace"
	console.log("is the fourth answer correct? " + isFourthAnswerCorrect)
```

Ok, let's explain what's going on here.  

We want to give you feedback as to whether or not you are properly selecting elements from the lab. So we wrote some code that will print out different statements in the console telling you whether you selected the correct elements. All you have to do is open up the developer console by right clicking, select Inspect, choosing the Console header and switching to the CodePen scope from the dropdown. There should already be some words in there:

```
is the first answer correct? false
is the second answer correct? false
is the third answer correct? false
is the fourth answer correct? false
```

You'll notice they all say `false`. That's no good! We want to get everything to `true`

### All together now, and a critical tip

Let's do the first one together, step by step. But first! A note about how to approach labs and programming in general.

> **Summarize the problem, get feedback** We ask you to write some code inside the JS tab that you see above. But you **should not** start off by writing code there. Instead read the test slowly in the JS tab to get a sense of what it is asking for, summarize the problem in your own words, and then try to produce the right answer by trying different solutions in the Developer Console. (Remember you can copy, paste and write in the developer console.) Then, only after you have produced a working solution in the Developer Console, should you place your working solution in the JS tab.  
>
> Professional programmers follow this approach all of the time and often code their JavaScript code in a developer console before moving it to a codebase.

1. Understand the problem

Ok, so let's take another look at the code.

```javascript
// 1. Write code to select the Ada Lovelace Image here

	var firstImage = document.querySelector('body')
	// if you select the first image, then the src attribute should equal the url on the line below
	var isFirstAnswerCorrect = (firstImage.src == "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a4/Ada_Lovelace_portrait.jpg/220px-Ada_Lovelace_portrait.jpg")

	// so then the line above will evaluate to a true or false value
	console.log("is the first answer correct? " + isFirstAnswerCorrect)
	// In the above line, we print out to the console whether it is a true or false statement
```

It tells us to write code to select the Ada Lovelace image with a bit of code to start us off: `firstImage` equals the result of calling `document.querySelector('body')`. This looks a little odd. `body` is a bit broad don't you think? We'll want to narrow that down a bit.

Moving on, the next line says `isFirstAnswerCorrect = (firstImage.src == "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a4/Ada_Lovelace_portrait.jpg/220px-Ada_Lovelace_portrait.jpg")`. This feels complicated, so let's unpack it a little. Notice that there are two `=` symbols in `firstImage.src == "https://..."`. Two `=` means "equals" whereas one `=` means "value is". This line is basically saying the value of `isFirstAnswerCorrect` is the result (true or false) of comparing `firstImage` to the specified link.

Let's work on this in the developer console. To do that, right-click inside the CodePen and choose inspect.

Let's paste the following code into our developer console and see what happens.

```javascript
firstImage.src == "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a4/Ada_Lovelace_portrait.jpg/220px-Ada_Lovelace_portrait.jpg"
```

Awesome - so pasting it into the console gives us our first error! **That's a good thing.** It says `firstImage is not defined`. This means there is no variable called `firstImage` yet. Remember the earlier line `var firstImage = document.querySelector('body')`? That one actually sets the `firstImage` variable. So before we can use it, we need to set it. While we do things in order in the JS tab, the console is a whole new world!

![A Whole New World](https://web-dev-readme-photos.s3.amazonaws.com/js/a-whole-new-world.gif)


It doesn't know about the variables in the JS Tab. So, let's first copy paste the variable setting line: 
`var firstImage = document.querySelector('body')`. 

This will return `undefined`. But! It did some magic. Type in `firstImage` and press Enter. Look! You just got the entire `body`. Now we know that `firstImage` has been set. Re-run the original command: `firstImage.src == "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a4/Ada_Lovelace_portrait.jpg/220px-Ada_Lovelace_portrait.jpg"`. 

BOOM we get `false` as the response. That's perfect. That's what our earlier message said. 
`is the first answer correct? false`. We are on the right track. I know that the right side of the `==` is `"https://upload.wikimedia.org/wikipedia/commons/thumb/a/a4/Ada_Lovelace_portrait.jpg/220px-Ada_Lovelace_portrait.jpg"`. 

What is on the left side though? Let's type in `firstImage.src`. Ok, that returns `undefined`. I would definitely say that `undefined` _does not_ equal `"https://upload.wikimedia.org/wikipedia/commons/thumb/a/a4/Ada_Lovelace_portrait.jpg/220px-Ada_Lovelace_portrait.jpg"`, wouldn't you? 

Ok, so now let's sum up, what we learned. The `firstImage` returns everything in the `body` tag, and then `firstImage.src` returns `undefined`. Because undefined does not equal `"https://upload.wikimedia.org/wikipedia/commons/thumb/a/a4/Ada_Lovelace_portrait.jpg/220px-Ada_Lovelace_portrait.jpg"`, it makes sense that the expression `(firstImage.src == "https://upload.wikimedia.org/wikipedia/commons/thumb/f/fc/Padlock-silver.svg/20px-Padlock-silver.svg.png")` returns `false`.  

If we want it to return `true`, we should change the code such that `firstImage` actually selects the image of Ada, and ideally then the expression `firstImage.src == "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a4/Ada_Lovelace_portrait.jpg/220px-Ada_Lovelace_portrait.jpg"` will return `true`. So to complete this problem we need to change the code `document.querySelector('body')` to a line that returns the image of Ada. How do we do that?

Let's use the browser to guide us on what the correct selector should be. Hit the element Selector icon. It's two icons to the left of the Elements Header. Then go over to the image of Ada in the CodePen and click. You'll notice she has an `id` of `lovelace-image`. Remember from previous lessons, we can select that image using the `#` sign before the `lovelace-image`. Let's test this out in the console. Type `var firstImage = document.querySelector('#lovelace-image')`. 

Ok, so that seems to have returned an image. Now, we're almost done. We remember that the `true` or `false` value depends on whether that `firstImage.src` equals the line that we saw earlier. So let's check that by typing into our console `document.querySelector('#lovelace-image').src`. Ok, so that return value seems to match. So we can copy that code and use it to replace the code in the JS tab. Our JS tab should now like the following: 


```javascript
// 1. Write code to select the Ada Lovelace Image here
	var firstImage = document.querySelector('#lovelace-image')
	// if you select the first image, then the src attribute should equal the url on the line below
	var isFirstAnswerCorrect = (firstImage.src == "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a4/Ada_Lovelace_portrait.jpg/220px-Ada_Lovelace_portrait.jpg")
	// so then the line above will evaluate to a true or false value
	console.log("is the first answer correct? " + isFirstAnswerCorrect)
```
Now, we should see an updated response in our Console that says: `is the first answer correct? true`

Awesome. 

![You're awesome](https://web-dev-readme-photos.s3.amazonaws.com/js/extraordinary.gif)

## One More

A quick reminder to make sure you're in the console in the CodePen Scope:

![Codepen](https://web-dev-readme-photos.s3.amazonaws.com/js/select-code-pen.gif)

OK, let's do one more together and then it's time for you to do a few on your own. 

The next question is

```javascript
// 2. Select the first link in the first paragraph
	var mathematicianLink = document.querySelector('p a')
	var isSecondAnswerCorrect = (mathematicianLink.href == "https://s.codepen.io/wiki/Mathematician")
	console.log("is the second answer correct? " + isSecondAnswerCorrect)
```

Again, if you copy the `==` line into your console `(mathematicianLink.href == "https://s.codepen.io/wiki/Mathematician")`, you'll get `mathematicianLink is not defined`. We know this error. It means that the variable `mathematicianLink` has not been set yet! Easy Peasy. Type in `var mathematicianLink = document.querySelector('body')` and you'll now have the `mathemeticianLink` variable set. We can double check by typing `mathematicianLink` and pressing enter. You'll see we get the entire body! That's not what we want all. We want the first link in the first paragraph. 

How do we get the first paragraph? Remember that if you just type in the tag itself you'll get the first of that tag. We want the first paragraph, which is a `p` tag. So, first let's try out `document.querySelector('p')`. If you expand that, you'll see it's the entire paragraph! Whoops, not quite what we want. We need to scope this down to just the first link in the first paragraph.

Since we already have the paragraph, we just need to go deeper and get the first link. Just like we got the first paragraph in the entire site like this `document.querySelector('p')`, we can get the first link, in the first paragraph like this: `document.querySelector('p a')`. If you try that in your console you'll see just the link! Now let's modify our code in the JS tab.

```javascript
// 2. Select the first link in the first paragraph
	var mathematicianLink = document.querySelector('p a')
	let isSecondAnswerCorrect = (mathematicianLink.href == "https://s.codepen.io/wiki/Mathematician")
	console.log("is the second answer correct? " + isSecondAnswerCorrect)
```

## You got this

The rest of the problems will work similar to that. We will be asking you to change the first line of the problem to make sure you are either selecting the correct element or the correct attribute. 

One thing to remember is that when working through these labs, developing a process for approaching problems in the way a professional programmer would is as important (if not more important) than learning the correct methods. So try to use the process we performed above - even if you may not need it for every problem. As you move forward, you will build your own process based on the principles of gathering feedback, summarizing a problem, checking the details.

Now try these on your own:

  3. Select the text of the first link in the first paragraph
  4. Select the header "Ada Lovelace" at the top.

Good luck!

<p class='util--hide'>View <a href='https://learn.co/lessons/selecting-single-elements-lab'>Selecting Single Elements Lab</a> on Learn.co and start learning to code for free.</p>

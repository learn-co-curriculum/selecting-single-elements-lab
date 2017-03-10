## Selecting Elements Lab

### Introduction

Welcome to your first lab!  Please read this entire readme.  We'll try to only include information to help you so as not to waste your time and allow you to get to the coding as fast as possible.

We are going to continue with our search engine that pulls identifying information from Wikipedia.  As you remember, Aardvark created a chatbot such that when a user asked a question, the program would look to Wikipedia to pull related information about the question topic.


### Your task
In the last section we pulled the first category information as a way to categorize the topic.  In this lab, we'll use the information we learned to pull a related image, information from the *See Also* section in Wikipedia, and the first line as a type of summary.


### The rules of the lab

Ok, let's explain how to pass this lab, and stick this bad boy on your refrigerator for all the world to see.

Use your favorite text editor to open up the `lovelace.html` file.  There you will see the HTML of our Wikipedia article.  Now, scroll to the bottom of the file.

INSERT PICTURE

There, you'll see a script tag, and the following code:

```html
<script>
// Write your code here :)

// 1. Write code to select the first image here

	let firstAnswer = document.querySelector('')
	// if you select the first image, then the src attribute should equal the url on the line below
	let firstAnswerCorrect = (firstAnswer.src == "https://upload.wikimedia.org/wikipedia/commons/thumb/f/fc/Padlock-silver.svg/20px-Padlock-silver.svg.png")
	// so then the line above will evaluate to a true or false value
	console.log("is the first answer correct? " + firstAnswerCorrect)
	// In the above line, we print out to the console whether it is a true or false statement

...

</script>
```

Ok, let's explain what's going on here.  

We want to give you feedback as to whether or not you are properly selecting elements from the lab.  So we wrote some code that will print out different statements in the console telling you whether you selecting the correct elements.  All you have to do is open up the file in your favorite browser, and then open up the console.

### All together now, and a critical tip

Let's do the first one together, step by step.  But first! A note about approach to labs, and programming in general.

> **Guess and Get Feedback**  We ask you to write some code inside the script tags that you see above.  But you **should not** start off by writing code there.  Instead read the test slowly in the script tag to get a sense of what it is asking for, summarize the problem in your own words, and then try to produce the right answer by trying different solutions in the developer console.  Then, only after you have produced a working solution should you place your working solution in the HTML file.  
>
> Professional programmers follow this approach all of the time, and often code their Javascript code in a developer console before moving it to a codebase.

1. Understand the problem

Ok, so let's take another look at the code.

```html
<script>
// Write your code here :)

// 1. Write code to select the first image here

	let firstImage = document.querySelector('')
	// if you select the first image, then the src attribute should equal the url on the line below
	let isFirstAnswerCorrect = (firstImage.src == "https://upload.wikimedia.org/wikipedia/commons/thumb/f/fc/Padlock-silver.svg/20px-Padlock-silver.svg.png")
	// so then the line above will evaluate to a true or false value
	console.log("is the first answer correct? " + isFirstAnswerCorrect)
	// In the above line, we print out to the console whether it is a true or false statement

...

</script>
```

It tells me to write code to select the first image.  Then it says that the first image equals result of calling `document.querySelector('')`.  This looks a little odd to me because so far all of the query selectors had some content inside of the quotes, and this one doesn't.  My guess is this won't select anything.  

Moving on, the next line says isFirstAnswerCorrect equals `(firstImage.src == "https://upload.wikimedia.org/wikipedia/commons/thumb/f/fc/Padlock-silver.svg/20px-Padlock-silver.svg.png")`.  This feels complicated, so let's unpack it a little.  

One thing we can do is paste the code into our developer console.

Awesome - so it returns false and we want it to return true.  Let's keep going and see why it returns false.  Breaking it down more, just type in firstImage.  

It says that firstImage currently returns everything in the body tag.  Then type in `firstImage.src`.  The console says that it returns undefined.  Ok, so now let's sum up, what we learned.  The `firstImage` returns everything in the body tag, and then `firstImage.src` returns undefined.  Because undefined does not equal `"https://upload.wikimedia.org/wikipedia/commons/thumb/f/fc/Padlock-silver.svg/20px-Padlock-silver.svg.png"`, it makes sense that the expression

`(firstImage.src == "https://upload.wikimedia.org/wikipedia/commons/thumb/f/fc/Padlock-silver.svg/20px-Padlock-silver.svg.png")` returns false.  If we want it to return true, we should change the code such that firstImage actually selects the first image, and ideally then the equality statement will return true.  So to complete this problem we need to change the code `document.querySelector('body')` to a line that returns the first image.  How do we do that?

Let's go to the browser and make a guess.  First right click on an image, and inspect the element.  This should open up the console to the appropriate image.  We see that the HTML tag is `img`.  This seems to be the tag.  We remember that to select by a tag, we simply pass through the name of the tag between the quotes in our query selector method, so we give it a shot in the console.  

Ok, so that seems to have returned an image.  Now, we're almost done.  We remember that true or false value depends on whether that firstImage.src equals the line that we saw earlier.  So let's check that by typing into our console `document.querySelector('img').src`, ok that return value seems to match.  So we can copy that code, and move it to our HTML file.  Our HTML file should now like the following:

```html
1. Write code to select the first image here
 let firstImage = document.querySelector('img')
 // if you select the first image, then the src attribute should equal the url on the line below
 let isFirstAnswerCorrect = (firstImage.src == "https://upload.wikimedia.org/wikipedia/commons/thumb/f/fc/Padlock-silver.svg/20px-Padlock-silver.svg.png")
 // so then the line above will evaluate to a true or false value
 console.log("is the first answer correct? " + isFirstAnswerCorrect)
 // In the above line, we print out to the console whether it is a true or false statement
```

Now, if we refresh our HTML page (by pressing ctrl+r) or by hitting the refresh button, we should see an updated line in our console that states that:

`is the first answer correct? true`

Awesome.

## You got this

The rest of the problems will work similar to that.  We will be asking you to change the first line of the problem to make sure you are either selecting the correct element or the correct attribute.  If you refresh the page and the console tells you that you have the answer correct, you got it right.

One thing to remember is that when working through these labs, developing a process for approaching problems in the way a professional programmer would is as important (if not more important) than learning the correct methods, so try to use the process we performed above - even if you may not need it for every problem.  As you move forward, you will build a process based on the principles of gathering feedback, summarizing a problem, checking the details, that works for you.

Here's what's left

  2. Select the image of Ada Lovelace to the right
    To do so, you will likely need to use child selectors
  3. Select first link from the first paragraph
  4. Select the text of the first link in the first paragraph
  5. Select the bold title, above the picture of Ada Lovelace, in the infobox to the right

Good luck!

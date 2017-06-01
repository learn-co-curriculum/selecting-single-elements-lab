## Selecting Elements Lab

### Introduction

Welcome to your first lab! Please read this entire readme. We'll try to only include information to help you. This way, we won't waste your time and will allow you to get to the coding as fast as possible.

We are going to continue with our search engine that pulls identifying information from Wikipedia. As you remember, Aardvark created a search engine such that when a user asked a question, the program would look to Wikipedia to pull related information about the question topic.


### Your task

In the last section, we pulled the header, the text from the first link and the `href` from the first link. In this section we are going to pull the same information, but from a different simplified Wikipedia page. Since this is a **lab** we are going to submit our final code in the CodePen below. You will work in the Console to discover what the final solution will be, but to complete the lab, you must put your completed code in the CodePen until in the Console you see the correct answers.

### The rules of the lab

Ok, let's explain how to pass this lab, and stick this bad boy on your refrigerator for all the world to see.

<iframe height='482' scrolling='no' title='adele-goldberg-simplified' src='//codepen.io/joemburgess/embed/PmxyNW/?height=482&theme-id=0&default-tab=js,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/joemburgess/pen/PmxyNW/'>adele-goldberg-simplified</a> by Joe Burgess (<a href='http://codepen.io/joemburgess'>@joemburgess</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

Go ahead and select the JS tab and you'll see some Javascript code

```javascript
//Enter querySelector Code here
var header = "ENTER HEADER CODE HERE"
var linkText = "ENTER LINK TEXT CODE HERE"
var linkHref = "ENTER LINK HREF CODE HERE"


// NO NEED TO MODIFY BELOW HERE
console.log(`The header is: ${header}`)
console.log(`The first link text is: ${linkText}`)
console.log(`The first link href is: ${linkHref}`)
```

Let's take a look at what is going on.

The first three lines are _variable definitions_. Variables in Javascript are just like you remember them in Algebra. They are simply names for some sort of data. The `=` sign assigns whatever is on the right side to be held inside of whatever is on the left side. With the default code the phrase `"ENTER HEADER CODE HERE"` is held inside of the `header` variable. 

If you open your Console by right clicking, select inspect, and then selecting Console you should see some output:

```
The header is: ENTER HEADER CODE HERE
The first link text is: ENTER LINK TEXT CODE HERE
The first link href is: ENTER LINK HREF CODE HERE
```

This is outputted by the `console.log` lines

```
console.log(`The header is: ${header}`)
console.log(`The first link text is: ${linkText}`)
console.log(`The first link href is: ${linkHref}`)
```

`console.log` is a tool we use to output text to our console. Makes sense right? Above I told you that currently the `header` variable contains "ENTER HEADER CODE HERE". The first `console.log` looks like this:

```
console.log(`The header is: ${header}`)
```

This outputs `The header is: ENTER HEADER CODE HERE`. Do you see what happened there? The `${header}` took the contents of `header` and made sure they were sent to the console. 

Our task in this lab is to modify the three variables to be the correct `querySelector` to select the correct elements. Then the `console.log` statements will output the code we wrote. 

### All Together Now

We are going to do the first one together, then you'll do the second two on your own. Here is your first task:

**Write the `querySelector` to grab the header, then use `innerHTML` to grab the contents of the header. You should put that code in the JS tab of the CodePen where it says `"ENTER HEADER CODE HERE"`. Be sure to replace the quotes as well. If everything worked as planned your console will output `The header is: Adele Goldberg`**

The first variable asks for the `querySelector` line for the header. Using the same technique you learned in the previous lesson, inspect the element and find out the `id` attribute of the header. It should be `header`. Great, now in the Console (be sure to change the top dropdown to CodePen Preview) type `document.querySelector("#header")`. That should return the correct header. This time though I want just the words "Adele Goldberg". To get just the words in an `h1` tag we are going to use the `innerHTML` attribute. 

 >There are a lot of attribute out there. Don't memorize them, just google around when you can't remember!

Back in the console type:


```javascript
document.querySelector("#header").innerHTML
```

That should return `"Adele Goldberg"`. Now, let's get it into our CodePen and make sure the Console is logging correctly.

Modify the first line of code to be:

```javascript
var header = document.querySelector("#header").innerHTML
```

Looking at the console, you should see the updated logging.

```
The header is: Adele Goldberg
The first link text is: ENTER LINK TEXT CODE HERE
The first link href is: ENTER LINK HREF CODE HERE
```

### On Your Own

You've successfully completed the first question. Now, using what you've learned solve the next two problems:

 1. Using the `documentSelector` and `text` attribute, set the `linkText` variable to equal the text of the first link, which is "computer scientist". This will be just like you did in the previous README. If done correctly, your console will output `the first link text is: computer scientist`.
 2. Using the `documentSelector` and `href` attribute, set the `linkHref` variable to equal the `href` of the first link, which is `"https://en.wikipedia.org/wiki/Computer_scientist"`. This will also be just like you did in the previous README. If done correctly, your console will output `The first link href is: https://en.wikipedia.org/wiki/Computer_scientist`.

Good luck!

<p class='util--hide'>View <a href='https://learn.co/lessons/selecting-single-elements-lab'>Selecting Single Elements Lab</a> on Learn.co and start learning to code for free.</p>

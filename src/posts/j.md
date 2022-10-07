---
title: Function In Javascript
description: Understanding Javascript
author: Peter Ime
date: 2022-10-06T22:47:05.876Z
thumbnail: /static/img/lap.avif
image: /static/img/lap.avif
tags:
  - javascript
---
As a developer, your entire activities will be spent writing function upon function to solve specific problems.

You might be thinking why functions are so important, especially starting out your tech journey.\
\
I'll give you a very simple definition while walking you through some code examples like I'm explaining to a 5-year-old child so you have solid grabs that can stand the test of time.

Sound interesting?\
\
Let's dive right into it.

So for this tutorial, we'll write a basic program that checks a student's score for the programing language test they took and determine whether to pass or fail them.\
\
Before we proceed, you should have an understanding of what functions do:

\
Functions are just like your pot of soup that lets you combine together a group of ingredients to deliver a super delicious 😋 meal. So functions allow you to group together codes that perform a specific task e. g you can have a function to sign in someone on your site, sign out, register a user, etc basically anything you could think of.\
\
Does it make sense?\
\
Okay let's go back to the program we're going to be working on.

Here's the code.

```javascript
function fail() {
    const comment = "Ooops! sorry dude you failed badly"
    console.log(comment)
}

function pass() {
    const comment = "Yo champ! you did very well"
    console.log(comment)
}

function checkResult(score) {
    if (score >= 50) {
        return pass()
    }else {
        return fail()
    }
}

checkResult(50)
```

> The above example might be intimidating to some people while to some it's just eba and egusi soup.

If it's too much for you, just know that it's okay not to understand everything right now. Just follow my explanation and make sense of it then revisit this article when you've leveled up.\
\
In the above code, you can see that we have three functions, each of them are doing a specific task.

We have a fail function which holds the information that will be displayed to the student if they fail\
\
The pass function here is also doing the same thing as the fail function\
\
Next is the checkResult function that actually performs the evaluation of checking the student's score and determining the Right function to call.\
\
Notice that the checkResult function on declaration accepts a parameter and an argument when the function is called/invoked

> Parameters are like placeholder to a function which will denote the value that will passed to the function when called. While\
> Arguments are the value that you provide to your function when invoked.

![code snippet](/static/img/whiteboard.jpeg)

We have a conditional check Inside the function. In this case, we are checking if the student's score is greater than or equal to 50. If the condition is true we return the pass function -- else, we return the fail function.

> Return keyword is used to stop the execution of a function and returning a final value

So in our program, we are using the return keyword to stop our checkResult function and return the corresponding value of the function(pass or fail) that passes the conditional check.

> The return statement should be the last statement in a function because the code after the return statement will not run.

Now our program is working like magic - kudos to you for coming this far!!

You can run the program directly in vscode, ensure that you have node installed then open a JavaScript file and paste the codes. On your vscode, type ctr + shift + ~(backticks) backticks is the key below your ESC key or the key next to the number 1 key. This command will open vscode console. On the console, type node fellowing the file name then press enter and that's the result.

### Conclusion

This is just a basic console program. You can extend the complexity and function of the program to doing something like -- redirecting or giving your users access to another page or maybe awarding them a certificate to download after passing a test. The possibility is endless.
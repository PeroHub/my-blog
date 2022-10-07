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

You might be thinking to yourself why functions are so important especially starting out your tech journey.\
\
I'll give you a very simple definition while walking you through some code examples like I'm explaining to a 5-year-old child so you have a solid grabs that can stand the test of time.

Sound interesting?\
\
Let's dive right into it.

So for this tutorial, we'll write a basic program that checks a student score for the programing language test they took and determine whether to pass or fail them.\
\
Before we proceed, you should have an understanding of what functions do:

\
Functions are just like your pot of soup that lets you combine together a group of ingredients to deliver a super delicious 😋 meal. So functions allow you to group together codes that perform a specific task e. g you can have a function to sign in someone on your site, sign out, register a user, etc basically anything you could think of.\
\
Does it make sense?\
\
Okay let's go back to the program we're going to be working on.

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
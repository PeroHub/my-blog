---
title: Function In Javascript
description: Understanding Javascript
author: Peter Ime
date: 2022-10-06T22:47:05.876Z
thumbnail: /static/img/lap.avif
tags:
  - javascript
---
As a developer, your entire activities will be spent writing function upon function to solve specific problems.

You might be thinking to yourself why functions are so important especially starting out your tech journey.\
\
I'll give you a very simple definition while walking you through some code examples like I'm explaining to a 5 year old child so you have a solid grabs that can stand the test of time.

Sound interesting?\
\
Let's dive right into it.

So for this tutorial, we'll write a basic program that checks a student score for the programing language test they took and determine weather to pass or fail them.\
\
Before we proceed, you should have an understanding of what functions does.

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
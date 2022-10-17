---
title: How To build mobile-first responsive web design
description: Understanding mobile-first responsive web design
author: Peter Ime
date: 2022-10-15T14:50:57.620Z
image: /static/img/fcc-cover.jpg
tags:
  - css
---
Knowing pretty good how to build a fully responsive website that adapts to different device screen resolutions can open a world of endless opportunity and respect to you as you're starting out as a frontend developer or thriving to get good at your Craft.\
\
Your super power or your making of mouth as a frontend developer lies in your ability to build intuitive engaging good user experience products that sit/fits into different screen resolutions. Not something that quashes or stretches outside the screen.\
\
You know those websites where you are like o boy "the person wer implements this one no get joy at all😄". You are either trying so hard to click something or it's overflowing on the screen and creating a horizontal scroll on a mobile device and you're probably like "oh man, this sucks". Sometimes it's your developer friend who shares their project for feedback, you end up telling them those comforting comments so they don't feel bad.\
\
Yea, you know yourself 😁 but sometimes, every newbie needs those comments to feel good.



Why Mobile First\
Naturally, websites are responsive before we even write a single line of CSS. Which is made possible by the meta information present in the header of your page.

```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

\
This gives the browser instructions on how to control the page's dimensions and scaling.\
\
The width=device-width part sets the width of the page to follow the screen width of the device (which will vary depending on the device).\
\
The initial-scale=1.0 part sets the initial zoom level when the page is first loaded by the browser.\
\
So, by default, your contents are responsive on a mobile device with just padding, margins, font size, and font family without writing media queries or adding layout properties like flexbox or grid.

I'll be using a project from frontend mentor in this tutorial to show the difference.\
\
You can click on this [link](https://www.frontendmentor.io/challenges/social-proof-section-6e0qTv_bA) to get the starter Kits for this project and build along.

### Building For Mobile-first

After successfully getting the kits from the frontend mentor site, open it on your vscode and paste in the code below.

The above code represents the HTML structure of our website.\
\
Next up, open a CSS file and paste these code.

Open your project with live server and inspect the page. Shrink the browser width to 375px([](https://www.w3schools.com/css/css_rwd_mediaqueries.asp)[Typical Device Breakpoints](https://www.w3schools.com/css/css_rwd_mediaqueries.asp)) so we can see how it will look on mobile.

See how our page looks good on mobile without any media query and adding flex.

> Browser stacks contents by default which is what we what for our mobile design.

Now, stretch the browser to bigger width and notice how the contents keep responding to the width of the page. Here, remember how I explained the meta-information above. So we are simply designing in accordance with the default scaling of the page and not going against it in any way.

Make sense?\
\
Wait a sec, you're probably thinking "okay Peter the website is not looking nice when the page is stretched, so what are you trying to say?"\
\
Hmm🤪 right. But just chill small let me break it to ya😁\
\
So now, this is where the media query of minimum width and flex property comes in. On mobile we want things to stack(column) from "Top to Butum" 😋 and appear as rows on tablet or laptop.

You now have a functional mobile-first responsive design. If you host on netlify now, it will look absolutely good on mobile but not on big screens yet.\
\
To have it look good on big screens add this line of code and there you go.

### Building For Desktop-first

So here, we are doing quite the opposite of what we did in the mobile-first approach.\
\
We go against the browser scaling by using flex at first to create the layout to row and using media query maximum width to return to column(stacking)\
\
Comment out the mobile-first CSS and paste in the CSS below.\
\
See how we are having a lot of code inside the media query which is a red flag.

> Flexbox or grid is our go-to property for layout design in desktop-first.

So what we are doing in desktop is using flexbox to alter the default behavior and then using media query to re-arrange it back which is not very nice. You will agree that we going against the golden rule of DRY(don't repeat yourself) coupled with a lot of redundant code.

### Conclusion

Today mobile devices are at forefront of the digital revolution. With approximately 60% of web traffic coming from these devices, mobile-first design should be the norm.\
\
My point here is to always build for mobile devices first even if you have a desktops-mockup-only design available. It's not difficult and you'll realize how it safe you a ton of redundant codes.
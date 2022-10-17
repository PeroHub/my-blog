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

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!-- displays site properly based on user's device -->

    <link
      rel="icon"
      type="image/png"
      sizes="32x32"
      href="./images/favicon-32x32.png"
    />
    <link rel="stylesheet" href="./style.css">

    <title>my project</title>

    
    <script src="https://kit.fontawesome.com/040b7576f0.js" crossorigin="anonymous"></script>
  </head>
  <body>
    <main>
      <section>
        <div class="contentleft">
         
          <h3 class="headerText">10,000+ of our users love our products.</h3>
          <p>We only provide great products combined with excellent customer service.
            See what our satisfied customers are saying about our services.</p>
        </div>
        <div class="contentright">
          <div class="content">
            <span>
              <i class="fa fa-star style="color:yellow !important;"></i>
              <i class="fa fa-star"></i>
              <i class="fa fa-star"></i>
              <i class="fa fa-star"></i>
              <i class="fa fa-star"></i>
            </span>
            <p>Rated 5 Stars in Reviews</p>
          </div>
          <div class="content">
            <span>
              <i class="fa fa-star style="color:yellow !important;"></i>
              <i class="fa fa-star"></i>
              <i class="fa fa-star"></i>
              <i class="fa fa-star"></i>
              <i class="fa fa-star"></i>
            </span>
            <p> Rated 5 Stars in Report Guru</p>
          </div>
          <div class="content">
            <span>
              <i class="fa fa-star style="color:yellow !important;"></i>
              <i class="fa fa-star"></i>
              <i class="fa fa-star"></i>
              <i class="fa fa-star"></i>
              <i class="fa fa-star"></i>
            </span>
            <p>Rated 5 Stars in BestTech</p>
          </div>
        </div>
      </section>
      <section>
        <div class="cardcontainer">
          <div class="cardmedia">
            <div class="cardheader-img">
              <img src="./images/image-colton.jpg" alt="colton">
            </div>
            <div class="headertext">
              <p>Colton Smith </p>
              <p>Verified Buyer</p>
            </div>
          </div>
          <div class="cardaction">
            <p>"We needed the same printed design as the one we had ordered a week prior.
              Not only did they find the original order, but we also received it in time.
              Excellent!"</p>
          </div>
        </div>
        <div class="cardcontainer">
          <div class="cardmedia">
            <div class="cardheader-img">
              <img src="./images/image-irene.jpg" alt="Irene">
            </div>
            <div class="headertext">
              <p>Irene Roberts </p>
              <p>Verified Buyer</p>
            </div>
          </div>
          <div class="cardaction">
            <p>"Customer service is always excellent and very quick turn around. Completely
              delighted with the simplicity of the purchase and the speed of delivery."</p>
          </div>
        </div>
        <div class="cardcontainer">
          <div class="cardmedia">
            <div class="cardheader-img">
              <img src="./images/image-anne.jpg" alt="Anne">
            </div>
            <div class="headertext">
              <p>Anne Wallace </p>
              <p>Verified Buyer</p>
            </div>
          </div>
          <div class="cardaction">
            <p>Put an order with this company and can only praise them for the very high
              standard. Will definitely use them again and recommend them to everyone!"</p>
          </div>
        </div>
      </section>
    </main>
    

    <div class="attribution">
      
     Coded by <a href="#">me</a>.
    </div>
  </body>
</html>

```

The above code represents the HTML structure of our website.\
\
Next up, open a CSS file and paste these code.

```css
@import url('https://fonts.googleapis.com/css2?family=League+Spartan:wght@400;500;700&display=swap');

* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    font-family: 'League Spartan', sans-serif;
}

.fa-star {
    color: hsl(19, 80%, 58%);
}

main {
    padding: 20px;
}

.contentleft h3 {
    font-size: 2rem;
    text-align: center;
    margin: 20px 0;
    color: hsl(300, 43%, 22%);
}

.contentleft p {
    text-align: center;
    color: hsl(300, 43%, 22%);
    margin: 20px 0;
    padding: 10px;
}

.contentright .content {
    background-color: hsl(300, 24%, 96%);
    padding: 20px;
    text-align: center;
    margin-top: 10px;
}

.contentright .content p {
    color: hsl(300, 43%, 22%);
    font-weight: bold;
    margin-top: 10px;
}

.cardcontainer {
    background-color: hsl(300, 43%, 22%);
    color: hsl(0, 0%, 100%);
    margin-top: 20px;
    padding: 30px;
    border-radius: 10px;
}

.cardmedia {
    display: flex;
    margin: 20px 0;
    align-items: center;
}

.cardmedia .cardheader-img {
    display: inline;
    width: 50px;
    height: 50px;
}

.cardmedia .cardheader-img img {
    width: inherit;
    height: inherit;
    border-radius: 50%;
}

.cardmedia .headertext {
    display: inline;
    margin-left: 10px;
   
}

.cardmedia .headertext p:nth-child(2) {
    color: hsl(333, 80%, 67%);
    margin-top: 5px;
}

```

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
To have it look good on big screens add this line of code below and there you go.

```css
@media screen and (min-width: 700px) {
    .section1 {
        display: flex;
        justify-content: space-evenly;
        align-items: center;
        /* background-color: red; */
    }

    .contentleft, .contentright {
        width: 30%;
    }

    .contentleft h3, .contentleft p {
        text-align: left;
        /* font-size: 2.5rem; */
    }

    .contentleft p {
        padding: 0;
    }

    .contentright .second {
        position: relative;
        left: 50px;
    }

    .contentright .third {
        position: relative;
        left: 85px;
    }

    .contentright .content {
        padding: 15px;
    }

    .section2 {
        display: flex;
        gap: 20px;
        width: 75%;
        margin: 0 auto;
        margin-top: 40px;
    }

    .attribution {
        margin-top: 30px;
        text-align: center;
    }
}
```



### Building For Desktop-first

So here, we are doing quite the opposite of what we did in the mobile-first approach.\
\
We go against the browser scaling by using flex at first to create the layout to row and using media query maximum width to return to column(stacking)\
\
Comment out the mobile-first CSS and paste in the CSS below.

```css
@import url('https://fonts.googleapis.com/css2?family=League+Spartan:wght@400;500;700&display=swap');

* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    font-family: 'League Spartan', sans-serif;
}

.fa-star {
    color: hsl(19, 80%, 58%);
}

main {
    padding: 20px;
}

.section1 {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    /* background-color: red; */
}

.contentleft, .contentright {
    width: 30%;
}

.contentleft h3 {
    font-size: 2.5rem;
    text-align: left;
    margin: 20px 0;
    color: hsl(300, 43%, 22%);
}

.contentleft p {
    text-align: left;
    color: hsl(300, 43%, 22%);
    margin: 20px 0;
    padding: 10px;
}

.contentright .content {
    background-color: hsl(300, 24%, 96%);
    text-align: left;
    margin-top: 10px;
    padding: 20px;
}

.contentright .second {
    position: relative;
    left: 50px;
}

.contentright .third {
    position: relative;
    left: 85px;
}

.section2 {
    display: flex;
    gap: 20px;
    width: 75%;
    margin: 0 auto;
    margin-top: 40px;
}

.cardcontainer {
    background-color: hsl(300, 43%, 22%);
    color: hsl(0, 0%, 100%);
    margin-top: 20px;
    padding: 30px;
    border-radius: 10px;
}

.cardmedia {
    display: flex;
    margin: 20px 0;
    align-items: center;
}

.cardmedia .cardheader-img {
    display: inline;
    width: 50px;
    height: 50px;
}

.cardmedia .cardheader-img img {
    width: inherit;
    height: inherit;
    border-radius: 50%;
}

.cardmedia .headertext {
    display: inline;
    margin-left: 10px;
   
}

.cardmedia .headertext p:nth-child(2) {
    color: hsl(333, 80%, 67%);
    margin-top: 5px;
}

.attribution {
    margin-top: 30px;
    text-align: center;
}

@media screen and (max-width: 700px) {
    .section1 {
        flex-direction: column;
    }

    .contentleft, .contentright {
        width: 100%;
    }

    .contentright .second {
        left: 0;
    }
    
    .contentright .third {
        left: 0;
    }

    .contentleft h3, .contentleft p {
        text-align: center;
    }

    .contentright .content {
        text-align: center;
    }

    .section2 {
        flex-direction: column;
        width: 100%;
        gap: 0;
    }

    .contentright .content p {
        margin-top: 10px;
    }
}






```

See how we are resetting the layout(flex-direction, position and width) bo how the browser had already positioned them by default which is a red flag.

> Flexbox or grid is our go-to property for layout design in desktop-first.

So what we are doing on desktop is using flexbox to alter the default behavior and then using media query to re-arrange it back which is not very nice. You will agree that we going against the golden rule of DRY(don't repeat yourself) coupled with a lot of redundant code.

### Conclusion

Today mobile devices are at forefront of the digital revolution. With approximately 60% of web traffic coming from these devices, mobile-first design should be the norm.\
\
My point here is to always build for mobile devices first even if you have a desktops-mockup-only design available. It's not difficult and you'll realize how it safe you a ton of redundant codes.
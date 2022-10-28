---
title: How To Filter in React
description: How To Filter in React
author: Peter Ime
date: 2022-10-27T16:36:34.558Z
image: /static/img/filter.avif
tags:
  - react
---
Implementing filter functionality in an application is very common task of a developer to create a seemingly good user experience feature which saves a user the stress of scrolling through our website a bunch of time to find what they want.

In this tutorial, I assume that you have React knowledge already as this not a beginner tutorial.

To proceed, ensure that you have Node installed. Node is an open source JavaScript runtime environment that runs on chrome V8 engine. This comes bundled with NPM-- a package manager that would enable us install and run React and other packages that we will use.

### How To Check If Node Installed

Open your cmd or terminal and run this command to confirm -

```shell
node -v
```

Your output will look like this -

![node screenshort](/static/img/node.jpg "node")

Also run this command to see the version of NPM -

```shell
npm -v
```

Y﻿ou'll have somthing like this -

![npm screenshort](/static/img/npm.jpg "npm")

Your version of node and npm  might be different at the time of download. No need to worry as the projects is constantly releasing new improved versions.

If you're not having the expected results, go over it again step by step.

### Installing React

Run this command and open the folder on vscode after successful installation.

```shell
npx create-react-app my-app
```

G﻿o inside the folder and start the project with these command-

```shell
cd my-app
npm start
```

N﻿ow lets install tailwind for design and react icons

#### Install Tailwind CSS

```shell
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

#### Configure your template paths

A﻿ tailwind.config.js fille will be generated. Open it and confirm that the configuration is the same as the one below -

```javascript
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

#### Add the Tailwind directives to your CSS

Lets add the @tailwind directives for each of Tailwind’s layers to your ./src/index.css file. Open index.css file and paste in these code-

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

#### I﻿nstall React Icons

Run the code below -

```shell
npm install react-icons --save
```

P﻿hew!, we are done with the setup. Lets start building our app.

### B﻿uilding The App

Now open App.js file and paste in these code below -

```javascript
import React from 'react';
import { useState, useEffect } from 'react';
import './App.css'
import { BsChevronUp, BsChevronDown } from 'react-icons/bs';

const faqObject = [
  {
    ques: 'What is #23forObi about?',
    res: '#23forObi is a movement that connects people in the grass root, we aim to educate people about PVC, good governance and how we can use this power to change our nation for the better.With your help and the help of everyone around you, we can better make this country a reliable, sustainable and relevant institution for ourselves and our kids.',
  },
  {
    ques: 'How do I contribute?',
    res: '#23forObi is a movement that connects people in the grass root, we aim to educate people about PVC, good governance and how we can use this power to change our nation for the better.With your help and the help of everyone around you, we can better make this country a reliable, sustainable and relevant institution for ourselves and our kids.',
  },
  {
    ques: 'What the process of being a part of the movement',
    res: '#23forObi is a movement that connects people in the grass root, we aim to educate people about PVC, good governance and how we can use this power to change our nation for the better.With your help and the help of everyone around you, we can better make this country a reliable, sustainable and relevant institution for ourselves and our kids.',
  },
  {
    ques: 'What is #23forObi about?',
    res: '#23forObi is a movement that connects people in the grass root, we aim to educate people about PVC, good governance and how we can use this power to change our nation for the better.With your help and the help of everyone around you, we can better make this country a reliable, sustainable and relevant institution for ourselves and our kids.',
  },
  {
    ques: 'What is #23forObi about?',
    res: '#23forObi is a movement that connects people in the grass root, we aim to educate people about PVC, good governance and how we can use this power to change our nation for the better.With your help and the help of everyone around you, we can better make this country a reliable, sustainable and relevant institution for ourselves and our kids.',
  },
];

const App = () => {
  const [searchQuery, setSearchQuery] = useState('');
  const [searchValue, setSearchValue ] = useState(faqObject)
  const [faq, setFaq] = useState(false);

  const faqShow = {
    height: '150px',
    transition: '0.5s',
  };

  const faqHide = {
    height: '50px',
    transition: '0.5s',
  };

  const toggle = (index) => {
    if (faq === index) {
      return setFaq(null);
    }
    setFaq(index);
  };



  const handleChange = (e) => {
    setSearchQuery(e.target.value);
  };

  useEffect(() => {

    if(searchQuery !== ''){
      let search = searchValue.filter((value) => {
          return value.ques.toLowerCase().includes(searchQuery.toString().toLowerCase())
        })
        // console.log(search)
        setSearchValue(search)
    }else {
      setSearchValue(faqObject)
    }
  }, [searchQuery])

  
  return (
    <div className='container'>
      <div>
        <div className='flex items-center relative w-[320px] h-[44px] border-2 border-[#979797] rounded-full'>
          <input
            type="text"
            placeholder="Search here"
            value={searchQuery}
            onChange={handleChange}
            className='mx-5 w-1/2 outline-none'
          />
          <div className='absolute left-0 bottom-3 lg:bottom-2 px-2'>
            {/* <Image src={search} alt="search" /> */}
          </div>
        </div>

        <div >
          {searchValue.map((item, index) => (
            <div className='border h-27 rounded-2xl mt-10 overflow-y-hidden bg-white p-4'
              style={faq === index ? faqShow : faqHide}
              onClick={() => toggle(index)}
              key={index}
            >
              <section className='h-8 flex justify-between items-center'>
                <h3>{item.ques}</h3>
                {faq === index ? (
                  <BsChevronDown className="text-3xl" />
                ) : (
                  <BsChevronUp className="text-3xl" />
                )}
              </section>
              <p>{item.res}</p>
            </div>
          ))}
        </div>
      </div>
    </div>
  );
};

export default App;
```

L﻿ong code right? don't worry before I explain, add this responsive CSS code to App.css file - 

```css
.container {
  margin-top: 50px;
}

@media screen and (min-width: 700px) {
  .container {
    width: 70%;
    margin: 0 auto;
    margin-top: 50px;
  }
  
}
```

A﻿lright, let me explain what is happening in App.js :-

1. A﻿rray

![Array](/static/img/array.jpg "Array")

T﻿he data in the image above represent our array of questions and answers that we are using to build our UI.

2﻿. React Event

![event](/static/img/event.jpg "event")



3﻿. Filter Function

![filter](/static/img/filter.jpg "filter")

H﻿ere, we are only filtering when the search fill is not empty. Inside the condition, we get the user inputs and filter from our array of data using include method and converting all values to lowercase. We return the correct values if their search is available else we show the initial data.

And that is it for this tutorial.

### Conclusion

There other ways to achieve the same result. Explore, improve and do some magic with your coding super power.
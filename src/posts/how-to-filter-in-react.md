---
title: How To Filter in React
description: How To Filter in React
author: Peter Ime
date: 2022-10-27T16:36:34.558Z
image: /static/img/filter.avif
tags:
  - react
---
Implementing filtering functionality in an application is very common task of a developer to create a seemingly good user experience feature which saves a user the stress of scrolling through our website a bunch of time to find what they want.

In this tutorial, I assume that you have React knowledge already as this not a beginner tutorial.

To proceed, ensure that you have Node installed. Node is an open source JavaScript runtime environment that runs on chrome V8 engine. This comes bundled with NPM-- a package manager that would enable us install and run React.

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

```shell
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```
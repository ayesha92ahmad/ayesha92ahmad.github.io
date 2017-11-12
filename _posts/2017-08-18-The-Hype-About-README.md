---
layout: post
crosspost_to_medium: true
comments: true
title:  "The Hype about README.md"
excerpt: "Reiterating the importance of documentation no matter how simple a programming language gets"
date:   2017-08-18 22:00:00
---

<br>

If you have ever developed a software you know how you feel about documentation. **Borrrrrring!**
However, if you have worked on completing a half developed project or enhancing a developed project you know the pain of going through code and not knowing what it does without spending a whole lot of time on it. At that time didn't you wish you had some description of what is what and what should you do next? Exactly!

A documentation is an explained description of what the code does, how to install/deploy and some other information that might aid another developer to understand the product better. In fact, a documentation is not just for another developer. It is also for you. Imagine this! You write a code for a complex functionality. After six months you need to modify this functionality. In those six months you have worked on a few different modules and you have forgotten what you had written all that time ago. What do you do? You spend a whole lot of time figuring out what you did six months ago and then spend time to modify it. Now, Imagine this: You _have_ documented the code well. Written comments where necessary and written good description in your README file. Six months later when you refer the documentation, you know exactly what you did and now your work is as simple as figuring out what is the modification to be done.

Something simple like this:

![README pic]({{ site.url }}/assets/img/readme-pic.png)
<br>

A good documentation isn't boring or unapproachable. Often it's written in plain english.

For small projects writing a separate documentation can be an overkill. And this is when README comes to the rescue. It is a file that exists on your project folder that contains the documentation. The concept of README started when computer programs were written using punch cards. The single file contained information about the all the other files in the project. It is the file who's name is always in all caps to stand out amongst the crowd of other files.

[Here](https://github.com/matiassingers/awesome-readme) you can find the curated list of awesome READMEs. Call out to @matiassingers for ths list!


Following are some of the key things you might want to include in your README initially:
1. Steps needed to be taken.
1. Installations or configurations needed.
1. Pointers to understand code that might be of complex nature.

As your codebase grows you can add the following information:
1. Table of content
1. Known bugs.
1. Frequently asked questions

Markdown is the language we use to write READMEs. You can get some help to write on github [here](https://help.github.com/categories/writing-on-github/)

Hence, the hype about READMEs are in fact not hype. You can tell they are a very important part of development. Writing great code isn't just about building something that works but building something that is easy to use and easy to maintain. Therefore, from now on make documentation a priority. Start writing documentation as you write the code. Comment your code well. Do not wait for the last minute. You'll see the difference in the overall quality of product you produce.

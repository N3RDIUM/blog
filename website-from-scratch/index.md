---
title: How I Made A Website From Scratch In Two Weeks - N3RDIUM's Blog
description: If I were to make a website from scratch today, what would I do differently? To answer this question, I decided to remake my personal website from scratch.
lastmod: 2026-03-10
published: 2026-03-10
changefreq: never
priority: "0.8"
feeds:
  - blog/index.json
  - blog/atom.xml
  - blog/rss.xml
  - search.json
tags:
  - diy
  - web
  - project
readtime: 5 min read
template: n3rdium.dev
---
# How I Made A Website From Scratch In Two Weeks
Ever since I came across the [dead internet theory](https://en.wikipedia.org/wiki/Dead_Internet_theory), I’ve foudn the “modern” web a little… unsettling. On the bright side of things, I came across [neocities](https://neocities.org/) going down the same rabbit-hole.

I decided to remake my personal website from scratch, to answer: “If I were to make a website from scratch today, what would I do differently?”

What you’re witnessing right now is the result of two weeks’ worth of hard work. Whether I have been able to contribute anything to help make the internet more “alive” again is for you to decide.
## The Tech
So, what fancy new framework will I be using to make this website?

*NONE.* That’s right. This entire website was hand-made (neovim btw) in plain HTML, CSS and a sprinkle of JS, hosted on GitHub Pages. Also, I try my best to keep the initial page loads as lightweight as possible. All images and non-essential stuff is lazy-loaded or deferred. 

In fact, the initial load for the homepage (as well as most other pages on this site) is under `14kb` uncompressed (the compression makes it `~5kb`)!
## Ergonomics
But… what kind of blogger writes HTML in this day and age? To address this, I wrote a lightweight static site generator for [obsidian](https://obsidian.md) vaults, tailored specifically for this site. The page you’re viewing right now actually went through it. The source code is available at [permafrost](https://github.com/n3rdium/permafrost).

Long story short, using my static site generator, I can write my blog posts and other lightweight text pages in markdown, and it will automatically convert it into optimized HTML at build time.

Obsidian vaults are imported to this website as remote repositories using a [config file](https://github.com/N3RDIUM/n3rdium.dev/blob/main/permafrost.json). Permafrost automatically clones and updates the repositories at build time, which I find to be really convenient. To add a new obsidian vault, I simply have to create the repo and add four lines to a config file.
## UX
As you can (hopefully) tell, despite how lightweight the website is, the UX (hopefully) doesn’t take a hit. Mobile devices, unlike desktops, get a nice drawer-style navigation menu.

For my fellow vim enthusiasts/keyboard power-users out there, I’ve also implemented keyboard-based navigation, which allows you to basically never have to touch the mouse to navigate this site. Get started on the [about](https://n3rdium.dev/about/) page!
## Optimizations
Speaking of optimizations, I also made this site builder/optimizer: [doorknob](https://github.com/n3rdium/doorknob). It handles things like building sitemaps/feeds, injecting (minified) inline CSS/JS, optimizing images, and minifying HTML.
## Hard Numbers
Talk is cheap. Show me the numbers!

Here’s the lighthouse scores of the homepage (sorry about that fireworks particle effect obscuring some text):

![[homepage-lighthouse-report.png]]

Feel free to run any page on this site through [PageSpeed Insights](https://pagespeed.web.dev/)! Of course, getting perfect lighthouse scores doesn’t necessarily mean it’s a good site. But UX and engagement does, and the fact that you’ve to this point is enough for me.

If you encounter any bugs/problems on this website or have suggestions, don’t be shy and file [an issue](https://github.com/n3rdium/n3rdium.dev/issues/)!
## Conclusion
Using this custom build pipeline, I can get perfect lighthouse scores on both desktop and mobile while not sacrificing on looks or UX. You can inspect the source [on github](https://github.com/n3rdium/n3rdium.dev).

At the time of writing this, both [permafrost](https://github.com/n3rdium/permafrost) and [doorknob](https://github.com/n3rdium/doorknob) codebases are really messy, mainly because I was in a hurry to ship this website. I hope that, by the time you’re reading this, future me will have cleaned it all up.

If I could ship this site in about two weeks’ time, you can too!
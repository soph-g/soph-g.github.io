---
layout: post
title: "👩🏼‍💻Teach Yourself CS - Programming Module Setup 👩🏼‍💻"
date: 2020-12-22 13:30:00 +0000
excerpt_separator: <!--more-->
categories: [computer science, coding, learning]
published: true
---

_I am spending some of my lockdown Christmas following the [Teach Yourself CS Curriculum](https://teachyourselfcs.com/). These are my notes on setting up for the [Programming](https://teachyourselfcs.com/#programming) section._

When I started this project I thought I'd be off and away really quickly - learning all the computer science things and revelling in my new found knowledge by Christmas. That is **not** what has happened 😂 I've found the setup required to really follow the suggested course a bit tricky, so I'm making notes here in the hope that it might be of use.


<!--more-->

Of course, writing it all here will make it seem very simple, but trust me this took a while to work out!

# Gathering the Course Material

[Teach Yourself CS](https://teachyourselfcs.com/) recommends studying **CS61A: Structure and Interpretation of Computer Programs** from [University of California, Berkeley](https://www.berkeley.edu/). The public version of the course is now almost 10 years old, but the concepts taught are very much relevant to programming today.

To follow the course as if you are a Berkeley student, and complete the recommended assignments, you need the following course materials:

## Lectures

All the lectures can be found online in the [Internet Archive](https://archive.org/details/ucberkeley-webcast-PL3E89002AA9B9879E?sort=titleSorter).

Start with [Lecture 1 - Functional Programming 1](https://archive.org/details/ucberkeley_webcast_l28HAzKy0N8)

Students at Berkeley would have 3 lectures a week for 15 weeks, plus 1 lab session and 1 discussion session each week. There are also 3 mid-term exams, 4 projects, and a final exam. More information about the structure can be found in the Course Information Handout.

## Textbook

The course is based on _Structure and Interpretation of Computer Programs by Abelson, Sussman and Sussman_.

The book is available for free online, and I found a reasonable PDF version [here](https://sicpebook.files.wordpress.com/2011/06/sicp.pdf)

There is set reading for each week, and homework assignments are sometimes take from the text.

## Course Information Handout

Available as part of the [course repository](https://inst.eecs.berkeley.edu//~cs61a/sp11/), the [Course Information Handout](https://inst.eecs.berkeley.edu//~cs61a/sp11/0.pdf) contains some irrelevant admin info, but it also explains the structure of the course and I recommend reading it before you start.

It also includes the reading and homework assignments for each week, so you can prepare before watching the lectures and get the most out of the course.

## Course Reader 1

[Course Reader 1](https://inst.eecs.berkeley.edu//~cs61a/reader/vol1.html) includes the homework assignments, lab assignments, and the 4 projects to be completed during the course.

## Course Reader 2

[Course Reader 2](https://inst.eecs.berkeley.edu//~cs61a/reader/vol2.html) includes reference documents, and mock mid-term exams.

## Lab & Homework solutions

[Solutions](https://people.eecs.berkeley.edu/~bh/61a-pages/Solutions) for the homework and lab exercises each week.

# Setting up Racket with Simply Scheme

Now you've got the materials gathered and you're ready to start watching the first lecture, it's a good time to set up your development environment. _(Note: this section will be updated as I become more familiar with Racket and Simply Scheme)_

The version of Scheme used in the lectures won't work on modern Macs, but there is a decent alternative available - [Racket](https://racket-lang.org/), with the [Simply Scheme package](https://github.com/jbclements/simply-scheme/tree/master).

- Install Racket by downloading the relevant installation package [here](https://download.racket-lang.org/) (don't use Homebrew, you'll need access to RacketDr which comes with the download).

- You'll need to have access to the `raco` command in the command line to install `simply-scheme`, once you've downloaded and installed Racket, set the path in `.zshrc`

```
export PATH="$PATH:/Applications/Racket v7.9/bin"
```
  Check the file path matches your local setup, and you'll need to re-start Terminal, or reload your profile to pickup the changes. Type `raco help` in the command line to check that this has worked.

- Now you can install [simply-scheme](https://github.com/jbclements/simply-scheme/tree/master) following the simple instructions in the README.

- Now you're ready to give [Simple Scheme](https://docs.racket-lang.org/manual@simply-scheme/index.html) a whirl in DrRacket, the interactive development environment for Racket. Open the DrRacket application, and in the top half to the window change the following line from:

```racket
#lang racket
```

to

```racket
#lang simply-scheme
```

Hit the run button, and you should see the language selection change to Simply Scheme. You'll now how access to the functions used throughout the lecture series - you can type these into to the bottom half of the window and hit enter to evaluate the function 🎉

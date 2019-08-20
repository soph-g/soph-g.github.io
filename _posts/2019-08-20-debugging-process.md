---
layout: post
title: "Debugging Process"
date: 2019-08-20 18:23:10 +0100  
categories: [coding, debugging]
published: true
---

Today I ran a workshop introducing some of the new cohort at [Makers](http://makers.tech){:target="_blank"} to the idea of having a repeatable debugging process.

Most developers find this process naturally, and will apply it without giving it too much thought. But at Makers we are trying to rapidly up-skill developers, and help them to build good coding processes in weeks, not months or years.

## Do you have a repeatable debugging process?

If you're at the very start of your coding journey, you might not yet have a repeatable debugging process. How can you tell if you need one? Look out for these signs:

- You can spend hours on small problems, like undeclared variables

- You aren't always sure how you solved a bug

- You spend a long time reading code to work out what it does

- You often guess what the solution might be

These are just some of the signs that you should work on having a repeatable debugging process! Adopting a methodical approach should help you identify and resolve bugs much quicker.

## What does a repeatable debugging process look like?

Luckily, there are only a few steps that you need to master to make a big difference to your debugging approach.

### Create a short feedback loop

One of the best ways to do this is to make sure you have tests for your code, by using TDD. Running the code and manually interacting with it to replicate bugs takes a lot more time than running automated tests.

### Identify where in the code the bug is occurring

You'll want to find the exact line generating the bug. You might be able to do this using error messages, or the test failure message. Or, you might need to use the next tool to help with this.

### Get visibility of what is happening in the code

Start printing out different parts of the code to work out what is happening. You should aim to turn any of your assumptions about what is happening into concrete knowledge. For example, what is a variable set to? What does a conditional statement return?

In JavaScript this would mean using `console.log` to look at the different parts of the code. The values will be logged when you run the tests.

### Use Google, the smart way

Think carefully about what you are searching for, rather than copying and pasting random code snippets or error messages. Try asking your question aloud before typing it into Google.

Once you've got your search results, favour official documentation over StackOverflow or blogs. Afterall, the people who write tutorials are usually the people who have read the docs!

Use these tools to identify what you need to change to resolve the problem you can see. Once you're confident in your assessment make the change and use your feedback loop (running the tests) to check your work.

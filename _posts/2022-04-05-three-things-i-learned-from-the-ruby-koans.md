---
layout: post
title: Takeaways from The Ruby Koans
---

This week I completed [The Ruby Koans](http://rubykoans.com/), a 281-problem excercise that comprehensively covers Ruby syntax and operators. The problems deal with arrays, methods, regular expressions, classes, exceptions, hashes, modules, blocks, and more. 

*Here are a couple of things I learned:*

#### **1) Blocks with Curly Braces** 
Ruby blocks are anonymous functions that can be passed into methods. Blocks are enclosed in a **do-end statement** or **curly braces {}**. do-end is usually used for blocks that span through multiple lines while {} is used for single line blocks. Blocks can have arguments which should be defined between two pipe | characters.

One way to pass an each statement with a **do-end** block:

```sh
[1, 2, 3].each do |num|
  puts num
end
```
The same code can be condensed and simplified with a **curly braces {}** block:
```sh
[1, 2, 3].each { |num| puts num }
```
This may seem like a minor improvement, but this functionality can enable more complex iterative processes as we move to more complicated problems.

#### **2) Regular Expressions** 
Ruby regular expressions (**ruby regex** for short) are used to identify specific patterns inside strings. 

For example, say we wanted to know whether "Some words" contains any vowels. 

We can use Ruby's .match function:
```sh
if "Some words".match(/[aeiou]/)
  puts "You've got vowels!"
else
  puts "No vowels around these parts."
end
```
Regular expressions are always defined between **two forward slashes**, to differentiate them from other language syntax. The square brackets tell the match function to check whether the referenced text includes *any* of the characters in question.

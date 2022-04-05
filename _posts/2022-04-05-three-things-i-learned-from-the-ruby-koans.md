---
layout: post
title: Takeaways from The Ruby Koans
---

This week I completed [The Ruby Koans](http://rubykoans.com/), a 281-problem excercise that comprehensively covers Ruby syntax and operators. The problems cover arrays, methods, regular expressions, classes, exceptions, hashes, modules, blocks, and more. 

Here are some things I learned:

### 1) Blocks 
Ruby blocks are anonymous functions that can be passed into methods. Blocks are enclosed in a do-end statement or curly braces {}. do-end is usually used for blocks that span through multiple lines while {} is used for single line blocks. Blocks can have arguments which should be defined between two pipe | characters.

One way to pass an each statement:

```sh
[1, 2, 3].each do |num|
  puts num
end
```
The same code can be condensed and simplified with a block:
```sh
[1, 2, 3].each { |num| puts num }
```
This may seem like not much of an improvement, but this functionality can enable more complex iterative processes as we move to more complicated problems.

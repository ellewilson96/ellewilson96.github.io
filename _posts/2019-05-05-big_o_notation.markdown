---
layout: post
title:      "Big O Notation"
date:       2019-05-05 19:17:08 +0000
permalink:  big_o_notation
---


Sometimes, algorithms use test data that isn't reflective of a long-term trend. One that might initially be faster than another could scale to be incredibly slow.

**How do algorithms change as n gets bigger?
**

This is expressed by a concept of Big O notation, which is used in two different ways:

- Informal, conversational language that describes how fast algorithms run
- Formal, mathematical definition:
- "O(g(n)) is a set of functions. Any other function f(n) is in the set O(g(n)) if the ratio between f and g, f(n)/g(n), stays at or below constant C as n scales."

For example, f(n) = 3n + 1 is O(n) because the ratio between f(n) and g(n) = n stays below or at c = 4 as long as n is greater than or equal to 1. 

f(n)/g(n) = (3n +1)/n, with C = 4 describing the upper bound on the ratio.

Let's say Algorithm Q takes timeQ(n) to deal with n users. This is roughly proportional to f(n) = n^2.
Algorithm L takes timeL(n) to run with n users. Proportinal to g(n) = log(n). 

So, timeQ's runtime is O(n^2) and timeL's runtime is O(log n) - Q is quadratic and L is logarithmic.

Logarithmic algorithms are generally preferred as they are often fast even on large inputs.

![](https://cdn-images-1.medium.com/max/1600/1*KfZYFUT2OKfjekJlCeYvuQ.jpeg)

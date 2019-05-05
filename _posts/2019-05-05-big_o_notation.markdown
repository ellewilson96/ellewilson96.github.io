---
layout: post
title:      "Big O Notation"
date:       2019-05-05 15:17:09 -0400
permalink:  big_o_notation
---


Sometimes, algorithms use test data that isn't reflective of a long-term trend. One that might initially be faster than another could scale to be incredibly slow.

**How does the algorithm's efficiency change as n gets bigger?**

This is expressed by a concept of Big O notation, or time complexity, which is used in two different ways:

- Informal, conversational language that describes how fast algorithms run
- Formal, mathematical definition:
- "O(g(n)) is a set of functions. Any other function f(n) is in the set O(g(n)) if the ratio between f and g, f(n)/g(n), stays at or below constant C as n scales."

For example, f(n) = 3n + 1 is O(n) because the ratio between f(n) and g(n) = n stays below or at c = 4 as long as n is greater than or equal to 1. 

f(n)/g(n) = (3n +1)/n, with C = 4 describing the upper bound on the ratio.

Let's say Algorithm Q takes timeQ(n) to deal with n users. This is roughly proportional to f(n) = n^2.
Algorithm L takes timeL(n) to run with n users. Proportional to g(n) = log(n). 

So, timeQ's runtime is O(n^2) and timeL's runtime is O(log n) - Q is quadratic and L is logarithmic.

Logarithmic algorithms are generally preferred as they are often fast even on large inputs.


Here is a guide from [Salma Elshahawy](https://medium.com/@salmaeng71/big-o-notation-cheat-sheet-4a7e5632c93e) on Medium:

* If you are iterating over a single collection of elements using one loop, then run-time will be O(n).
* If you are iterating over half of the collection, it will be O(n/2) -> O(n).
* If you are iterating over two separate collections using two different loops, so it will become O(n+m) -> O(n).
* If you are iterating over a single collection using two nested loops, so it will be O(n²).
* If you are iterating over two different collections using two nested loops, so it will become O(n*m) -> O(n²).
* If you are sorting a collection, this becomes O(n*log(n)).

![](https://cdn-images-1.medium.com/max/1600/1*vWVvdTjrmZzYtCGpr5CwAg.jpeg)

---
layout: post
title:      "Searching Arrays"
date:       2019-04-27 19:31:57 +0000
permalink:  searching_arrays
---


Since graduating from Flatiron School, I have found that I've needed to supplement my studies with additional research on computer science fundamentals. I come from a fashion background, so I certainly didn't go to college for computer science. 

I recently came across this series of courses on [Brilliant.org](http://brilliant.org, which is based on learning through problem-solving  - a method which I almost always prefer. They have courses ranging from Artificial Neural Networks, to Astrology, to Number Theory. I began with the Computer Science Fundamentals course, and so far I am impressed with the course and its material! 

I will start this post series with a couple of different ways to accomplish searching an array.

When searching arrays, we essentially are contiously comparing one element to another until that element has been found - or not found - in the array. We can determine if a particular search method is efficient based on the number of comparisons (*n*) that have to be made in order to find the element.

**Linear Search**

The best case is that one comparison is made, which would mean that the first element in the array was the target element.
The worst case is that n comparisons are made, meaning it took until the very last element in the array to reach a conclusion. 
The average case is that (n + 1)/2 comparisons are made. 

Whether you have the worst case or the average case, both scale linearly with *n* which is not good! The best case is also not very likely.

log₂n gives the number of times n needs to be divided by two before reaching 1. 1 is added to account for the final comparison since there is one element remaining.

**Binary Search**

- Repeatedly chooses a number in the middle of the remaining possible numbers, and then determines if the desired number would lie to the left or the right of the chosen number.
- In each iteration, the amount of remaining numbers is halved, making binary search very efficient.

**For example:
**

If you have 100,000,000 sorted elements, what would the worst case be for a linear search vs binary search?

A linear search's worst case is n, which is 100,000,000 comparisons.

For a binary search, [log₂100,000,000]+1 requires only 27 comparisons. The base two logarithm for 100,000,000 is 26.58, after which we round down and add 1, resulting in 27 comparisons. 

The binary search method, in this case, is 4 million times more efficient.

---
layout: post
title:      "Sorting Lists"
date:       2019-05-01 19:53:22 -0400
permalink:  sorting_lists
---


After reviewing search methods, the next topic to be covered is sorting methods. As I mentioned in my previous post, I have been studying computer science fundamentals through [Brilliant.org](http://brilliant.org) and would highly recommend their material! 

**Insertion Sort**

The essential question here is: How can we place a given element into our array while keeping the array sorted?

1. Place the element, e, to be inserted at the end of the array, A. 
2. Compare e to the element on its left:
* **if there is no element to the left**, then there is no need to go any further, since element e will be the smallest element at the start of the array.
* **if e is greater than or equal to the element on the left**, then we are done here as well; element e is on the right of all smaller elements and on the left of all greater elements, so the array is sorted.
* **If e is smaller**, then it needs to be before the compared element; swap the two.
3. Repeat step 2 until finished.

Example:
```
A = [1, 3, 6, 7, 10] 
e = 4

Step 1: new A = [1, 3, 6, 7, 10, 4]

Step 2: make 4 comparisons total to end with final A: [1, 3, 4, 6, 7, 10]

```


![](https://www.studytonight.com/data-structures/images/basic-insertion-sort.png)

**Insertion Sort Algorithm**

Divides the array into two sections; sorted region on the left and unsorted region on the right.

By repeatedly inserting elements from the unsorted half into the sorted half, the algorithm will produce a fully sorted array.

1. Designate leftmost element of array A as the only element of the sorted side. It will be sorted by default since there is only one element.
2. Insert the first element of the unsorted side into the sorted side, increasing the number of sorted elements by 1.
3. Repeat step 2 until finished.


A plus of using insertion sort is it doesn't require creating a new array - it can sort in-place. 
Its best case is O(n).

However, insertion sort's worst case with large numbers becomes quadratic, and this is more likely than getting the best case.

![](https://www.oreilly.com/library/view/algorithms-in-a/9780596516246/httpatomoreillycomsourceoreillyimages595745.png)




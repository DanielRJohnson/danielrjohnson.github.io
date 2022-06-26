---
title: "On Iteration"
date: 2022-04-04T21:25:02-05:00
draft: false
---

While designing `Glimmer`, I had to think about what forms of iteration I should bring to the language.
None are strictly necessary due do having first-class functions, thanks Haskell Curry. 
However, we do not wish pure recursive iteration on our worst enemies. So, what are our options?

### While
While loops are bread-and-butter to non-functional languages. They do exactly what they promise, and 
they do it well. However, they are not the most convenient for keeping track of indices or iterating
over a range of values. They are able to do this, but it doesn't *feel* good. While's always good to 
have, but we should add some sugar on top of it. Most of the time this sugar comes in the form of for loops.

### The (C)lassic Approach
As long as you don't code in Python or functional languages, you've likely seen the 
`for (something; something; something) { body }` pattern. We have a statement that runs before the loop, 
a condition expression, and a statement that runs after each iteration. This allows for iteration over 
really any sort of type such as a range of integers, a range of floats, pointer arithmetic, etc. 
This approach gives explicit control and is not extremely hard to learn.

However, there are some problems with the classic approach. Without the knowledge of what executes when,
the functionality is not immediately recognizable. It offers half-decent readability, but also enables
writing bad code. Beginners might write `for (; x<5; ) { x++; }`, which should be written instead as a 
while loop since it only checks a condition. Or for instance we have some value `v` in 
`for (v = 0; v < 10; ) { some long body that updates v }`, which can easily lead to confusion. In general,
allowing empty segments can hurt readability.

### The Pythonic Approach
If you have programmed in Python, you've seen the pattern `for variable(s) in collection: do something`.
It's simple. Every iteration you get the next item in the collection. This may seem less capable at first,
but it can be very powerful and intuitive with the right collection modification functions. For instance,
iterating over a range of integers seems annoying until you see `range(low, high, step)`. Keeping track of
your index seems annoying until you find `enumerate(collection)`. 

The Pythonic Approach keeps capability, but offer more intuitiveness. for-in loops are beautiful and 
instantly recognizable without any extra knowledge of what runs when. This is why I implemented for-in
loops in `Glimmer`. 

### Glimmer's Solution
My solution is not new or ground-breaking, but it sure is elegant. Here's how they work:

```
# standard for-in over array
for x in range(5) { # x takes values 0,1,2,3,4
    ...
}

# automatic enumeration of arrays
for i, x in range(5, 10) { # i takes indices 0,1,2,3,4
    ...                    # x takes values 5,6,7,8,9
}

# dict key enumeration
for key in {"a": 1, "b": 2} { # key takes keys "a", "b"
    ...
}

# dict key val enumeration
for key, val in {"a": 1, "b": 2} { # key takes keys "a", "b"
    ...                            # val takes values 1, 2
}
```
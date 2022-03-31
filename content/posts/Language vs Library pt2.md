---
title: "Language vs Library Pt2"
date: 2022-03-08T21:56:01-06:00
draft: false
categories: ["Rant"]
tags: ["Languages"]
---

What is a language responsible for supplying and what should be left to the libraries?

This is a question that I have been pondering when thinking of features to add 
to my language, Glimmer. Obviously a language had better be turing complete
and convenient to work with, but where exactly does language end and library start?

One idea I had to add to Glimmer is NumPy-style arrays with suitable operations baked in.
Although, if you have appropriate operator overloading and basic semantics, there is
no reason that this could not be pushed to a library.

On the flip side of this coin, what about database-style relations. I feel like having
two-dimensional relations with full query and operational support could be very
beneficial to have in a base language. Not everyone needs a SQL server running for
their application, but query-ready tables are very handy to have. Is this needed
to be turing complete? No. Does this add to the convenience and accessability of
the language? I think it may! 

These are two examples of things that could go either way between language and library.

Once a language is turing complete, which is very easy now-a-days, the main goals of
a language is to be efficient and effectively model human reasoning. The second of which
is just as difficult as the first, and deserves much thought.
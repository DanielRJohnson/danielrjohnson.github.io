---
title: "Language vs Library"
date: 2022-03-08T13:53:01-06:00
draft: false
categories: ["Rant"]
tags: ["Languages"]
---

Lately I've been thinking about the relation between a language and its libraries.

Often times, libraries can carry a language to massive popularity, see Python.
While Python as a language has many perks, it also has very notable downsides
like performance. 

Writing your computationally heavy libraries in pure python
doesn't happen much, people use bindings for C/C++. So, the best way to write Python
sometimes is to not write Python. 

I say this while Python is my go-to language. 
I love NumPy, Pandas, Tensorflow, Itertools, and many more libraries for my 
machine learning and data science workflows. However, I've come to learn though that I'm
not a huge fan of Python's overall semantics. Some of my gripes are that lambdas 
are limited to one line, it is dynamically typed, and it is whitespace dependent.

With these downsides, it has made me wonder: what if a language like Go, Dart,
or Lua had the library support like Python?

But maybe I'm looking at this the wrong way. It would be fair to say that Python
has the support of so many libraries through its popularity. I just find it 
unfortunate that it is difficult to move towards new and more elegant languages
because the infrastructure that we have built is not transferable. 

Maybe one day in heaven we'll have perfectly portable languages and APIs.
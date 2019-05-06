---
layout: post
title: "Some rules of simple code"
date: 2019-05-05
---

## The following lines are from *Clean Code* book by Uncle Bob

## In one part the author  quotes the programmer `Ron Jeffries` who talks about his rules of simple code:

In recent years I begin, and nearly end, with Beck’s
rules of simple code. 

In priority order, simple code:

• Runs all the tests;

• Contains no duplication;

• Expresses all the design ideas that are in the
system;

• Minimizes the number of entities such as classes,
methods, functions, and the like.

Of these, I focus mostly on duplication. When the same thing is done over and over,
it’s a sign that there is an idea in our mind that is not well represented in the code. I try to
figure out what it is. Then I try to express that idea more clearly.

Expressiveness to me includes meaningful names, and I am likely to change the
names of things several times before I settle in. With modern coding tools such as Eclipse,
renaming is quite inexpensive, so it doesn’t trouble me to change. Expressiveness goes
beyond names, however. I also look at whether an object or method is doing more than one
thing.
 If it’s an object, it probably needs to be broken into two or more objects. If it’s a
method, I will always use the Extract Method refactoring on it, resulting in one method
that says more clearly what it does, and some submethods saying how it is done.

Duplication and expressiveness take me a very long way into what I consider clean
code, and improving dirty code with just these two things in mind can make a huge differ-
ence. There is, however, one other thing that I’m aware of doing, which is a bit harder to
explain.

After years of doing this work, it seems to me that all programs are made up of very
similar elements. One example is “find things in a collection.” Whether we have a data-
base of employee records, or a hash map of keys and values, or an array of items of some
kind, we often find ourselves wanting a particular item from that collection. 
When I find
that happening, I will often wrap the particular implementation in a more abstract method
or class. 
That gives me a couple of interesting advantages.
I can implement the functionality now with something simple, say a hash map, but
since now all the references to that search are covered by my little abstraction, I can
change the implementation any time I want. I can go forward quickly while preserving my
ability to change later.

In addition, the collection abstraction often calls my attention to what’s “really”
going on, and keeps me from running down the path of implementing arbitrary collection
behavior when all I really need is a few fairly simple ways of finding what I want.
Reduced duplication, high expressiveness, and early building of simple abstractions.

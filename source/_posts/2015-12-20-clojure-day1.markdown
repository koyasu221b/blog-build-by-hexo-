---
layout: post
title: "clojure day1"
date: 2015-12-20 10:48:26 +0800
comments: true
categories: clojure
---
Recently, I try to learn some functional programming.  
My first functional language is clojure,  
which is a dynamic language that targets the JVM.  
I choose the clojure language because it's a dialect of LISP.  
It's a better way to improve your programming thinking than OOP.  
I read the [Seven Languages in Seven Weeks](https://pragprog.com/book/btlang/seven-languages-in-seven-weeks) to start learing clojure.  
I think it's a good way to learn it quickly.  
The following is the practice of day1 excise:  
**HW1.**  Implement a function called (big st n) that returns true if a string st
is longer than n characters.
```
    (defn big [st n] (> (count st) n))))
```
**HW2.** Write a function called (collection-type col) that returns :list, :map,
or :vector based on the type of collection col.
```
(defn collection-type
 [col]
 (cond
    (list? col) :list
    (map? col) :map
    (vector? col) :vector
 )
)

```

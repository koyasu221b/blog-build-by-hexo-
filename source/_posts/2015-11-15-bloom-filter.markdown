---
layout: post
title: "bloom filter"
date: 2015-11-15 09:14:31 +0800
comments: true
categories: algorithm
---
Bloom Filter is a data structure to tell you, whether the elment is belong to a set.  
A basic idea to implement the data structure is bit vector and hash function.  
Here are the example:  

```
    BllomFilter(set A, hash_functions, integer m)
        filter [1..m] = 0;
        foreach ai in A:
            foreach hash function hj:
                filter[hj(ai)] = 1;
            end
        end
    return filter
```
```
    MembershipTest(element, filter, hash_functions)
        foreach hash function hj;
            if filter[hj(element)] !=1 then
                return False
            end
        end
    return True
```

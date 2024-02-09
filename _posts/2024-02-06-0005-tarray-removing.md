---
#layout: post
title:  "#5 - `TArray` removing"
date:   2024-02-06 22:33:33 -0800
tags: tarray containers
---
{% include post_header.html %}
Know your options for removing elements from a `TArray`.

But first...\
Know that all methods for removing elements have a `bAllowShrinking` parameter that defaults to `true`.\
This means that any time elements are removed, a reallocation *might* occur, which means elements need to be copied to a new location in memory, invalidating any pointers or references to those elements.\
If leaving that extra capacity in your array is acceptable, or references to elements must be preserved, then specify `false` so as to not incur the overhead of reallocation & keep your references intact.

#### ⚠ post content tbd ⚠

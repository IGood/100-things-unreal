---
#layout: post
title:  "#6 -- `FString` comparisons"
date:   2024-02-07 00:10:00 -0800
tags: [fstring, string things]
---
{% include post_header.md %}
Know how `FString` comparisons use case-sensitivity.\
This is important because case-insensitive comparisons are more expensive.

- `op==` **is not** case-sensitive
- `Equals` & `Compare` **are** case-sensitive by default (but can be changed with additional arguments)
- everything else (`StartsWith`, `Contains`, etc.) **is not** case-sensitive by default (but can be changed with additional arguments)

---

For performance critical code, prefer converting your string to lowercase before using `Equals` instead of using `op==`.
```cpp
// 👍 write this
MyString.ToLowerInline();
if (MyString.Equals(TEXT("foo"))) ...
else if (MyString.Equals(TEXT("bar"))) ...


// 👎 not that
if (MyString == TEXT("Foo")) ...
else if (MyString == TEXT("Bar")) ...
```
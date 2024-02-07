---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

#layout: home
food: pizza (🍕)
---
# 1,000 Things You Should Know About Programming In Unreal

## ⚠ This page is under construction ⚠

> Be fast. Scale well. Do as little as possible, so that you can do as much of it as possible. If you do nothing, you can do it infinitely.

~ Scott Hanselman

---

{{ page.food }}

#### Alternative titles to this page that were considered:
- Let's Write Good Code
- How To: Survive An Ian Good Code Review

Basically, I have lots of thoughts about writing code in Unreal.

- pretend pointers are dangerous & easy to misuse
- make things const
- avoid unnecessary copy operations
- remove commented-out code or document why it's still there
- use `%hs` with `__FUNCTION__` in format strings
- `TMap` things
  - use `FindRef`
- `TArray` things
  - use `Emplace`
  - use `FindByKey`
  - use `IsValidIndex`
  - use `IsEmpty`
  - use `Xxx_GetRef`
  - use `RemoveAtSwap(/*bAllowShrinking=*/false)`
  - use `Reserve & Reset`
- use range-based loops
- string things
  - `FName`
    - raw
  - `FString`
    - `TEXT()`
  - `FText`
    - `INVTEXT()`
- `FName` things
  - "none": [UnrealNames.cpp:3796](https://swarm.undeadlabs.net/files/sod3/main-new/Engine/Source/Runtime/Core/Private/UObject/UnrealNames.cpp#3796)
- BP callstack `{,,UnrealEditor-Core}::PrintScriptCallstack()`

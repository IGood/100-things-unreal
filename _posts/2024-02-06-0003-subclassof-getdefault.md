---
#layout: post
title:  "3 -- `TSubclassOf::GetDefault`"
date:   2024-02-06 22:22:22 -0800
categories: tsubclassof classes pointers cdo
---
#{{ page.title }}\
<sup>{{ page.date | date: site.date_format }}</sup>

When using `TSubclassOf`, use `TSubclassOf::GetDefault` directly instead of a null-check + `TSubclassOf::op->` + `UClass::GetDefault`.

```cpp
// 👍 write this
TSubclassOf<ABestActor> MyActorClass = ...;
if (const ABestActor* BestActorCDO = MyActorClass.GetDefault())
{
    ...
}

// 👎 not that
TSubclassOf<ABestActor> MyActorClass = ...;
const ABestActor* BestActorCDO = (MyActorClass != nullptr)
    ? MyActorClass->GetDefault<ABestActor>()
    : nullptr;
if (BestActorCDO != nullptr)
{
    ...
}
```

These operations are the same but the latter requires more written code & also generates more binary code.
- null-check calls `operator UClass*` which calls `operator*`
- `operator->` calls `operator*`
- that's 2 calls to `operator*` which performs run time type checking
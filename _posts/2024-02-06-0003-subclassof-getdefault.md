---
#layout: post
title:  "#3 - `TSubclassOf::GetDefault`"
date:   2024-02-06 22:22:22 -0800
tags: tsubclassof classes pointers cdo
---
{% include post_header.html %}
When using `TSubclassOf`, use `TSubclassOf::GetDefault` instead of a null-check + `TSubclassOf::op->` + `UClass::GetDefault`.

```cpp
// 👍 write this
TSubclassOf<ABestActor> MyActorClass;
if (const ABestActor* BestActorCDO = MyActorClass.GetDefault())
{
    ...
}

// 👎 not that
TSubclassOf<ABestActor> MyActorClass;
const ABestActor* BestActorCDO = (MyActorClass != nullptr)
    ? MyActorClass->GetDefault<ABestActor>()
    : nullptr;
if (BestActorCDO != nullptr)
{
    ...
}
```

These operations are the same but the latter requires more written code & also generates more binary code.
- null-check calls `op UClass*` which calls `op*`
- `op->` calls `op*`
- that's 2 calls to `op*` which performs run time type checking before we get to `GetDefault` which *also* performs a run time type check
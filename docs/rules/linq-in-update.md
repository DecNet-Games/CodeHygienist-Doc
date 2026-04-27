---
title: LINQ in Update
parent: Performance Rules
nav_order: 7
---

# LINQ in Update

LINQ (Language Integrated Query) is powerful and expressive, but it is generally unsuitable for runtime performance in Unity, especially on mobile.

## The Problem

Most LINQ operations (`.Where()`, `.Select()`, `.OrderBy()`, `.ToList()`) allocate memory on the heap. When used inside a frequently called method like `Update()`, these allocations trigger the Garbage Collector, leading to framerate "hiccups" and stuttering.

```csharp
void Update() 
{
    // ❌ LINQ allocates an iterator/collection every frame!
    var activeEnemies = allEnemies.Where(e => e.IsActive).ToList(); 
}
```

## Scanner Detection

Code Hygienist Pro identifies usage of common LINQ methods within performance-sensitive scopes.

- **High Severity**: Flagged as a "Critical" issue for Mobile profiles.
- **Context Awareness**: The scanner specifically looks for `.Select`, `.Where`, `.Any`, `.Count` and other enumerable extensions inside `Update`, `FixedUpdate`, and `LateUpdate`.

## Best Practice

- **Cache results**: Perform the query once in `Start()` or when the data changes, and store the result.
- **Use simple loops**: Use a standard `foreach` or `for` loop with a pre-allocated list to filter data without new allocations.

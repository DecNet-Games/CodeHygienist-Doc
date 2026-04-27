---
title: Physics NonAlloc
parent: Performance Rules
nav_order: 8
---

# Physics NonAlloc

Unity's standard physics query methods (like `Physics.OverlapSphere`) are convenient but contribute to memory fragmentation.

## The Problem

Methods like `OverlapSphere` or `RaycastAll` return a *new* array of results every time they are called. This array must be allocated on the heap and subsequently cleaned up by the Garbage Collector.

```csharp
void Update() 
{
    // ❌ Allocates a new array every frame!
    var hits = Physics.OverlapSphere(transform.position, 10f); 
}
```

## The Solution

Unity provides "NonAlloc" versions of these methods (e.g., `OverlapSphereNonAlloc`). These methods take a pre-allocated array as a parameter and return the number of results found, without creating any new memory.

```csharp
Collider[] results = new Collider[10];

void Update() 
{
    // ✅ Reuses the 'results' array. Zero allocations.
    int count = Physics.OverlapSphereNonAlloc(transform.position, 10f, results);
}
```

## How Code Hygienist Helps

- **Detection**: Flags standard physics methods used in `Update` loops.
- **Guidance**: Provides a template and explanation on how to transition to the `NonAlloc` pattern with pre-allocated buffers.

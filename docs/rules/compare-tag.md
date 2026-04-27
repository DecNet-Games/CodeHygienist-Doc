---
title: Use CompareTag
parent: Performance Rules
nav_order: 4
---

# Use CompareTag (PERF_004)

Using the direct `.tag == "string"` comparison in Unity is a common but subtle performance trap.

## The Problem

When you access `gameObject.tag`, Unity creates a new string copy of the tag from the native side to return it to the managed C# side. If you do this inside a collision check or an `Update()` loop, you are generating "Garbage" (memory allocations) every single time that line runs.

```csharp
if (other.gameObject.tag == "Player") // ❌ Allocates a new string!
{
    // ...
}
```

## The Solution

Unity provides a built-in method called `.CompareTag()` which performs the check on the native side without allocating a new string on the C# side.

```csharp
if (other.gameObject.CompareTag("Player")) // ✅ Zero allocations
{
    // ...
}
```

## Auto-Fix

Code Hygienist Pro automatically detects these comparisons and refactors them to use `.CompareTag()`. It correctly identifies the object prefix (e.g., `collision.gameObject` or just `this`) to ensure the refactor is syntactically perfect.

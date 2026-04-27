---
title: Boxing Detection
parent: Performance Rules
nav_order: 5
---

# Boxing Detection

Boxing is one of the most hidden causes of Garbage Collection (GC) spikes in Unity projects.

## What is Boxing?

Boxing occurs when a value type (like `int`, `float`, `struct`, or `enum`) is converted to an `object` type or an interface. This forces the value to be wrapped in a reference type on the heap, triggering a memory allocation.

```csharp
int health = 100;
Debug.Log("Current Health: " + health); // ❌ Boxing 'health' to object for string.Format
```

## How Code Hygienist Helps

Our scanner identifies code patterns where boxing is likely to occur, particularly in performance-critical areas like `Update()` or frequently called utility methods.

### Common Flagged Patterns:
- Passing value types into methods taking `params object[]` (like `string.Format` or `Debug.Log`).
- Implicitly converting enums to strings or objects.
- Storing structs in non-generic collections (like `ArrayList`).

## Optimization Tip

To avoid boxing, consider:
- Using generics (`<T>`) where possible.
- Pre-converting values to strings if they are used repeatedly.
- Avoiding `object` or `interface` parameters for high-frequency method calls.

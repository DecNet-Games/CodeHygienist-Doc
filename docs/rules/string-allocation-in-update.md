---
title: String Allocation in Update
parent: Performance Rules
nav_order: 9
---

# String Allocation in Update

Strings in C# are immutable reference types. Any time you modify or concatenate strings, a new memory allocation occurs on the heap.

## The Problem

Performing string operations inside per-frame methods like `Update()` is a major source of Garbage Collection overhead in Unity UI or logging logic.

```csharp
void Update() 
{
    // ❌ Creates a new string allocation every frame!
    timerText.text = "Time: " + currentTime.ToString("F2"); 
}
```

## Scanner Detection

Code Hygienist Pro identifies high-frequency string operations:
- **Concatenation**: Usage of the `+` operator with strings in loops.
- **Interpolation**: Usage of `$"string {value}"` patterns.
- **ToString() calls**: Frequent conversion of numbers or objects to strings.

## Optimization Best Practices

- **Update only on change**: Only update the UI string when the underlying value has actually changed.
- **StringBuilder**: Use `System.Text.StringBuilder` for complex string building.
- **Custom Formatters**: For numeric UI (like health or score), consider using pre-allocated string caches or custom non-allocating formatters.

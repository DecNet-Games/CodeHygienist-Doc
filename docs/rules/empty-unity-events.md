---
title: Empty Unity Events
parent: Performance Rules
nav_order: 6
---

# Empty Unity Events

Empty boilerplate methods like `void Update()` might seem harmless, but they can significantly impact performance in large scenes.

## The Overhead

Unity uses a messaging system to call lifecycle events like `Update`, `FixedUpdate`, and `LateUpdate`. Every frame, Unity must transition from native C++ code into managed C# code to call these methods. Even if the method body is empty, this transition (Native-to-Managed bridge) still consumes CPU cycles.

If you have 1,000 objects with an empty `Update()` method, you are wasting CPU time on 1,000 unnecessary bridge calls every single frame.

```csharp
void Update() 
{
    // ❌ Empty Update methods still incur overhead!
}
```

## The Scanner Solution

Code Hygienist Pro scans your `MonoBehaviours` for empty lifecycle methods.

- **Detection**: Identifies empty `Update`, `FixedUpdate`, `LateUpdate`, `OnGUI`, etc.
- **Reporting**: Groups these as "Code Smells" with low severity but high cumulative impact.
- **Auto-Fix**: Automatically removes these methods from your script, keeping your codebase lean and efficient.

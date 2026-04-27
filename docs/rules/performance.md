---
title: Performance Rules
layout: default
nav_order: 6
has_children: true
---

# Performance Rules

These rules focus specifically on C# patterns inside Unity that destroy CPU frametimes.

Code Hygienist detects these runtime allocations and intercepts them. 

## Included Rules

### Core Logic
- `GetComponentInUpdateRule`: Detects and caches `GetComponent<T>()` out of `Update`. 
- `CameraMainInUpdateRule`: Scans for `.main` string evaluation properties in loops.
- `HeavyFindsRule`: Strips `FindObjectOfType`, `GameObject.Find`, and tag searches out of looping behaviors.

### Memory & Allocations
- `BoxingDetectionRule`: Detects boxing allocations (e.g., passing value types to `object` parameters).
- `StringAllocationInUpdateRule`: Flags string concatenations and allocations inside per-frame loops.
- `LinqInUpdateRule`: Detects LINQ usage (`.Where`, `.First`, etc.) inside `Update`, which causes hidden per-frame allocations.

### Unity Specifics
- `CompareTagRule`: Replaces `.tag == "string"` with the allocation-free `.CompareTag("string")`.
- `EmptyUnityEventsRule`: Detects empty Unity Events (like `Update`, `Start`) that still incur a native-to-managed call overhead.
- `PhysicsNonAllocRule`: Encourages the use of `NonAlloc` physics variants (e.g., `OverlapSphereNonAlloc`) to avoid array allocations.

*Look at the child pages for deep dives into how the Auto-Fix engine translates these rules safely.*

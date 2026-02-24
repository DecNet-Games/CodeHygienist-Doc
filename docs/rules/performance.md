---
title: Performance Rules
layout: home
nav_order: 6
has_children: true
---

# Performance Rules

These rules focus specifically on C# patterns inside Unity that destroy CPU frametimes.

Code Hygienist detects these runtime allocations and intercepts them. 

## Included Rules

- `GetComponentInUpdateRule`: Detects and caches `GetComponent<T>()` out of `Update`. 
- `CameraMainInUpdateRule`: Scans for `.main` string evaluation properties in loops.
- `HeavyFindsRule`: Strips `FindObjectOfType`, `GameObject.Find`, and tag searches out of looping behaviors.

*Look at the child pages for deep dives into how the Auto-Fix engine translates these rules safely.*

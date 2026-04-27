---
title: Architecture Rules
layout: default
nav_order: 7
has_children: true
---

# Architecture Rules

These rules don't necessarily kill framing performance directly, but they are classic "Code Smells". 

Code Hygienist ensures large projects maintain a clean structural hierarchy, preventing long-term tech debt in Unity projects.

## Included Rules

- `GodClassRule`: Identifies `MonoBehaviours` that are tackling too many responsibilities (huge class thresholds, massive parameter counts).
- `PrivateFieldNamingRule`: Scans the project and automatically reformats inconsistent private variables to standard conventions (e.g. standardizing raw variables into `_privateVariables`).

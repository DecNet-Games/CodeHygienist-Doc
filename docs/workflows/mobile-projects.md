---
title: Optimizing Mobile Projects
parent: Workflows
nav_order: 1
---

# Optimizing Mobile Projects

The constraints on mobile hardware are vastly different than PC. Small allocations that trigger Garbage Collection (GC) spikes will cause noticeable framerate hitching. 

Code Hygienist is an incredible asset for the mobile pipeline.

## The Mobile Profile
When scanning your project, select the **Mobile Filter Profile**. 

This will automatically elevate severity warnings on:
- **LINQ in Update:** Immediately triggers Critical alerts.
- **Repeated new allocations per frame:** Flags and highlights where GC allocs are consistently firing during runtime.

## Batch Fixing for Mobile
If you've bought a template or inherited a messy client project:
1. Go to `Tools > Code Hygienist`
2. Select your `Scripts/` folder.
3. Apply the **Mobile Strict** profile.
4. Click **Batch Auto-Refactor**.

The engine will strip out your basic `.GetComponent` and `Camera.main` allocations across the entire codebase instantly, saving you potentially hours of manual refactoring.

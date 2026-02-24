---
title: Core Features
layout: home
nav_order: 5
has_children: true
---

# Core Features

Code Hygienist Pro isn't just a static analysis utility. It was built from the ground up to solve long-term C# project maintenance issues specific to the Unity Engine.

## Highlighted Capabilities

### 1. The Auto-Refactor Engine
Code Hygienist is packed with **Roslyn AST-based transformations**. Where regex-replacement creates broken logic and compilation errors, Code Hygienist Pro actually understands your code structure and gracefully rewrites it exactly like a senior developer would.

### 2. Deep Scanning Rules
Unity's specific paradigm (`Update` loops, `MonoBehaviour` hierarchies) leads to unique performance sinkholes:
- High-allocation `Update()` methods
- God Classes 
- Slow reflection/search (`FindObjectOfType`)

The scanner identifies exactly what rule string triggered the problem and measures the severity.

### 3. Detailed Reporting
For teams and studios, Code Hygienist automatically outputs an overall "Hygiene Score" alongside HTML and CSV reports detailing what was fixed and when.

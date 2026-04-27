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

### 2. Visual Rule Builder
Create project-specific constraints visually. No need to write C# scripts or master complex Regex. The **Visual Rule Builder** allows you to define rules based on method calls, variable names, or context scope (like only flagging issues inside Update loops).

### 3. CI/CD & Command Line Interface
Automate your code hygiene scans. Use the **CLI** to run scans in batch mode on your build server. Export results to JSON, calculate hygiene scores, and even fail builds if critical issues are detected.

### 4. Deep Scanning Rules
Unity's specific paradigm (`Update` loops, `MonoBehaviour` hierarchies) leads to unique performance sinkholes. Our scanner identifies precisely what rule triggered the problem and measures its severity.

### 5. Detailed Reporting
For teams and studios, Code Hygienist automatically outputs an overall "Hygiene Score" alongside HTML and CSV reports detailing what was fixed and when.

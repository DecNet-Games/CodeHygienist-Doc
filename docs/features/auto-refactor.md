---
title: Auto-Refactor Engine
parent: Core Features
nav_order: 1
---

# The Auto-Refactor Engine

The **Auto-Refactor Engine** is the beating heart of Code Hygienist Pro.

What differentiates this tool from standard Linting or Unity Project Auditor is its ability to *fix* the code it complains about safely.

## No Blind Text Replacement 

Typical script editors use simple regex replacements. Regex cannot distinguish between similar method calls or correctly calculate variable scopes in C# classes. Hand-rolling replacements leads to syntax errors requiring manual repairs.

Code Hygienist Pro instead uses **Roslyn Syntax Tree (AST)** transformations.

## Example Transformation

Code Hygienist will detect this performance smell:

```csharp
public void Update() {
    var cam = Camera.main; // Calling Camera.main every frame!
    cam.transform.position += Vector3.up;
}
```

The Engine intercepts the AST, identifies the surrounding `class` node, and safely injects: 
1. A private field `_cachedCamera`.
2. Initialization of that field in `Awake()`.
3. Replaces `Camera.main` within `Update()` with the cached field!

```csharp
private Camera _cachedCamera;

public void Awake() {
    _cachedCamera = Camera.main;
}

public void Update() {
    var cam = _cachedCamera; // Completely safe, GC-free access!
    cam.transform.position += Vector3.up;
}
```

## Diff Previews
Before ANY files are written back to your codebase, the Auto-Refactor Engine presents the proposed refactor script inside the **Safe Mode Diff Viewer**.

If you're skeptical of a refactor, inspect the side-by-side diff overlay before consenting to write to disk. 

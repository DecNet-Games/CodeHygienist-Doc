---
title: Getting Started
layout: home
nav_order: 2
---

# Getting Started with Code Hygienist Pro

Welcome to the future of cleanly managed Unity projects.

**Code Hygienist Pro** sits on top of your Unity project as a "Code Cleanup Engine." Unlike typical static analyzers that just point out bad code and tell you to fix it by hand, Code Hygienist:

1. **Detects** code smells using specific performance and architecture rules.
2. **Explains** exactly *why* it's bad and its performance impact.
3. **Previews** the generated fix with a side-by-side diff.
4. **Applies** the refactor securely using Roslyn AST (Syntax Tree) modification—*not regex-based search-and-replace.*

## Core Concepts

If you’ve inherited messy prototype code, or just never got around to refactoring:

> 💡 **"Safe Mode" (Diff Preview)**
> Code Hygienist embraces safety. You will **never** have your codebase blindly overwritten. Every single fix goes through our Diff Preview Window. Approve it per-file, per-rule, or blindly click "Approve All" when you trust a rule! 

> 💡 **The Auto-Refactor Engine**
> The engine doesn't simply replace strings. If it detects `GetComponent<Rigidbody>()` inside an `Update()` loop, it will gracefully inject a `_rigidbody` private field and place the assignment in the `Awake()` method—ensuring minimal GC allocs across frames!

---

## "Hello World" Scan 🌍

Ready to unleash it on your code? Head over to the [Quick Start Guide]({{ site.baseurl }}/docs/quick-start.html) to scan your first folder!

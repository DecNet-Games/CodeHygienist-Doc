---
title: FAQ
layout: home
nav_order: 9
---

# Frequently Asked Questions

### Does Code Hygienist just use regex to fix my code?
**No.** While the *Custom Rule Creator* uses Regex to flag issues, the built-in **Auto-Refactor Engine** uses Microsoft's Roslyn framework to construct and modify the Abstract Syntax Tree. It understands scoping, references, and language rules to guarantee it outputs valid C# code!

### Will it break my project?
The tool is designed with absolute safety in mind. 
1. **Never Blind:** It never modifies files invisibly.
2. **Safe Mode:** Every proposed change is displayed in the side-by-side Diff Previewer.
3. **Undo:** Batch operations automatically generate backup folders and support Revert capabilities.

### Is there a performance hit when using the tool?
Only while scanning the scripts in the Editor. The modifications made by the tool *improve* your runtime performance. There is zero runtime overhead added to your builds.

### Where can I buy this?
Code Hygienist Pro is available exclusively on the Unity Asset Store.

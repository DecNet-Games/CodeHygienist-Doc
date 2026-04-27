---
title: Custom Rule Creator
parent: Core Features
nav_order: 3
---

# Custom Rule Creator

For advanced users, Unity teams, and studio veterans: Code Hygienist Pro enables you to define your own project-specific **Custom Rules**.

Is your team repeatedly committing `FindObjectOfType` or leaving a specific internal testing method in production code? You can automatically flag it across the entire project.

## How to Create Rules

There are two primary ways to create custom rules in Code Hygienist Pro:

### 1. Visual Rule Builder (Recommended)
The [Visual Rule Builder]({{ site.baseurl }}/docs/features/visual-rule-builder.html) provides a user-friendly UI to define constraints visually. It automatically handles the underlying Regex generation, allowing you to focus on *what* to find rather than *how* to write the pattern.

### 2. Manual Regex Rules
For complex patterns that require fine-grained control, you can define rules directly using Regular Expressions in the Rules tab of the main dashboard.

## Storing Team Rules

Custom Rules are stored inside your editor configuration and can be shared across the team by including the `ProjectSettings/CodeHygienistSettings.json` (or similar configuration file) in your version control.

> 📝 **Note**
> Custom rules currently support **Detection** only. The Auto-Refactor AST engine is reserved for built-in rules to ensure absolute syntax safety.

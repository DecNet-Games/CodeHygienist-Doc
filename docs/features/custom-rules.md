---
title: Custom Rule Creator
parent: Core Features
nav_order: 3
---

# Custom Rule Creator

For advanced users, Unity teams, and studio veterans: Code Hygienist Pro enables you to define your own project-specific **Custom Rules**.

Is your team repeatedly committing `FindObjectOfType` or leaving a specific internal testing method in production code? The Custom Rule Creator will automatically flag it across the entire project for all developers.

## Creating a new Custom Rule

Custom rules are built using regular expressions to pattern match code smells.

1. Open the **Code Hygienist Dashboard** -> `Rules` Tab.
2. Click **Create New Custom Rule**.
3. Supply the Rule Title, a description, and the **Regex Pattern**.
4. Define the Warning Message (What the developer will see in the Scanner view).
5. Specify Severity Level (`Info`, `Warning`, or `Critical`).

*Note: The Auto-Refactor AST engine currently does not auto-fix custom Regex paths. They will be strictly reported as scanner warnings to be fixed manually.*

### Storing Team Rules

Custom Rules are stored inside your editor configuration. They are saved dynamically into `EditorPrefs` making them persistent across project sessions.

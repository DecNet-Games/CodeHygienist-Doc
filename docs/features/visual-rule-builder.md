---
title: Visual Rule Builder
parent: Core Features
nav_order: 5
---

# Visual Rule Builder 🎨

The **Visual Rule Builder** allows you to create custom codebase constraints without writing a single line of C# or wrestling with complex Regex patterns.

Access it via: `Tools > Code Hygienist > Visual Rule Builder`.

## Why use it?

While Code Hygienist Pro comes with a powerful set of default rules, every project has unique architectural constraints. You might want to:
- Flag usage of a specific legacy internal method.
- Enforce a variable naming convention for a specific subsystem.
- Prevent specific comments from being left in the codebase.

## Builder Workflow

1. **General Properties**: Give your rule a name, set its severity, and write the warning message developers will see in the scanner.
2. **Target Definition**: 
   - **Look For**: Select what the scanner should search for (Method Call, Variable Name, Comment Pattern, or Raw Regex).
   - **Condition**: Choose how to match (Contains, Starts With, Ends With, Exact Match).
   - **Target String**: Enter the text you want to find.
3. **Context Scope**: (Optional) Toggle whether the issue must be inside an `Update` or `FixedUpdate` loop to be flagged (perfect for catching project-specific performance pitfalls).

## Instant Integration

Once you click **Save & Add to Scanner**, your new rule is instantly added to the main Hygienist Scanner. No compilation or project restart required.

> 📝 **Pro Tip**
> The builder automatically generates the underlying Regex for you. You can see a preview of the generated pattern at the bottom of the window before saving.

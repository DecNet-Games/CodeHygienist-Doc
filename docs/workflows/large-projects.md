---
title: Managing Large Codebases
parent: Workflows
nav_order: 2
---

# Managing Large Codebases

When working on a large team with junior and senior developers, maintaining code quality and consistency is difficult. Code Hygienist helps keep entropy under control.

## The Pre-Build Guard
One of the most powerful features for large teams is the **Pre-Build Guard**. 

If Critical issues are detected in the active scenes or codebase when a build is triggered:
- The build is automatically paused/flagged.
- The CI/CD pipeline or Developer is notified.

This ensures simple code smells like a stray `GameObject.Find` inside an `Update()` loop never hit production builds!

## The Shame Dashboard
For studios, Code Hygienist generates a Gamified "Shame Dashboard" that shows:
- The Top 10 worst offending scripts.
- Visual improvements to overall project Hygiene Score.

Encourage developers to take pride in raising the hygiene store of the subsystems they manage!

---
title: Quick Start
layout: default
nav_order: 4
---

# Quick Start ⚡

Ready to stop doing manual refactor drudgery? Let's fix your project in a few clicks.

## Step 1: Open the Scanner 

Once installed, open the main dashboard from the Unity menu:
`Tools > Code Hygienist > Dashboard`

## Step 2: Select a Target

The main window provides options for how broadly you'd like to scan:
- **Entire Project**: Caution, on large projects, this might take a minute!
- **Specific Folder**: (Recommended initially) Pick a `Scripts/` subfolder heavily populated by prototypes.
- **Specific Script**: Great for cleaning up individual massive classes before pushing to source control.

## Step 3: Preview and Auto-Fix!

After scanning, the tool will report a list of findings categorized by **Severity** (Warning, Critical, Info).

If the rule supports Auto-Fix (like caching `Camera.main` out of Update loops), a **"Fix"** or **"Preview"** button will appear.
1. Click **Preview Diff**. 
2. View the side-by-side comparison. You'll see exactly how the private field and `Awake()` allocations get injected.
3. If it looks good, click **Apply Fix**.

Code Hygienist will write the changes directly to your script and ask Unity to recompile!

---
*Ready to see what the Scanner can detect? Check out our list of [Features]({{ site.baseurl }}/docs/features/index.html)*

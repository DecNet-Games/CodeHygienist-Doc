---
title: Command Line Interface (CLI)
parent: Core Features
nav_order: 4
---

# Command Line Interface (CLI)

Code Hygienist Pro supports headless operation, making it perfect for integration into CI/CD pipelines (GitHub Actions, Jenkins, Azure DevOps).

## Usage

You can trigger a headless scan from the terminal using the following command structure:

```bash
Unity -quit -batchmode -projectPath . -executeMethod CodeHygienist.Editor.Build.CodeHygienistCLI.RunHeadlessScan
```

## Command Line Arguments

| Argument | Description |
| :--- | :--- |
| `-reportOutput <path>` | Specifies the destination path for the generated JSON report (Default: `CodeHygieneReport.json`). |
| `-strict` | If present, the CLI will exit with code `1` (failing the build) if any **Critical** severity issues are found. |

## CI/CD Integration

By integrating the CLI into your build pipeline, you can ensure that code quality remains high. 

1. **Scan and Score**: The CLI calculates a "Project Hygiene Score" (0-100%).
2. **Artifact Generation**: It produces a JSON report containing all found issues, which can be stored as build artifacts.
3. **Automated Enforcement**: Use the `-strict` flag to prevent merging or building code that contains critical performance killers.

> 📊 **Hygiene Scoring**
> The score is calculated by subtracting penalties from 100 based on issue severity:
> - **Critical**: -5 points
> - **Warning**: -2 points
> - **Info**: -1 point

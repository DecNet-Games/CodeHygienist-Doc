---
title: Reporting & Metrics
parent: Core Features
nav_order: 2
---

# Reporting & Metrics

Accountability is everything when handling large refactoring efforts across multiple developers. Out-source studios fixing client code need proof of optimization, and large teams need metrics tracking over time.

Code Hygienist Pro provides multiple ways to capture and share your project's health.

## 1. HTML Report Generator

Ideal for human review and stakeholder updates.

- **Total Found Issues**: High-level overview of codebase health.
- **Severity Distribution**: Breakdown of Critical vs Warnings vs Info.
- **Hygiene Score**: A cumulative percentage representing your project's optimization level.

The generated HTML file is standalone and can be attached to emails or embedded in studio Wikis for pipeline visibility.

## 2. JSON Reporting (CLI)

For automated systems and CI/CD pipelines, Code Hygienist Pro can export raw scan data in JSON format.

- **CI/CD Integration**: Seamlessly feed hygiene data into dashboards like Grafana or custom build trackers.
- **Detailed Issue Tracking**: The JSON output includes file paths, line numbers, and exact rule violations for every issue found.
- **Headless Automation**: Generate these reports automatically on every build using the [CLI]({{ site.baseurl }}/docs/features/cli.html).

## 3. CSV Export

For those who need to perform custom analysis in Excel or Google Sheets, all scan results can be exported as a standard CSV file.

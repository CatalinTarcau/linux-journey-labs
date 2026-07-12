# Linux Troubleshooting Guide
 
> A practical guide describing a structured methodology for investigating and resolving Linux and application-related incidents. The objective is to develop an engineering mindset rather than memorizing isolated commands.
 
---
 
# Purpose
 
Troubleshooting is one of the most valuable skills for Linux Engineers, Systems Administrators, and DevOps Engineers.
 
Knowing commands is important.
 
Knowing **which command to execute next** is what differentiates an experienced engineer from someone who simply memorizes syntax.
 
This document presents the investigation methodology developed throughout this repository.
 
---
 
# Investigation Principles
 
Before executing any command:
 
1. Understand the problem.
2. Gather information.
3. Avoid assumptions.
4. Reduce the investigation scope.
5. Validate every hypothesis.
 
Never make changes before understanding the issue.
 
---
 
# Standard Investigation Workflow
 
Whenever an application or service fails, follow this process.
 
```
Problem Report
        │
        ▼
Understand the symptoms
        │
        ▼
Locate the affected service
        │
        ▼
Inspect the logs
        │
        ▼
Inspect the configuration
        │
        ▼
Validate permissions
        │
        ▼
Check dependencies
        │
        ▼
Identify root cause
        │
        ▼
Implement solution
        │
        ▼
Validate the fix
```
 
---
 
# Step 1 — Understand the Problem
 
Before opening a terminal, ask questions.
 
Examples:
 
- What is failing?
- When did it start?
- Is every user affected?
- Did anything change recently?
- Can the problem be reproduced?
 
A good investigation begins with understanding the symptoms.
 
---
 
# Step 2 — Identify the Affected Component
 
Determine which application or service is involved.
 
Examples:
 
- Nginx
- Apache
- SSH
- Docker
- PostgreSQL
- MySQL
 
Clearly identifying the affected component narrows the investigation.
 
---
 
# Step 3 — Inspect the Logs
 
Logs are usually the first source of useful information.
 
Common locations:
 
```text
/var/log
```
 
Typical examples:
 
```text
/var/log/syslog
/var/log/auth.log
/var/log/messages
```
 
Application-specific logs may also exist inside dedicated directories.
 
Example investigation:
 
```bash
grep -i error application.log
```
 
---
 
# Step 4 — Inspect Configuration Files
 
If logs suggest a configuration issue, inspect the relevant configuration files.
 
Typical locations:
 
```text
/etc
```
 
Look for:
 
- Incorrect values
- Missing parameters
- Invalid syntax
- Recent modifications
 
Configuration mistakes are one of the most common causes of service failures.
 
---
 
# Step 5 — Validate Permissions
 
Many problems originate from incorrect ownership or permissions.
 
Verify:
 
- File owner
- Group ownership
- Read permissions
- Write permissions
- Execute permissions
 
Incorrect permissions often prevent applications from accessing required resources.
 
---
 
# Step 6 — Check Dependencies
 
Applications rarely operate in isolation.
 
Verify that dependent services are available.
 
Examples:
 
- Database connectivity
- DNS resolution
- Network connectivity
- Required processes
- Mounted filesystems
 
Always consider external dependencies before assuming an application defect.
 
---
 
# Step 7 — Verify the Solution
 
After implementing a fix:
 
- Restart the affected service if necessary.
- Confirm the issue is resolved.
- Review the logs again.
- Ensure no additional errors appear.
- Validate the application from the user's perspective.
 
A solution is only complete after successful validation.
 
---
 
# Frequently Used Commands
 
Display logs:
 
```bash
cat application.log
```
 
Search for errors:
 
```bash
grep -i error application.log
```
 
Find configuration files:
 
```bash
find /etc -name "*.conf"
```
 
Display recent commands:
 
```bash
history
```
 
Search command history:
 
```bash
history | grep ssh
```
 
Display current directory:
 
```bash
pwd
```
 
List directory contents:
 
```bash
ls -la
```
 
---
 
# Investigation Checklist
 
Before escalating an issue, verify:
 
- Have I reproduced the problem?
- Have I checked the logs?
- Have I inspected the configuration?
- Have I verified permissions?
- Have I considered dependencies?
- Have I validated the solution?
 
---
 
# Common Mistakes
 
Changing configuration before understanding the issue.
 
Ignoring log files.
 
Restarting services repeatedly without investigation.
 
Searching the internet before collecting local evidence.
 
Making multiple changes simultaneously.
 
Skipping validation after implementing a fix.
 
---
 
# Interview Notes
 
### What is the first thing you do when an application stops working?
 
Gather information and inspect the logs before making any changes.
 
---
 
### Why are logs important?
 
Logs provide evidence of what happened and often point directly toward the underlying problem.
 
---
 
### Why should engineers avoid assumptions?
 
Incorrect assumptions increase investigation time and may introduce additional problems.
 
Every conclusion should be supported by evidence.
 
---
 
# Engineering Mindset
 
Troubleshooting is a process of eliminating possibilities until only the root cause remains.
 
Professional engineers:
 
- Observe first.
- Think second.
- Act third.
 
A disciplined investigation is usually faster than a rushed one.
 
---
 
# Best Practices
 
Collect evidence before making changes.
 
Investigate systematically.
 
Reduce the investigation scope.
 
Document findings.
 
Validate every solution.
 
Learn from every incident.
 
---
 
# Related Documents
 
- linux-fundamentals.md
- grep-cheatsheet.md
- interview-notes.md
- devops-mindset.md
 
---
 
# Summary
 
Effective troubleshooting is built on methodology rather than intuition.
 
By following a structured investigation process and relying on evidence instead of assumptions, engineers can resolve incidents more efficiently while minimizing risk to production systems.

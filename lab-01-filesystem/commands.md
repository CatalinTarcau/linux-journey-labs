# Commands Used

This document contains the commands used during **Lab 01 - Linux Filesystem Basics** together with their purpose and observations made while completing the exercises.

---

# pwd

## Purpose

Displays the current working directory.

## Syntax

```bash
pwd
```

## Example

```bash
pwd
```

## Observation

By default, after logging into the system, the current working directory is the user's home directory (`/home/<username>`). After changing the directory with `cd /`, running `pwd` confirmed that the current location became the root directory (`/`).

---

# cd

## Purpose

Changes the current working directory.

## Syntax

```bash
cd <directory>
```

## Example

```bash
cd /
```

## Observation

The command changes the current location inside the Linux filesystem. In this lab it was used to navigate from the user's home directory to the root directory.

---

# ls

## Purpose

Lists the contents of a directory.

## Syntax

```bash
ls
```

## Example

```bash
ls /
```

## Observation

Running the command against the root directory displayed all top-level directories of the Linux filesystem, allowing me to explore the overall structure of the operating system.

---

# ls -l

## Purpose

Displays directory contents using the long listing format.

## Syntax

```bash
ls -l
```

## Example

```bash
ls -l /
```

## Information Displayed

- File permissions
- Owner
- Group
- File size
- Last modification time

## Observation

The long listing format provides significantly more information than the standard `ls` command and is useful when investigating system files.

---

# ls -a

## Purpose

Displays all files, including hidden files and directories.

## Syntax

```bash
ls -a
```

## Example

```bash
ls -a /
```

## Observation

Files and directories beginning with a dot (`.`) become visible. These are usually hidden configuration files.

---

# ls -la

## Purpose

Combines the functionality of both `-l` and `-a`.

## Syntax

```bash
ls -la
```

## Example

```bash
ls -la /
```

## Observation

This command provides the most complete overview of a directory by displaying detailed information together with hidden files. During the lab it helped me better understand how the root filesystem is organized.
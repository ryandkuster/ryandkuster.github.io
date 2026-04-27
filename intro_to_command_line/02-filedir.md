---
layout: default
title: 2. Navigating Files and Directories
parent: Introduction to Command Line
nav_order: 2
---

# Navigating Files and Directories

## `pwd` — Print Working Directory

`pwd` shows you where you are in the filesystem:

```
$ pwd
```

Example output:

```
/home/nelle
```

## `ls` — List Directory Contents

```
$ ls
```

### Useful `ls` options

| Flag | Effect |
|------|--------|
| `-F` | Appends `/` to directories, `*` to executables, `@` to links |
| `-l` | Long format (permissions, size, date) |
| `-h` | Human-readable file sizes (use with `-l`) |
| `-t` | Sort by modification time |
| `-r` | Reverse sort order |

```
$ ls -F
$ ls -l
$ ls -lh
$ ls -rt
```

You can list the contents of a specific directory without navigating into it:

```
$ ls -F practice_data/
```

## Getting Help

```
$ ls --help
$ man ls
```

> **_NOTE:_**  
> On macOS, some built-in shell commands (like `cd`) don't have a `man` page. Try `help cd` instead.

## `cd` — Change Directory

```
$ cd practice_data
$ cd ..
$ cd ~
$ cd /
```

| Path | Meaning |
|------|---------|
| `..` | One level up (parent directory) |
| `~` | Your home directory |
| `/` | The root of the filesystem |

### Absolute vs relative paths

An **absolute path** starts with `/` and describes the full location:

```
$ cd /home/nelle/practice_data
```

A **relative path** describes a location relative to where you are now:

```
$ cd practice_data
```

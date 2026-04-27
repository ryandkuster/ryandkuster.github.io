---
layout: default
title: 3. Working With Files and Directories
parent: Introduction to Command Line
nav_order: 3
---

# Working With Files and Directories

## `mkdir` — Make a Directory

```
$ mkdir results
```

Create nested directories in one step with `-p`:

```
$ mkdir -p project/data project/results
```

> **_NOTE:_**  
> Avoid spaces in directory names — use `_` or `-` instead (e.g., `my_results`, not `my results`).

## `nano` — Create and Edit Text Files

`nano` is a simple terminal text editor:

```
$ nano draft.txt
```

Key nano shortcuts:

| Shortcut | Action |
|----------|--------|
| `Ctrl-O` | Save (WriteOut) |
| `Ctrl-X` | Exit |
| `Ctrl-G` | Help |

## `touch` — Create an Empty File

```
$ touch my_file.txt
```

## `mv` — Move or Rename

Rename a file:

```
$ mv draft.txt thesis.txt
```

Move a file into a directory:

```
$ mv thesis.txt results/
```

## `cp` — Copy

```
$ cp genomic_subset.gff genomic_subset_backup.gff
$ cp -r practice_data/ practice_data_backup/
```

Use `-r` (recursive) to copy entire directories.

## `rm` — Remove

```
$ rm my_file.txt
$ rm -r old_results/
```

> **_NOTE:_**  
> There is no Trash or Recycle Bin in the shell. Deleted files are gone immediately. Use `rm` with care.

## Checking Your Work

After any operation, use `ls -F` to confirm the result:

```
$ ls -F
```

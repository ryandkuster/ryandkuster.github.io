---
layout: default
title: 6. Shell Scripts
parent: Introduction to Command Line
nav_order: 6
---

# Shell Scripts

A shell script is a text file containing shell commands that can be run as a program. Scripts let you save and repeat complex workflows.

## Creating a Script

Use `nano` to write the script:

```
$ nano count_reads.sh
```

Inside the file:

```
wc -l *.fastq | sort -n
```

Save and exit (`Ctrl-O`, `Ctrl-X`).

## Running a Script

```
$ bash count_reads.sh
```

## Passing Arguments to a Script

Use `$1`, `$2`, etc. to refer to arguments passed on the command line:

```
$ nano first_lines.sh
```

Inside the file:

```
head -n "$2" "$1" | tail -n "$3"
```

Run it with arguments:

```
$ bash first_lines.sh Col_0h_rep1_1_subset.fastq 20 5
```

`$1` = filename, `$2` = number of lines for `head`, `$3` = number of lines for `tail`.

## `$@` — All Arguments

`$@` expands to all arguments passed to the script, useful for handling multiple input files:

```
$ nano count_all.sh
```

Inside:

```
wc -l "$@"
```

Run:

```
$ bash count_all.sh *.fastq
```

## Comments with `#`

Lines starting with `#` are ignored by the shell — use them to document your script:

```
# Count lines in all FASTQ files and sort numerically
wc -l "$@" | sort -n
```

## Saving Commands from History

View recent commands:

```
$ history | tail -n 10
```

Save the last 5 commands into a script:

```
$ history | tail -n 5 > recent_commands.sh
```

Then review and clean up `recent_commands.sh` before running it.

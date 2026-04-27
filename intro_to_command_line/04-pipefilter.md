---
layout: default
title: 4. Pipes and Filters
parent: Introduction to Command Line
nav_order: 4
---

# Pipes and Filters

## `wc` — Word Count

`wc` counts lines, words, and characters in a file:

```
$ wc Col_0h_rep1_1_subset.fastq
```

| Flag | Counts |
|------|--------|
| `-l` | Lines only |
| `-w` | Words only |
| `-m` | Characters only |

Count lines in all FASTQ files at once using a wildcard:

```
$ wc -l *.fastq
```

## Redirecting Output with `>`

Send output to a file instead of the screen:

```
$ wc -l *.fastq > line_counts.txt
```

> **_NOTE:_**  
> `>` overwrites the file if it already exists. Use `>>` to append instead.

## `cat` — Print File Contents

```
$ cat line_counts.txt
```

## `less` — Page Through a File

For large files, use `less` instead of `cat`:

```
$ less Col_0h_rep1_1_subset.fastq
```

Navigate with the arrow keys. Press `q` to quit, `b` to go back a page.

## `sort` — Sort Lines

```
$ sort line_counts.txt
$ sort -n line_counts.txt
```

`-n` sorts numerically rather than alphabetically.

## `head` and `tail` — First and Last Lines

```
$ head Col_0h_rep1_1_subset.fastq
$ tail Col_0h_rep1_1_subset.fastq
$ head -n 4 Col_0h_rep1_1_subset.fastq
```

## `uniq` — Remove Duplicate Adjacent Lines

```
$ uniq species_list.txt
```

Usually combined with `sort` first so duplicates are adjacent.

## Pipes `|`

Connect commands so the output of one becomes the input of the next:

```
$ wc -l *.fastq | sort -n
$ wc -l *.fastq | sort -n | head -n 1
```

This is the core idea of shell pipelines: small tools chained together to do complex things.

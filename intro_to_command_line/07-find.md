---
layout: default
title: 7. Finding Things
parent: Introduction to Command Line
nav_order: 7
---

# Finding Things

## `grep` — Search Within Files

`grep` prints lines in a file that match a pattern:

```
$ grep "ATCG" cds_subset.fna
```

### Useful `grep` flags

| Flag | Effect |
|------|--------|
| `-w` | Match whole words only |
| `-n` | Show line numbers |
| `-i` | Case-insensitive search |
| `-v` | Invert — print lines that do NOT match |
| `-r` | Recursive — search all files in a directory |
| `-c` | Count matching lines instead of printing them |
| `-E` | Use extended regular expressions |

Examples:

```
$ grep -n ">" cds_subset.fna
$ grep -c ">" cds_subset.fna
$ grep -i "atcg" cds_subset.fna
$ grep -v ">" cds_subset.fna
$ grep -r "gene" practice_data/
```

### Regular Expressions with `-E`

| Pattern | Matches |
|---------|---------|
| `^` | Start of line |
| `.` | Any single character |
| `*` | Zero or more of the preceding character |
| `?` | Zero or one of the preceding character |

```
$ grep -E "^>" cds_subset.fna
```

This prints all FASTA header lines (lines beginning with `>`).

## `find` — Search for Files

`find` searches for files and directories by name, type, or other attributes:

```
$ find . -name "*.fastq"
$ find . -type f -name "*.fna"
$ find . -type d
```

| Flag | Effect |
|------|--------|
| `-name` | Match filename (supports wildcards) |
| `-type f` | Files only |
| `-type d` | Directories only |

## Combining `find` and `grep`

Count matching lines across all files found by `find`:

```
$ find . -name "*.fna" | wc -l
```

Pass `find` results to another command using a loop:

```
$ for file in $(find . -name "*.fna")
> do
>     grep -c ">" $file
> done
```

## `cut` — Extract Columns

`cut` extracts specific fields from delimited text:

```
$ cut -d , -f 1 sample_sheet.csv
$ cut -d , -f 1,3 sample_sheet.csv
```

`-d ,` sets the delimiter to `,`; `-f 1` selects field 1.

Combine with `grep` and `sort`:

```
$ grep "sample" sample_sheet.csv | cut -d , -f 2 | sort | uniq
```

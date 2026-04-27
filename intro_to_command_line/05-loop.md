---
layout: default
title: 5. Loops
parent: Introduction to Command Line
nav_order: 5
---

# Loops

Loops let you run the same commands on many files without repeating yourself.

## Basic `for` Loop Syntax

```
for variable in list_of_items
do
    command $variable
done
```

## Example: Print Filenames

```
$ for filename in Col_0h_rep1_1_subset.fastq Col_0h_rep1_2_subset.fastq
> do
>     echo $filename
> done
```

> **_NOTE:_**  
> The `>` at the start of each line is the shell's **continuation prompt** — it means the shell is waiting for more input. Do not type it yourself.

## Using Wildcards in Loops

Process all FASTQ files in a directory:

```
$ for filename in *.fastq
> do
>     echo $filename
>     head -n 4 $filename
> done
```

## Looping Over a Numeric Range

```
$ for number in {1..9}
> do
>     echo $number
> done
```

## Appending Output with `>>`

Concatenate all FASTA files into one:

```
$ for filename in *.fna
> do
>     cat $filename >> all_sequences.fna
> done
```

> **_NOTE:_**  
> Use `>>` (append) not `>` (overwrite) inside loops, or you'll overwrite the output file on every iteration.

## Filenames With Spaces

Wrap the variable in double quotes when filenames might contain spaces:

```
$ for filename in "sample 1.fastq" "sample 2.fastq"
> do
>     head -n 4 "$filename"
> done
```

## Variable Naming

Any word works as a loop variable — choose something descriptive:

```
$ for sample in *.fastq
> do
>     wc -l $sample
> done
```

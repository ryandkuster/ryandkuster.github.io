---
layout: default
title: 1. Introducing the Shell
parent: Introduction to Command Line
nav_order: 1
---

# Introducing the Shell

The Unix shell is a command-line interface (CLI) that lets you interact with your computer by typing commands. The shell reads your input, runs the command, and prints the output.

## The Prompt

When the shell is ready for input it displays a **prompt**, typically `$`:

```
$
```

It may include your username and machine name:

```
nelle@localhost $
```

Do not type the `$` itself — it is just the indicator that the shell is waiting.

## Your First Command: `ls`

`ls` lists the contents of the current directory:

```
$ ls
```

Example output:

```
Desktop     Downloads   Movies      Pictures
```

## Typos and Errors

If you mistype a command, the shell will tell you it wasn't found:

```
$ ks
ks: command not found
```

> **_NOTE:_**  
> Spelling matters exactly. The shell is case-sensitive and does not guess what you meant.

## What Is the Shell Good For?

The shell lets you:
- navigate and manipulate files and directories
- combine existing tools into pipelines
- automate repetitive tasks with scripts and loops

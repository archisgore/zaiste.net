+++
date = 2018-05-02T00:00:00.000Z
title = "Create Directory with Hypen"
description = """
Use -- to create directory with hyphen.
"""
[taxonomies]
topics = [ "CLI" ]

[extra]
priority = 0.8

+++

Use `mkdir` with `--` to create a directory with a hyphen in the name. This disables further option parsing.

```bash
mkdir -- -my-dir
```

Put additional options always before `--`

```bash
mkdir -p -- -my-dir/foo
```

This is a convention that is part of the POSIX standard. The argument `--` is a delimiter indicating the end of options. Any following arguments should be treated as operands, even if they begin with the '-' character.

Alternatively, use the current directory prefix

```bash
mkdir ./-my-dir
```

This also applies to other commands such as `cd`:

```bash
cd -- -my-dir
```

or `rm`

```bash
rm -r -- -my-dir
```

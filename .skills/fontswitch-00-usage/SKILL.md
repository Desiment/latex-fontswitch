---
name: fontswitch-00-usage
description: Use fontswitch commands to define and apply dynamic font size switches in LaTeX documents.
license: MIT
compatibility: opencode
metadata:
  package: fontswitch
  topic: usage
---

# fontswitch: Usage

## When To Use

Use `fontswitch` when experimenting with changing the base page font size after
the document has started. This is an experimental package.

## Required Setup

The package is intended for use with `extarticle` and size `.clo` files.

```latex
\documentclass{extarticle}
\usepackage{fontswitch}
```

## Commands

### `\SetPageFontSize{<size>}`

Loads `size<size>.clo` at runtime and switches base font-size definitions.

```latex
\begin{document}
Normal text.

\SetPageFontSize{14}
Larger text.
\end{document}
```

Use sizes supported by available class option files, for example `10`, `11`,
`12`, or sizes provided by `extarticle`.

### `\ignore{<tokens>}`

Implementation helper used to suppress `\NeedsTeXFormat` while loading a size
file. It is exposed but not intended for ordinary documents.

### `\originnewcommand`

Implementation copy of the original `\newcommand`, used to restore definitions
after loading a size file. Not intended for ordinary documents.

### `\originNeedsTeXFormat`

Implementation copy of the original `\NeedsTeXFormat`, used to restore the
kernel command after loading a size file. Not intended for ordinary documents.

## Rules

- Use after `\begin{document}`.
- Prefer `extarticle`.
- Treat as experimental; it temporarily changes `\newcommand` and `\NeedsTeXFormat` while loading a class option file.
- Verify output after each font-size switch.

## Avoid

```latex
\documentclass{article}
\usepackage{fontswitch}
```

Prefer:

```latex
\documentclass{extarticle}
\usepackage{fontswitch}
```

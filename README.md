# fontswitch - Dynamic Font Size Switching

LaTeX package for changing base font size after preamble (experimental).

**Requirements:** LaTeX2e (2024-11-01+), xparse, extarticle document class.

**Installation:** Place `fontswitch.sty` in LaTeX path or document folder.

## Command

`\SetPageFontSize{size}` - Changes base font size to `size` points (e.g., 10, 12, 14).

**Example:**
```latex
\documentclass{extarticle}
\usepackage{fontswitch}
\begin{document}
Normal text (10pt).
\SetPageFontSize{14}  % Switch to 14pt
Large text.
\end{document}
```

## Limitations
- **Experimental:** Uses non-standard techniques
- **Class:** Currently only works with `extarticle`
- **Timing:** Must be used after `\begin{document}`

**Version:** 0.1.0 (2025-10-07) | **LaTeX:** 2024-11-01+ | **Status:** Experimental

# LaTeX Article Template

A modern, professional LaTeX template for scientific articles with a clean two-column layout optimized for journal submissions.

## Features

- **Modern Typography**: Uses Charter font family for a contemporary, professional look
- **Two-Column Layout**: Journal-style formatting with optimized spacing
- **US Letter Format**: Designed to match IEEE, Elsevier, Springer, and MDPI layouts
- **Modular Structure**: Separate files for each section (introduction, methods, results, etc.)
- **Bibliography Management**: Pre-configured with natbib (numeric citations)
- **VimTeX Compatible**: Optimized for VimTeX workflows with latexmk
- **Length Prediction**: Margins and fonts calibrated to closely match final journal output

## Quick Start

### Prerequisites

- LaTeX distribution (TeX Live, MiKTeX, or MacTeX)
- `latexmk` for automated compilation
- XCharter font package (usually included in full TeX distributions)

### Building the Document

```bash
# Primary build command (recommended)
latexmk -pdf main.tex

# Alternative: manual compilation
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex

# Clean auxiliary files
latexmk -c
```

## Project Structure

```
.
├── main.tex                    # Main document with preamble
├── sections/                   # Modular section files
│   ├── 01_abstract.tex
│   ├── 02_introduction.tex
│   ├── 03_methods.tex
│   ├── 04_results.tex
│   ├── 05_discussion.tex
│   └── 06_conclusion.tex
├── references/
│   └── references.bib          # BibTeX bibliography
└── figures/                    # Images and figures
```

## Customization

### Title and Author

Edit lines 48-51 in `main.tex`:

```latex
\title{\vspace{-0.5cm}\bfseries Your Title Here}
\author[1]{Your Name}
\affil[1]{Your Institution}
\date{\vspace{-0.5cm}\today}
```

### Spacing Options

```latex
% For draft review with line numbers
\linenumbers              % Uncomment line 45

% For double-spaced drafts
\doublespacing           % Uncomment line 44
```

### Citation Style

Change from numeric to author-year:

```latex
% Line 20: Change citation style
\usepackage{natbib}      % Remove [numbers] option

% Line 71: Change bibliography style
\bibliographystyle{plainnat}
```

## Document Settings

### Page Layout
- **Paper**: US Letter (8.5" × 11")
- **Margins**: Top 0.75in, Bottom 1in, Left/Right 0.625in
- **Column separation**: 0.17in
- **Font**: 10pt Charter (XCharter package)
- **Line spacing**: 1.05 stretch

### Key Packages
- **XCharter**: Modern Charter font family
- **natbib**: Bibliography management (numeric style)
- **hyperref**: Clickable links and cross-references
- **graphicx, caption**: Figure management
- **amsmath, amssymb**: Mathematical notation
- **siunitx**: SI unit formatting
- **booktabs**: Professional tables
- **authblk**: Author affiliations
- **titlesec**: Section spacing customization

## Adding Content

### Sections
Edit section files directly in `sections/`. They are automatically included in `main.tex`.

### Figures
Place images in `figures/` and reference them:

```latex
\begin{figure}[ht]
    \centering
    \includegraphics[width=0.8\linewidth]{figures/yourimage.png}
    \caption{Your caption here}
    \label{fig:yourlabel}
\end{figure}
```

For full-width figures spanning both columns, use `figure*` environment.

### Citations
Add references to `references/references.bib` in BibTeX format, then cite:

```latex
\cite{key}           % Numeric citation [1]
\citet{key}          % Textual citation: Author [1]
\citep{key}          % Parenthetical: (Author, year)
```

## Journal Compatibility

This template provides accurate length prediction (±10%) for:
- IEEE Transactions
- Elsevier journals
- Springer journals
- MDPI journals

When ready to submit, simply copy your content into the journal's official template.

## License

This template is provided as-is for academic and research use.

## Author

Daniel H. Solano Teran
School of Engineering and Sciences, Tecnológico de Monterrey

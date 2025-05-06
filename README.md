# LaTeX Cheatsheet Package

A customizable LaTeX package for creating compact, well-formatted cheat sheets for exams, classes, or quick reference guides. Used throughout my exams at Stanford in CS and Math. 

## Features

- Multi-column layout with automatic balancing
- Compact, customizable design perfect for fitting lots of information on a single page
- Numbered sections and subsections with pastel color highlights
- Mathematical formula support with special highlighting for important equations
- Header with student name, class, and date
- Fully customizable sizes, margins, and spacing

## Installation in Overleaf

1. Create a new project in Overleaf
2. Create a new file named `cheatsheet.sty`
3. Copy the package code into this file
4. Create your `main.tex` file to use the package

## Basic Usage

```latex
\documentclass{article}

% Load the cheatsheet package
\usepackage{cheatsheet}

% Customize your header
\setcheatsheetheader{Your Name}{Course Name}{May 6, 2025}

\begin{document}

% Start the cheat sheet
\begincheatsheet

% Add a section
\nsection{Mathematics}

% Add a subsection with content
\nsubsection{Calculus}{%
  Fundamental theorem: $\int_a^b f'(x)dx = f(b) - f(a)$.
  \begin{itemize}
    \item Derivatives: $\frac{d}{dx}(x^n) = nx^{n-1}$
    \item Integration by parts: $\int u dv = uv - \int v du$
    \item L'Hôpital's rule: \keyfm{\lim_{x \to a}\frac{f(x)}{g(x)} = \lim_{x \to a}\frac{f'(x)}{g'(x)}}
  \end{itemize}
}

% Add a column break if needed
\columnbreak

% End the cheat sheet
\endcheatsheet

\end{document}
```

## Configuration Options

The package comes with many customization options:

### Layout Settings

```latex
\setcheatsheetcolumns{3}         % Number of columns (default: 3)
\setcheatsheetmargin{0.25in}     % Page margins (default: 0.15in)
\setcheatsheetcolsep{0.2in}      % Column separation (default: 0.12in)
```

### Font Settings

```latex
\setcheatsheetfontsize{5}        % Base font size (default: 5)
\setcheatsheetsecsize{7}         % Section title size (default: 6.5)
\setcheatsheetsubsecsize{6.5}    % Subsection title size (default: 6)
```

### Spacing Settings

```latex
\setcheatsheetdensity{1.5pt}     % Controls line spacing and item separation (default: 1pt)
```

### Header Settings

```latex
\setcheatsheetheader{John Smith}{Mathematics 101}{May 6, 2025}  % Set header info
\hidecheatsheetheader            % Hide the header completely
```

## Advanced Features

### Formula Highlighting

Use `\keyfm{...}` to highlight important formulas:

```latex
\keyfm{\oint_S \vec{E} \cdot d\vec{A} = \frac{Q_{enc}}{\epsilon_0}}
```

### Manual Column Breaks

Use `\columnbreak` to force a new column:

```latex
\nsubsection{Last subsection in this column}{...}
\columnbreak
\nsection{First section in the next column}
```

## Examples

### Physics Formulas

```latex
\nsection{Physics}

\nsubsection{Mechanics}{%
Newton's Laws: $F = ma$, $F_{12} = -F_{21}$. Conservation of energy: $E_k + E_p = constant$.
\begin{itemize}
\item Kinetic energy: $E_k = \frac{1}{2}mv^2$
\item Potential energy: $E_p = mgh$
\item Momentum: $p = mv$
\end{itemize}
}
```

### Computer Science

```latex
\nsection{Computer Science}

\nsubsection{Algorithms}{%
Big O notations: $O(1) < O(\log n) < O(n) < O(n \log n) < O(n^2)$.
\begin{itemize}
\item Sorting: Quicksort $O(n \log n)$ average, $O(n^2)$ worst
\item Search: Binary search $O(\log n)$
\item Graph: Dijkstra's $O((V+E)\log V)$
\end{itemize}
}
```

## Troubleshooting

### Content Overflow

If your content doesn't fit on a single page:

1. Reduce the number of columns: `\setcheatsheetcolumns{2}`
2. Decrease font sizes: `\setcheatsheetfontsize{4.5}`
3. Reduce margins: `\setcheatsheetmargin{0.1in}`
4. Make content more compact: `\setcheatsheetdensity{0.5pt}`

### Compilation Errors

1. **Missing brace errors**: Ensure each `\nsubsection{title}{content}` has matching braces.
2. **Package not found**: Verify `cheatsheet.sty` is in the same directory as your `main.tex`.
3. **Undefined control sequence**: Make sure you've placed `\begincheatsheet` after `\begin{document}` and `\endcheatsheet` before `\end{document}`.

## Tips for Better Cheat Sheets

1. Prioritize key information - don't try to include everything
2. Use concise descriptions and formulas
3. Group related concepts together
4. Use itemized lists for better readability
5. Highlight the most important formulas with `\keyfm{}`
6. Balance your columns manually if needed with `\columnbreak`

## License

This package is provided under the MIT License. Feel free to modify and distribute it as needed.

# HFU LaTeX Template for Academic Theses

This LaTeX template complies with the guidelines of Furtwangen University, Faculty of Computer Science for academic theses (March 2023).

## File Structure

```
project/
├── preamble.tex                           # Main LaTeX file
├── bibtex.bib                             # Bibliography and references
├── framework/                             # Framework files
│   ├── titlepage.tex                      # Title page
│   ├── abstract.tex                       # Abstract (English/German)
│   ├── abbreviations.tex                  # List of abbreviations
│   └── declaration_of_authorship.tex      # Declaration of authorship
├── chapters/                              # Folder for chapters
│   ├── 01_introduction.tex                # Chapter 1: Example chapter with basic LaTeX structure
│   ├── 02_fundamentals.tex                # Chapter 2: Example chapter with basic LaTeX structure
│   └── Other chapters...                  # Additional chapters
└── images/                                # Folder for images
    └── hfu_logo.png                       # HFU logo
```

## LaTeX Setup

1. Install Strawberry Perl.
2. Install MiKTeX as LaTeX distribution.
3. Update MiKTeX by opening the MiKTeX Console, navigating to the Update tab, and clicking on Update now.
4. Start your favorite LaTeX editor (I recommend VS Code or IntelliJ IDEA with the LaTeX plugin).

## Customization

### 1. Adjust Metadata (preamble.tex)
```latex
\newcommand{\thesistype}{Projektarbeit/Praxissemesterbericht/Bachelorarbeit/Masterarbeit}
\newcommand{\studyProgram}{Informatik}
\newcommand{\thesistitle}{Title of the Thesis}
\newcommand{\thesissubtitle}{Subtitle of the Thesis}
\newcommand{\supervisorname}{Prof. Dr. Supervisor Name}
\newcommand{\cosupervisorname}{Prof. Dr. Co-Supervisor Name}
\newcommand{\deadline}{\today}

\newcommand{\authorname}{Your Name}
\newcommand{\matriculationNumber}{xxxxxx}
\newcommand{\streetName}{Street Name, House Number}
\newcommand{\postalCode}{12345}
\newcommand{\city}{City Name}
\newcommand{\mail}{user-name@stud.hs-furtwangen.de}
```

### 2. Choose Citation Style
**IEEE:**
```latex
\usepackage[backend=biber,style=ieee,sorting=none]{biblatex}
```

**APA:**
```latex
\usepackage[backend=biber,style=apa]{biblatex}
```

### 3. Create Chapters
Create separate .tex files for each chapter in the `chapters/` folder and include them in main.tex:
```latex
\input{chapters/01_introduction}
```

## Custom Commands

The template provides several custom commands for consistency:

### Reference Commands
```latex
\figureref{fig:label}      % Bild 1.2
\tableref{tab:label}       % Tabelle 1.2
\chapterref{chap:label}    % Kapitel 1
\sectionref{sec:label}     % Absatz 1.2
\equationref{eq:label}     % Gleichung 1.2
```

### Page Commands
```latex
\newchapterpage            % New page for chapters, continues at the next page on the top left
\newsectionpage            % New page for sections, continues at the next page
\blankpage                 % Insert blank page
```

### Text Formatting
```latex
\emphtext{important}      % Bold emphasis
\codetext{variable}       % Monospace for code
```

## Formatting Guidelines

### Font Sizes (HFU compliant)
- **Title:** 22pt, bold
- **Main chapters:** 14pt, bold
- **Subchapters:** 12pt, bold
- **Body text:** 12pt
- **Footnotes:** 10pt

### Layout
- **Margins:** Inner 4cm (incl. binding), Outer 2.5cm, Top 3cm, Bottom 2cm
- **Line spacing:** 1.5 for body text
- **Text alignment:** Justified
- **Main chapters:** Start on right page

### Headers
- Left/Inner: Chapter title
- Right/Outer: Page number
- Horizontal line separator

## Language Settings

- **Primary language:** German (for HFU requirements)
- **Secondary language:** English
- **Declaration:** Both English and German versions included
- **Abstract:** Both languages as per HFU guidelines

### Language Commands
```latex
\selectlanguage{english}   % Switch to English
\selectlanguage{ngerman}   % Switch to German, default
```

## Special Features

### Page Numbering
- **Title page:** No page number
- **Front matter:** Roman numerals (I, II, III, ...)
- **Main matter:** Arabic numerals (1, 2, 3, ...)

### Lists and Tables
- Table of contents: Maximum 3 hierarchy levels
- List of figures: Only if figures present
- List of tables: Only if tables present
- List of abbreviations: Always required

### Citations
- **Direct quotes:** Use sparingly, in quotation marks
- **Indirect quotes:** Preferred in technical work
- **Source references:** After each cited thought, not at end of paragraphs

## Helpful Features

### Bibliography Management
Add sources to `bibtext.bib` and cite with:
```latex
\cite{key}                 % Normal citation
\textcite{key}             % Author as part of sentence
```

### Code Listings
```latex
\begin{lstlisting}[language=Python, caption=My Code, label=lst:example]
def hello_world():
    print("Hello, World!")
\end{lstlisting}
```

### Figures and Tables
```latex
% Figure
\begin{figure}[htbp]
    \centering
    \includegraphics[width=0.8\textwidth]{images/example.png}
    \caption{Example figure}
    \label{fig:example}
\end{figure}

% Table
\begin{table}[htbp]
    \centering
    \caption{Example table}
    \label{tab:example}
    \begin{tabular}{@{}lcc@{}}
        \toprule
        Item & Value 1 & Value 2 \\
        \midrule
        A & 1 & 2 \\
        B & 3 & 4 \\
        \bottomrule
    \end{tabular}
\end{table}
```

## Quick Start

1. Adjust metadata in `main.tex`
2. Create chapters in `chapters/` folder
3. Add literature to `bibtext.bib`
4. Compile using the `build.ps1` script or manually in your LaTeX editor

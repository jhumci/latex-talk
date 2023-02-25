# Introduction to LaTeX

## Slides
Slides and scriptum can be found in the Sakai Courses. The structure is build on the examples from the courses handboook and on a talk by [Malte Schmitz](https://github.com/malteschmitz/LaTeX-talk).

## What is LaTeX?
*see Slides*

### Licencing 
LaTeX is [free software](https://www.LaTeX-project.org/lppl/) and can be used free of charge.
This is true for most software that exists in the LaTeX ecosystem. However, there are [exceptions](https://www.overleaf.com/user/subscription/plans).



### Online with Overleaf
LaTeX can be used online with [Overleaf](https://www.overleaf.com/) without local installation. Overleaf is perfect for getting started. Collaboration via document sharing is also integrated.


### Local Installation
To work locally with LaTeX, a LaTeX distribution and an editor must be installed.

#### LaTeX distributions
The LaTeX distribution contains the compiler and various LaTeX packages. The distributions are relatively large, because a lot of packages are included.

- Windows: [MikTeX](https://miktex.org/howto/install-miktex)
- Mac: MacTeX
- Linux: TeX Live

*We recommend installing MikTeX*

#### Editors

LaTeX files are text files and can be edited accordingly with any text editor. However, special editors simplify the work enormously.

- TeXworks (Windows, Linux, Mac) is free and already included in the three popular LaTeX distributions MiKTeX, MacTeX and TeX Live.
- TeXshop (Mac) is a free LaTeX editor specifically for Mac and already included in MacTeX.
- Texmaker (Windows, Linux, Mac) is a free, modern and cross-platform LaTeX editor.
- [TeXstudio](https://www.texstudio.org/) (Windows, Linux, Mac) is a fork of Texmaker.
- Kile (Linux) is a free development environment for LaTeX under KDE.
- TeXnicCenter (Windows) is a free development environment for LaTeX under Windows.

*We recommend installing TeXstudio*

### Using LaTeX

#### Minimal Document

Create a file ```article.txt``` containing

```
\documentclass{scrartcl}

\begin{document}
    This is a nice article.
\end{document}
```

After compiling the file (green arrow) a bunch of other files will be created. One file is the finished pdf. 
If the compilation does not succede there es in error message. There are also warning, if something is off. 

#### Structuring in LaTeX

happens with different commands, markups and environments

##### Commands in LaTeX

are special keywords always staring with ```\``` . For instance ```\\``` forces a new line.
If You start typing ```\``` TexStudio will suggest fitting commands.

```
\documentclass{scrartcl}
\begin{document}
    This is a nice article. \\ In which we force a new line.
\end{document}
```

Therefore, be careful when using ```\```. 

```\test``` ist not known by LaTeX as an command and therefore throws an error during compilation. Use ```%``` for comments. Everything behind a ```%``` is ignored by the compiler.

```
\documentclass{scrartcl}
\begin{document}
    This is a nice article. \\ In which we force a new line.
\end{document}

% \test
```

```
\documentclass{scrartcl}
\begin{document}
    This is a nice article. \\ In which we force a new line.
    It      does        not     matter      how     many    blanks   we     use.
\end{document}
```


##### Markups in LaTeX

```
\documentclass{scrartcl}
\begin{document}
    This is a \emph{nice} article. \\ In which we force a new line.
\end{document}
```


There is more we can do with different markups:

```
\documentclass{scrartcl}
\begin{document}
    This is a \textit{nice} \textbf{article}.
\end{document}
```



##### Environments in LaTeX

are longer structures in the text, that behave in special ways. They start and end with special keywords (```\begin{<name>}``` and ```\end{<name>}```). Certain commands and markups only work in special environments.

###### Lists

are a simple selection on bullet points. Note that we use indentation to structure the source code. This is only for the reader.

```

\begin{itemize}
    \item Frist
    \item Second
    \item Third
    \end{itemize}
```

Lists can be stacked and there is a special environment for numbered lists (```enumerate```):

```
\begin{enumerate}
	\item Manche mögen die Grünen am liebsten,
	\item manche die Gelben.
	\item Ich mag am liebsten die Roten.
	\begin{enumerate}
		\item Sie glühen richtig rot,
		\item und ihr Himbeergeschmack fährt wie Napalm über
		die Geschmacksknospen.
	\end{enumerate}
\end{enumerate}
```

Another special list is a ```description```, which takes an word as an option ```[<option>]```. This word is highlighted:

```
\begin{description}
	\item[Das Schlagwort] steht am Anfang einer Zeile und wird
	hervorgehoben, während der zugehörige
	\item[Text] dahinter in normaler Schrift erscheint.
\end{description}
```

##### Headings

We define the structure of a text by adding different levels of headings.

```
\section{Gummibärchen}

\subsection{Forscherdrang}

\section{Der Blindtext-Fall}

\section{Weit hinter den Wortbergen}
```

###### Table Of Content

These are used to automatically generate a table of content:

```
\tableofcontents
Manchmal will man eine Überschrift im Inhaltsverzeichnis verkürzt darstellen:

% We can define a shorter title for the TOC
\subsection[Short Title]{This a a very long title line}

% We can force the TOC to ignore headings
\subsection*{This won't be shown and does not get a number}
```

###### Title Page

There are different things, we can use  to improve the structure of our article. We can define a title page:

```
\begin{document}
	
\title{Our first paper}
\author{Julian Huber}
\date{Winter 2022}
\maketitle
\end{document}
```

###### Abstract

Also an abstract that come before the main body of the article:

```
\abstract{This is the abstract}
\section{Commands in LaTeX}
```

#### Layout in LaTeX

is independent from the content and the structure. We can change the appeance with just one line:

```
%\documentclass{scrartcl}
\documentclass[11 pt, a4paper,twosided,titlepage]{scrartcl}
\begin{document}
...
\end{document}
```

This happens before the main body of the document in the preamble. 

## Structure of a Document

*see Slides*

### Advanced 

to use the full potential of LaTeX for technical and scientific type setting there are few more things one has to know...

#### Packages

Packages provide additional functionalities that the compiler can use. The LaTeX distribution maintains the packages.
Be aware, that there is a thing call package collision where two packages do not work if they are integrated at the same time.
Only load the packages You really need.


```
\usepackage{xcolor}


\begin{document}
We can use \textcolor{orange}{colored text} now.
\end{document}
```

#### Important Packages


```
\usepackage[utf8]{inputenc}
%UTF-8 for text encoding

\usepackage[ngerman]{babel}
%German hyphenation, date formats etc.

\usepackage[T1]{fontenc}
%improves text encoding for western european languages

\usepackage{lmodern}
%more modern fonts

\usepackage{xcolor}
%adds command \textcolor fo colour

\usepackage{graphicx}
%adds command \includegraphics for figures

\usepackage[german=guillemets]{csquotes}
%adds command \enquote for parentheses

\usepackage{amsmath}
%adds environment align for aligned mathematical formulas

\usepackage[breaklinks=true]{hyperref}
%improves pdf creation (e.g. hyperlinks)

\usepackage{booktabs}
%nicer tables

```

## Modular Documents and Special Environments

### Modular Documents

Text from other ```.tex```-files is easy to integrate:

```
\input{sub_article}

\include{subfolder/sub_article}
```

### Special Environments

#### Figures

are integrated by the ```figure```-environment. The option ```[h]``` defines where the figures are placed. Figures are floating in the text document. The typesetting will place them in the end. Do not waste time forcing figures to positions before the rest of the document is finalized. 

There is a caption and a unique label in each figure. Use the label to reference the figure in the text.

The command ```\includegraphics``` defines the size of the figure via an option. 

```

\usepackage{graphicx}

\begin{document}

Figure~\ref{fig:AbleitungHyperbel} describes a hyperbola.

\begin{figure}[h]
	\centering
	\includegraphics[width=0.5\textwidth]{HyperbelAbleitung-eps-converted-to.pdf}
	\label{fig:AbleitungHyperbel}
	\caption[The figure caption comes below the figure.}
\end{figure}

\end{document}
```

#### Tables

can be a little tricky. Some tools (e.g. Python pandas) directly generate LaTeX tables. The online-tool [Tables Generator](https://www.tablesgenerator.com/) can also help with the task.


```
\usepackage{booktabs}

\begin{document}

\begin{table}[ht]
	\begin{center}
		\caption{The table caption comes above the table.}
		\begin{tabular}{l|cr}
			\toprule
			Spalte 1 & Spalte 2 & Spalte 3\\
			\midrule
			AA & AB & AC\\
			BA & BB & BC\\
			CA & CB & CC\\
			\bottomrule
		\end{tabular}
	\end{center}
\end{table}

\end{document}
```



#### Math

#### Math Environment

creates a numbered equation that has a label that can be referenced:

```
\usepackage{amsmath}													
\usepackage{amsfonts}													
\usepackage{amssymb}
\begin{document}
    \begin{equation}
        x=2
    \label{eq:x_is_two}
    \end{equation}
\end{document}

```

#### Listings

allow longer expressions, e.g., calculations:

```
\usepackage{listings}
\begin{document}
    \begin{lstlisting}[caption = Wege in den Mathematikmodus, label = ReininMathe]
        Mittels \emph{equation}-Umgebung:
        \begin{equation}
            a^2+b^2=c^2
            \label{Pythagoras}
        \end{equation}
        Mittels einfachen Dollarklammern: $a^2+b^2=c^2$\\
        Mittels doppelten Dollarklammern: $$a^2+b^2=c^2$$
    \end{lstlisting}
\end{document}
```

```$``` or ```$$```  are other ways to access the math mode.


#### Notation

allows for nearly every formula. Special operators and Greek alphabeth is included:
```
$$x = 5\cdot 2^{20} \cdot \frac{\Omega}{\omega}$$
$$\sum_{i=0}^{n}(X_i)$$
$$1^{2^3}$$
$$0= \sin{x} + \ln{x}$$
$$ \vec{V} = \hat{u}$$
```

#### Physical  Quantities

note that the convention is to write variables in italic but not the units:

```$l= 10 \text{m}$``` results in $l= 10 \text{m}$

The packages [SI-units](https://www.namsu.de/Extra/pakete/Siunitx.html) makes this much easier

```
\usepackage{siunitx}
\sisetup{exponent-product = \cdot, output-product = \cdot}
\begin{document}
    $$\text{k}=\SI{1.38e-23}{\joule \per\kelvin}$$
    $h=\SI{6.626e-34}{\joule \second}$\\
    $$\varepsilon_0=\SI[per-mode=fraction]{8.854e-12}{\ampere \second \per\volt \per\meter}$$
    $\SI{8000}{\kilo\gram\of{Metall} \per\hour}$\\
\end{document}

```

## Bibliographies

citations are build on special data bases stored in a bib file. You can get the data form different [sources](https://scholar.google.com/scholar?hl=de&as_sdt=0%2C5&q=julian+huber&btnG=&oq=julia). You can copy this directly to the bib file or use a special [program](https://www.jabref.org/) to manage your database.

This is how a bib file with only one article looks:


```
@article{lemola2007maternal,
  title={Maternal adjustment five months after birth: the impact of the subjective experience of childbirth and emotional support from the partner},
  author={Lemola, Sakari and Stadlmayr, Werner and Grob, Alexander},
  journal={Journal of reproductive and infant psychology},
  volume={25},
  number={3},
  pages={190--202},
  year={2007},
  publisher={Taylor \& Francis}
}
```

Using a bib-file makes it easy to manage citations independent from the required style. 

```
% defines how citations look
\usepackage [super , square , sort&compress ]{natbib}

\begin{document}
    % citation
    This is a \emph{nice} article \cite{lemola2007maternal}.

% defined how the bibliography looks
\bibliographystyle{alphadin}  

% defines the bib file and places a bibliography
\bibliography{bib_article}
\end{document}
```

Caution: There are [different](https://tex.stackexchange.com/questions/25701/bibtex-vs-biber-and-biblatex-vs-natbib) packages for managing bibliographies (i.e.,biblatex and natbib). Here, we use natbib!

## Addendum

- For trouble shooting:
    - google for error messages
    - try to build a minimal example of what You want to compile and increase complexity step by step
- [overleaf](https://de.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes) provides a useful documentation.

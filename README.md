## My custom (Xe)LaTex things

Some stuff I've collected to typeset things the way I like.

I put these files inside of `~/Library/texmf/`, and reference them in general
(Xe)LaTeX documents.

That is, they could be cloned like this:

```bash
mkdir ~/Library/texmf
git clone https://github.com/postylem/tex_utils.git ~/Library/texmf/custom
```

and then used in a .tex file like:

```latex
\documentclass{article}

\usepackage[%
natbib=true,backend=biber,sorting=nymdt,%
citestyle=authoryear,bibstyle=authoryear,%
url=false,doi=false,isbn=false%
]{biblatex}

\begin{filecontents}{\jobname.bib}
@article{Nymous2032,
  title={Something},
  author={Ann O Nymous},
  journal={Fake Journal},
  volume={1},
  pages={1--9},
  year={2032},
  url={http://www.zombo.com}
}
\end{filecontents}
\addbibresource{\jobname.bib}

% jbib_links: imports xcolor, imports/configs hyperref, defines nymdt sorting:
\input{/Users/j/Library/texmf/custom/jbib_links.tex}
\usepackage{cleveref} % must come after importing hyperref

% general formatting things. Imports packages contour, ulem
\input{/Users/j/Library/texmf/custom/jformat.tex}

% for a nice box environment 'kast':
\input{/Users/j/Library/texmf/custom/kast.tex}

% for expectation \E{}, entropy \H{}, MI \I{} etc:
\input{/Users/j/Library/texmf/custom/information-theory-operators.tex}

\begin{document}

\title{Test document}
\author{me}

\maketitle

Hello world. Here's an \myuline{underlined thing}, and a citation \citep[see][]{Nymous2032}.

\begin{kast}{A box}
Here is an equation
\[
\I{X:Y} = \H{X} - \H{X\mid Y}
\]
\end{kast}

\printbibliography{}
```

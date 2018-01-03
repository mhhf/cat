# Category Theory study document
This document serves the generation of flashcarts to remember and study
[Category Theory](angg.twu.net/MINICATS/awodey__category_theory.pdf).

## SetUp
1. Install and Get familiar with Anki: http://ankisrs.net/
(I use it on PC + Phone)
2. Install and get familiar with Latex Import: http://reh.math.uni-duesseldorf.de/~zibrowius/LatexNoteImporter/
3. You will need a custom anki not type:
    * create a new custom note type with the name Latex
    * import the `anki.apkg` in your anki
    * from here on you can import `doc.tex` into the cat dec
4. Sync & enjoy

## Usage

1. sync the git repo or modify the `doc.tex` file
2. Anki: File > Import `doc.tex` into `cat`

All anki cards have to be in the following format with an **unique** UUID:

```
\begin{note}
  \xplain{<UUID>}
  \begin{field}
    <Question>
  \end{field} \\
  \noindent\rule[0.5ex]{\linewidth}{1pt}
  \begin{field}
    <Answer>
  \end{field}
\end{note}
```

### VIM
I use the following snippet in ultisnips to generate a card boilerplate:

```
global !p
from uuid import uuid4
def uuid():
	return str(uuid4())
endglobal

snippet note "Anki note" b
\begin{note}
  \xplain{`!p if not snip.c: snip.rv = uuid()`}
  \begin{field}
		${1}
  \end{field}
  \begin{field}
		${2}
  \end{field}
\end{note}

endsnippet
```

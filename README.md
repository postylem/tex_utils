## My custom (Xe)LaTex things

Some stuff I've collected to typeset things the way I like.

I put these files inside of `~/Library/texmf/`, and reference them in general
(Xe)LaTeX documents.

That is, they could be cloned like this:

```bash
mkdir ~/Library/texmf
git clone https://github.com/postylem/tex_utils.git ~/Library/texmf/custom
```

and then used in a LaTeX file.
See example [`tex_utils_demo.tex`](demo/tex_utils_demo.tex)
(I compile with `latexmk -xelatex`).

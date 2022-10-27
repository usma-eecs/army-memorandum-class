# Army Memorandum LaTeX Class and Pandoc Template

Provides a basic AR 25-50 memo in latex.

## Setup

- Requires LuaLaTeX or XeLaTeX for font handling.
- Linux: install Arial font ("preferred" by AR 25-50 1-17)

Debian:

```bash
sudo apt-get install ttf-mscorefonts-installer
sudo fc-cache
fc-match Arial
```

## Usage

See `main.tex` and `main.md`.

If using Markdown, please follow the [Pandoc Markdown](https://pandoc.org/MANUAL.html#pandocs-markdown) standards.
In particular, it is important that lists use `#.` to denote each item to avoid overriding the Army memorandum template Latex styling for lists.

A minimum set of declarations are required for the office-symbol, subject, signature block, etc.
After these options, within `\begin{document}` ... `\end{document}`, the structure is based on an `enumerate` list.

## Compile

Currently the `Makefile` compiles the `main.md` to `out.pdf`.
TODO: build a more useful `Makefile`.

### LaTeX

```bash
latexmk -pdf -pvc -lualatex main.tex
```

### Markdown

```bash
pandoc -o out.pdf --pdf-engine=xelatex --template=default.latex main.md
```

### Overleaf

1. Download the file that starts “DOD” from GitHub – this is the image logo that appears in the upper left corner
2. Upload the DOD file into your overleaf project
3. Copy in the `armymemo.cls` file from GitHub into a new file of the same name in your overleaf project
4. Copy in the `main.tex` file from GitHub into the existing file of that name in your overleaf project – replacing the existing content of `main.tex`
5. Click the overleaf logo in the upper left corner of the overleaf web page and select the XeLaTex compiler in the settings.
6. Click ***“Recompile”*** button in overleaf.
7. You should see the memo template generate

---

Pandoc LaTeX template copyright (c) 2020 Nathaniel Stickney.

Army memorandum LaTeX class copyright (c) 2011 George Allen, all rights reserved.

This program is free software; you can redistribute it and/or modify it under
the terms of the GNU General Public License as published by the Free Software
Foundation; either version 2 of the License, or (at your option) any later
version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with
this program; if not, write to the Free Software Foundation, Inc., 59 Temple
Place, Suite 330, Boston, MA 02111-1307 USA

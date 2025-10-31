
# Circular Text Logo with LaTeX and PSTricks

This repository contains a LaTeX template for creating circular logos or name signs with text along top and bottom arcs, and an optional center text block. It uses **PSTricks** and **pst-text** for text-on-path effects, and optionally **allrunes** for runic characters.

---

## Features

* Top and bottom text along circular arcs
* Optional center text block (multi-line)
* Adjustable circle sizes and text radii
* Fully vector output — scales cleanly for print or web
* Minimal, easy-to-edit template

---

## Requirements

You need a LaTeX distribution (TeX Live, MacTeX, MiKTeX) with the following packages:

* `pstricks`
* `pst-text`
* `xcolor`
* `graphicx`
* `amssymb`
* `allrunes` (optional, only if you use `\textara{}`)

**Important:** PSTricks relies on PostScript, so **do not compile with `pdflatex`**. Use the LaTeX → DVI → PS → PDF workflow.

On Ubuntu, you can install the required packages using:

```
sudo apt install texlive texlive-latex-extra texlive-pstricks texlive-fonts-recommended
# add texlive-fonts-extra if you need extra fonts such as allrunes
```

---

## How to Compile

### Command Line

From the repository directory, run:

1. `latex circular_logo.tex` → produces `circular_logo.dvi`
2. `dvips circular_logo.dvi` → produces `circular_logo.ps`
3. `ps2pdf circular_logo.ps` → produces `circular_logo.pdf`

This produces a high-quality PDF suitable for printing or digital use.

### Using an Editor (Texmaker / TeXstudio)

1. Configure a Quick Build chain:

   * LaTeX → DVI
   * DVI → PS
   * PS → PDF

2. Run Quick Build or execute each step manually.

### Optional/Advanced: Makefile

You can create a Makefile to automate the build process:

```
TEX = circular_logo
all:
    latex $(TEX).tex
    dvips $(TEX).dvi
    ps2pdf $(TEX).ps

clean:
    rm -f $(TEX).aux $(TEX).log $(TEX).dvi $(TEX).ps $(TEX).pdf
```

Then run `make` to build the PDF.

---

## Template Overview

* **Circles (guids):** `\pscircle[linewidth=1pt,linecolor=green](0,0){3}` draws the outer circle of radius 3, and `\pscircle[linewidth=1pt,linecolor=purple](0,0){2.5}` draws the inner circle of radius 2.5. You can change linewidth/thickness, linecolors (remove for black) or radii. You can also simply delete or comment (with %) to remove one or both circles if desired.

* **Arc radius:** the distance from the center of the logo to the text along the arc (e.g., `2.75`). Adjust to move text inward or outward.

* **Vertical offset:** each `\pstextpath` has a coordinate like `(0,-0.15)` or `(0,-0.1)` to nudge the text relative to the arc. This ensures the path runs through the middle of the text. You may need to adjust this if you change font size or style.

* **Top text mirroring:** `\scalebox{1}[-1]{...}` flips the text vertically so it reads upright along the top arc. The bottom arc usually does not need mirroring.

* **Font and color:** use standard LaTeX commands like `\textbf{}`, `\textit{}`, `\textcolor{red}{...}`, and `\mathbb{...}`.

* **Runes:** if using the `allrunes` package, you can include runic letters with `\textara{}`. You can use different rune sets or look for other languages.

---

## Example Adjustments

* Move both text tracks farther from the center by increasing the arc radius.
* Adjust how text intersects the path by changing the vertical offset.
* Change font size and color to suit your design.
* Hide (guide) circles by commenting out the green/purple `\pscircle` lines once text placement is finalized.

---

## Troubleshooting

* **PSTricks commands undefined:** you ran `pdflatex`. Use the DVI → PS → PDF workflow instead.
* **Missing package:** install it via your OS package manager or TeX package manager.
* **Text alignment off after changing font size:** tweak the vertical offset `(0,y)` and/or use `\raisebox{...}{...}` for fine adjustments.

---

## License

MIT — free to use, modify, and redistribute.

---

## Author

Dan McNeill — 2025

---

## Quick Start

1. Edit `circular_logo.tex` to set your top, center, and bottom text.
2. Compile using the workflow above.
3. Optionally hide the guide circles once you are happy with placement.
4. Enjoy your circular logo!

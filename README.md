# sscita-assembly-biorxiv

This repository contains the LaTeX manuscript for the updated chromosome-level genome assembly of *Sporisorium scitamineum*.

## Automated Building

This repository is configured with GitHub Actions to automatically build the LaTeX document into a PDF whenever changes are pushed to the main branch.

### Workflows

1. **build-latex.yml**: Basic workflow that compiles the LaTeX document and uploads the PDF as an artifact
2. **build-and-release.yml**: Enhanced workflow that also creates releases when tags are pushed

### Building Locally

To build the document locally, you need a LaTeX distribution with the following packages:
- texlive-latex-base
- texlive-latex-extra
- texlive-fonts-recommended
- texlive-fonts-extra
- texlive-bibtex-extra
- texlive-science
- texlive-publishers

Then run:
```bash
cd src
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

### Creating a Release

To create a release with the compiled PDF:
1. Tag your commit: `git tag v1.0.0`
2. Push the tag: `git push origin v1.0.0`
3. The workflow will automatically create a GitHub release with the compiled PDF

### Files

- `src/main.tex`: Main LaTeX document
- `src/references.bib`: Bibliography file
- `src/theme.cls`: ASCE journal document class (ascelike-new)
- `src/theme.bst`: Bibliography style
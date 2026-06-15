# QuartoAutomation

This repository contains a single Quarto manuscript source in the repository root: `abstract.qmd`.

The project is configured to render that file to PDF. The GitHub Actions workflow in `.github/workflows/compile-quarto.yml` automatically runs on changes to root-level `.qmd`, `.bib`, or `_quarto.yml` files, finds the only `.qmd` file in the repository root, and compiles it to `abstract.pdf`.

## What it does

- Keeps the manuscript in one root Quarto file.
- Renders the source to PDF with Quarto.
- Uploads the generated PDF as a GitHub Actions artifact on every matching push or pull request.

## Local build

To render the document locally, run:

```bash
quarto render abstract.qmd --to pdf
```

The output PDF is written next to the source file.

## GitHub Actions

The workflow is set up to:

1. Check out the repository.
2. Install Quarto and Pandoc.
3. Detect the single `.qmd` file in the repository root.
4. Render it to PDF.
5. Upload the resulting PDF artifact.

## Project files

- `abstract.qmd`: main Quarto source document.
- `abstract.pdf`: compiled PDF output.
- `abstract.tex`: LaTeX output kept by Quarto.
- `non_compiled_files/presentation.qmd`: additional Quarto material not compiled by the root workflow.
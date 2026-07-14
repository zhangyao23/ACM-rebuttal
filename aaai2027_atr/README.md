# AAAI-27 ATR Manuscript

This directory is the canonical Git-tracked working project for the AAAI-27 revision of ATR.

## Entry Point

- Main source: `main.tex`
- Official style: `aaai2027.sty`, `aaai2027.bst`
- Section sources: `sections/`
- Figures: `figures/`
- Bibliography: `references.bib`
- Official checklist template: `ReproducibilityChecklist.tex`

## Current Scientific Positioning

The manuscript centers on **training-free selective re-reading through content-aware intra-video retrieval**:

1. Scout searches the complete video for candidate evidence.
2. Sniper jointly receives the same complete video and the retrieved clip.
3. Matched controls distinguish content selection from an extra call, extra tokens, or an arbitrary clip.
4. Source-2 removal tests whether the final decision actually uses the retrieved evidence.
5. FNR/FPR and efficiency are reported as deployment operating points.

`Asymmetric Causal Expansion (ACE)` is no longer treated as a method component. The frozen `10/2` rule is described only as temporal context padding; equal-budget controls show that `10/2` and `2/10` have identical balanced accuracy on the paired subset.

## Migration Status

The AAAI-27 format, revised title, abstract, introduction contributions, method padding terminology, and E10 padding table are in place. The remaining manuscript pass must reorganize Results around matched controls and faithfulness, compress defensive discussion, redesign the framework figure, and complete the official reproducibility checklist.

The ACM source remains unchanged in the parent workspace and should be treated as historical input, not as the canonical AAAI manuscript.

## Local Build

During authoring, the manuscript is split with `\input`. Before final source submission, it must be flattened if the AAAI submission portal enforces the Author Kit's single-source requirement.

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

Do not commit generated LaTeX auxiliary files or PDFs unless a reviewed release artifact is explicitly requested.

# Reading the Benchmark Table

A 12-slide guide to interpreting AI model evaluation scores, built around the
comparison table from the Claude Opus 5 System Card (July 2026).

**Live deck → [linusquan.github.io/modelbenchmark](https://linusquan.github.io/modelbenchmark/)**

## What it covers

- Why benchmark scores can't be compared across categories, and when they can be compared across models
- A cross-check of Anthropic's reported GPT-5.6 Sol numbers against OpenAI's own published figures
- The three scoring paradigms (binary pass/fail, efficiency ratio, rubric) and why a rubric score and a pass rate aren't the same kind of number
- Per-category methodology: coding, ARC-AGI-3, GDPval-AA, agentic search, long-chain business workflows
- The systematic error every benchmark carries — contamination, wrong ground truth, leaky scorers, composite indices that hide regressions

## Running it

```bash
npm install
npm run dev      # live editing at localhost:3030
npm run build    # static site → dist/
npm run export   # PDF
```

Built with [Slidev](https://sli.dev). Content lives in `slides.md`; theming in `style.css`.

## Two formats

| File | Use |
|---|---|
| `slides.md` | The Slidev deck — presenter mode, overview, PDF export, easy editing |
| `benchmark-deck.html` | Standalone single-file version — open directly in a browser, no build step |

Both carry the same content. Edits need applying to both.

## Deployment

Pushing to `main` triggers `.github/workflows/deploy.yml`, which builds the
static site and publishes it to GitHub Pages.

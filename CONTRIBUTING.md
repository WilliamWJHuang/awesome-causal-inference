# Contributing

Thanks for helping make this useful. The goal is not to collect every causal inference link on the internet. The goal is a compact, high-signal guide that helps people do better causal work.

## What Belongs

Good additions usually satisfy at least one of these:

- They help define a causal estimand or research design.
- They teach identification assumptions, not just estimation mechanics.
- They explain diagnostics, sensitivity analysis, robustness, uncertainty, or failure modes.
- They provide maintained software for experiments, quasi-experiments, causal ML, causal discovery, or design diagnosis.
- They are a canonical book, course, paper, package, benchmark, or serious technical industry writeup.

## What Usually Does Not Belong

- Generic blog posts that say "correlation is not causation" without adding technical substance.
- Vendor pages that mostly sell a product.
- Abandoned packages unless they are historically important.
- Resources that present causal estimates without discussing assumptions.
- Duplicate links to the same underlying resource.

## Pull Request Format

For each new resource, include:

- The resource name and canonical URL.
- One sentence explaining what it is useful for.
- The category where it belongs.
- Any caveat readers should know, such as "experimental", "dormant", "requires strong ignorability", or "focused on linear models".

Use this format in the README:

```markdown
- [Resource Name](https://example.com/) - Short, concrete description.
```

## Quality Bar

Please keep descriptions factual and modest. Do not call a method "best", "state of the art", or "unbiased" unless the statement is scoped to assumptions and supported by the linked source.

If a resource is about observational causal inference, the description should not imply that software alone solves confounding. If a resource is about experiments, mention important design issues when relevant: interference, noncompliance, attrition, exposure logging, novelty effects, guardrails, sample ratio mismatch, or metric validity.

## Link Preferences

Prefer links in this order:

1. Official documentation or project page.
2. Publisher, journal, arXiv, SSRN, NBER, or author page.
3. GitHub repository.
4. Stable institutional page.

Avoid link shorteners and scraped mirrors.


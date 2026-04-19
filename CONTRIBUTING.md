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
- The category where it belongs.
- The causal question, design, estimand, assumption, diagnostic, or failure mode it helps with.
- Why it improves the list compared with nearby resources already included.
- Any caveat readers should know, such as "experimental", "dormant", "requires strong ignorability", "focused on linear models", or "easy to misuse without a credible design".

Use this format in the README:

```markdown
- [Resource Name](https://example.com/) - Short, concrete description.
```

Descriptions should be one sentence when possible. If a caveat is important enough to mention, keep it in the description rather than hiding it in the pull request.

## Resource Review Questions

Before opening a pull request, answer these for each resource:

- What causal question does this help answer?
- What design or estimand does it support?
- What assumptions does it clarify?
- What diagnostics, robustness checks, falsification tests, or failure modes does it teach?
- Why is it better than, or complementary to, nearby resources already listed?

These answers do not all need to appear in the README, but they should be clear in the pull request or issue. See [REVIEWING.md](REVIEWING.md) for the review standard maintainers use.

## Quality Bar

Please keep descriptions factual and modest. Do not call a method "best", "state of the art", or "unbiased" unless the statement is scoped to assumptions and supported by the linked source.

If a resource is about observational causal inference, the description should not imply that software alone solves confounding. If a resource is about experiments, mention important design issues when relevant: interference, noncompliance, attrition, exposure logging, novelty effects, guardrails, sample ratio mismatch, or metric validity.

If a resource is mainly a tutorial, make sure it teaches design logic rather than only estimator syntax. If it is mainly a paper, prefer the author, publisher, journal, arXiv, NBER, SSRN, or stable institutional page over a mirror.

## Link Preferences

Prefer links in this order:

1. Official documentation or project page.
2. Publisher, journal, arXiv, SSRN, NBER, or author page.
3. GitHub repository.
4. Stable institutional page.

Avoid link shorteners and scraped mirrors.

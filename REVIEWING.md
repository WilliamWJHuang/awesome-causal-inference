# Reviewing Resources

This project is selective by design. A resource should help someone make a causal claim more precise, more credible, or easier to critique.

## Review Standard

Approve a resource when it does at least one of these well:

- Defines a causal question, intervention, estimand, or target population.
- Explains why a comparison identifies a counterfactual.
- States assumptions clearly enough to challenge them.
- Teaches diagnostics, robustness checks, falsification tests, sensitivity analysis, or failure modes.
- Provides maintained software that supports a credible design workflow.
- Is canonical, historically important, or unusually useful in practice.

Reject or ask for revision when a resource:

- Treats an estimator or package as a substitute for identification.
- Makes causal claims without stating assumptions.
- Is mostly SEO, marketing, or vendor positioning.
- Duplicates a stronger resource already listed.
- Uses vague praise such as "best", "powerful", or "state of the art" without a scoped reason.
- Is too narrow to help readers unless the README description makes that scope explicit.

## Description Standard

README descriptions should be short, factual, and modest. Prefer:

```markdown
- [Resource](https://example.com/) - What it helps with, under what design or assumption, and any important caveat.
```

Avoid descriptions that say only "guide", "overview", "tutorial", or "tool" without naming the causal job it performs.

## Reviewer Questions

Use these questions when reviewing an issue or pull request:

- What causal question does this resource help answer?
- What design family or estimand does it support?
- What assumptions does it make easier to see or test?
- What diagnostics, robustness checks, placebo tests, or sensitivity analyses does it teach?
- How could a reader misuse it?
- Is the linked page canonical and stable?
- Does the README description overclaim?
- Is there already a better resource in the same section?

## Common Revision Requests

- Ask for a more canonical URL.
- Ask for a caveat when a method needs strong ignorability, parallel trends, exclusion, overlap, no interference, pre-treatment covariates, or valid logging propensities.
- Ask for a different section if the proposed placement makes the resource look more general than it is.
- Ask for a shorter description if the entry reads like promotion.
- Ask for a stronger resource if the proposed link is a secondary summary of a canonical paper, book, course, or package.

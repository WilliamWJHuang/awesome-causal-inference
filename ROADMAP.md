# Roadmap

This roadmap keeps future additions focused on causal inference for experimentation and decision-making. Items here should become README resources only when there is a strong, stable, technically useful source to link.

## Seeded, But Worth Deepening

- Variance reduction in online experiments, including CUPED, CUPAC, CUPAC-like prediction covariates, and regression adjustment.
- Sequential testing, alpha spending, always-valid inference, online FDR, and experiment monitoring.
- Experiment health checks, including SRM, A/A tests, guardrail metrics, triggering, exposure logging, metric denominator checks, and launch-decision review.
- Cluster-randomized, geo, marketplace, and split-plot experiment designs.
- Interference, spillovers, network experiments, marketplace feedback loops, and two-sided-platform measurement.
- Classical econometrics, including RDD, event studies, IV/LATE, synthetic control, and staggered DiD diagnostics.
- Target-trial emulation and observational-design resources outside healthcare.
- Missing data, attrition, censoring, Lee bounds, IPCW, principal stratification, and MNAR sensitivity analysis.
- Recommender systems, ranking, ads, logged-policy evaluation, exposure propensities, delayed feedback, and long-horizon product loops.

## Medium Term

- Add more education, labor, healthcare, and public-policy case studies.
- Add resources on transportability, external validity, and treatment-effect generalization.
- Add practical examples of sensitivity analysis, negative-control workflows, and placebo tests.
- Add more experiment platform governance resources, including instrumentation reviews and pre-launch analysis checklists.
- Add short example notebooks only when they clarify design assumptions rather than just demonstrating an estimator API.

## Maintenance

- Keep the README selective rather than comprehensive.
- Prefer official docs, author pages, publisher pages, and maintained repositories.
- Revisit archived or dormant projects periodically.
- Use GitHub issues for proposed additions that need more review.
- Treat link-check and awesome-lint failures as maintenance work, not noise.

## Review Standard

Every new resource should help readers answer at least one of these:

- What is the causal question?
- What is the estimand?
- What identifies the counterfactual?
- What assumptions are required?
- What diagnostics or falsification checks are available?
- What are the important failure modes?

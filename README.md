# Awesome Causal Inference & Experimentation

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

A curated list of practical, research-grade resources for causal inference, experimentation, quasi-experiments, uplift modeling, causal machine learning, and decision-making from data.

Causal inference is not a menu of estimators. The best resources here help you define the estimand, state assumptions, defend identification, run or analyze experiments, test robustness, and communicate uncertainty.

## Scope

This list is meant for people who need to answer questions like:

- Did this product, policy, model, treatment, or intervention cause a change?
- Can we learn from an A/B test, quasi-experiment, rollout, or observational study?
- Which assumptions make the estimate credible, and which assumptions are doing too much work?
- How should we diagnose confounding, selection bias, interference, noncompliance, attrition, metric issues, or treatment heterogeneity?
- Which software is appropriate for a given design?

This repository deliberately emphasizes experimentation and applied decision-making. There are already strong general causal inference lists, so this one should earn its place by being selective, transparent about assumptions, and useful to practitioners.

## Contents

- [Foundations and Books](#foundations-and-books)
- [Courses and Lecture Notes](#courses-and-lecture-notes)
- [Causal Diagrams and Identification](#causal-diagrams-and-identification)
- [Randomized Experiments and A/B Testing](#randomized-experiments-and-ab-testing)
- [Quasi-Experiments and Observational Designs](#quasi-experiments-and-observational-designs)
- [Heterogeneous Effects, Uplift, and Policy Learning](#heterogeneous-effects-uplift-and-policy-learning)
- [Sensitivity, Robustness, and Diagnostics](#sensitivity-robustness-and-diagnostics)
- [Causal Discovery and Time Series](#causal-discovery-and-time-series)
- [Python Libraries](#python-libraries)
- [R Libraries](#r-libraries)
- [Datasets and Benchmarks](#datasets-and-benchmarks)
- [Industry Case Studies](#industry-case-studies)
- [Communities and Related Lists](#communities-and-related-lists)
- [Curation Checklist](#curation-checklist)

## Foundations and Books

- [Causal Inference: What If](https://miguelhernan.org/whatifbook) - Free book by Miguel Hernan and James Robins; especially strong on target trials, longitudinal data, exchangeability, positivity, and consistency.
- [Causal Inference: The Mixtape](https://mixtape.scunning.com/) - Scott Cunningham's applied econometrics book covering regression, matching, IV, DiD, RDD, and synthetic control.
- [The Effect](https://theeffectbook.net/) - Nick Huntington-Klein's accessible research-design-first book with code examples and a strong emphasis on identification.
- [Causal Inference for the Brave and True](https://matheusfacure.github.io/python-causality-handbook/landing-page) - Python-first online book with practical examples across experiments, matching, DiD, RDD, synthetic controls, and causal ML.
- [Introduction to Causal Inference from a Machine Learning Perspective](https://www.bradyneal.com/causal-inference-course) - Brady Neal's course text and lectures bridging graphical models, potential outcomes, and ML.
- [Elements of Causal Inference](https://mitpress.mit.edu/9780262037310/elements-of-causal-inference/) - Peters, Janzing, and Scholkopf on causal discovery, invariance, and structural causal models.
- [Design of Observational Studies](https://link.springer.com/book/10.1007/978-1-4419-1213-8) - Rosenbaum's design-centered treatment of observational studies and sensitivity analysis.
- [Field Experiments](https://wwnorton.com/books/Field-Experiments/) - Gerber and Green on designing and analyzing randomized field experiments.
- [Mostly Harmless Econometrics](https://press.princeton.edu/books/paperback/9780691120355/mostly-harmless-econometrics) - A classic design-based econometrics reference.
- [Mastering 'Metrics](https://press.princeton.edu/books/paperback/9780691152844/mastering-metrics) - A gentler companion focused on core empirical strategies.

## Courses and Lecture Notes

- [Causal Diagrams: Draw Your Assumptions Before Your Conclusions](https://harvardonline.harvard.edu/course/causal-diagrams-draw-your-assumptions-your-conclusions) - Harvard Online course by Miguel Hernan on DAGs, SWIGs, bias, and adjustment.
- [A Crash Course in Causality](https://www.coursera.org/learn/crash-course-in-causality) - University of Pennsylvania course on potential outcomes, DAGs, matching, IPTW, and IV.
- [Causal Inference](https://www.coursera.org/learn/causal-inference) - Columbia/Coursera course covering potential outcomes, ignorability, matching, weighting, and ML extensions.
- [Machine Learning & Causal Inference: A Short Course](https://www.gsb.stanford.edu/faculty-research/labs-initiatives/sil/research/methods/ai-machine-learning/short-course) - Stanford short course on ML for treatment effects, heterogeneity, and treatment assignment policies.
- [Causality, Decision Making, and Data Science](https://stanford-causal-inference-class.github.io/materials.html) - Stanford course materials including randomized experiments, online experiments, IV, DiD, RDD, and policy learning.
- [DoWhy + EconML Tutorial](https://www.pywhy.org/dowhy/v0.14/example_notebooks/tutorial-causalinference-machinelearning-using-dowhy-econml.html) - Hands-on notebook connecting causal assumptions, identification, estimation, and refutation.
- [Mixtape Sessions](https://github.com/Mixtape-Sessions) - Workshop material around modern causal inference and econometric methods.

## Causal Diagrams and Identification

- [DAGitty](https://www.dagitty.net/) - Browser-based tool and R package for drawing and analyzing causal DAGs and adjustment sets.
- [DoWhy](https://www.pywhy.org/dowhy/) - Python library organized around model, identify, estimate, and refute.
- [pgmpy causal inference](https://pgmpy.org/exact_infer/causal.html) - Causal queries, adjustment sets, and do-operator support for graphical models in Python.
- [Tetrad](https://www.cmu.edu/dietrich/causality/tetrad/) - CMU project for graphical causal modeling and causal discovery.
- [Single World Intervention Graphs: A Primer](https://arxiv.org/abs/1301.3908) - Richardson and Robins on SWIGs for counterfactual causal models.
- [A Crash Course in Good and Bad Controls](https://ftp.iza.org/dp13659.pdf) - Cinelli, Forney, and Pearl on when controls help, hurt, or change the estimand.

## Randomized Experiments and A/B Testing

- [Trustworthy Online Controlled Experiments](https://experimentguide.com/) - Kohavi, Tang, and Xu's practical guide to A/B testing, metrics, trustworthiness checks, and experimentation platforms.
- [ExP Platform](https://exp-platform.com/) - Papers and resources from Ronny Kohavi and collaborators on online controlled experiments at scale.
- [Controlled experiments on the web: survey and practical guide](https://link.springer.com/article/10.1007/s10618-008-0114-1) - Open-access survey on web experiments, common pitfalls, and practical design.
- [Online Experimentation at Microsoft](https://www.microsoft.com/en-us/research/?p=696748) - Lessons from Microsoft's experimentation platform and culture.
- [GrowthBook](https://docs.growthbook.io/) - Open-source feature flagging and experimentation platform.
- [PlanOut](https://facebook.github.io/planout/) - Framework for parameterized experiments and random assignment logic.
- [Ax](https://ax.dev/) - Adaptive experimentation and Bayesian optimization platform.
- [DeclareDesign](https://declaredesign.org/r/declaredesign/) - R framework for declaring, simulating, and diagnosing research designs before implementation.
- [randomizr](https://declaredesign.org/r/randomizr/) - R package for random assignment procedures.
- [estimatr](https://declaredesign.org/r/estimatr/) - R package for design-based estimators with robust and clustered standard errors.

## Quasi-Experiments and Observational Designs

- [did](https://bcallaway11.github.io/did/) - R package for modern difference-in-differences with multiple periods and staggered treatment timing.
- [fixest](https://lrberge.github.io/fixest/) - Fast fixed-effects estimation in R, including event-study and DiD workflows.
- [rdrobust](https://rdpackages.github.io/rdrobust/) - Robust inference, bandwidth selection, and plots for regression discontinuity designs.
- [Synth](https://cran.r-project.org/package=Synth) - R implementation of synthetic control methods for comparative case studies.
- [synthdid](https://synth-inference.github.io/synthdid/) - R package for synthetic difference-in-differences.
- [CausalImpact](https://google.github.io/CausalImpact/CausalImpact.html) - Bayesian structural time-series approach for estimating impacts of interventions on time series.
- [MatchIt](https://kosukeimai.github.io/MatchIt/) - R package for matching and preprocessing before causal estimation.
- [WeightIt](https://ngreifer.github.io/WeightIt/) - R package for balancing weights across binary, multi-category, continuous, and longitudinal treatments.
- [cobalt](https://ngreifer.github.io/cobalt/) - Covariate balance diagnostics and Love plots for matching and weighting workflows.

## Heterogeneous Effects, Uplift, and Policy Learning

- [EconML](https://econml.azurewebsites.net/) - Python library from Microsoft Research for CATE estimation, orthogonal ML, causal forests, IV methods, and policy interpretation.
- [CausalML](https://causalml.readthedocs.io/) - Python package for uplift modeling, CATE estimation, meta-learners, causal trees, and model validation.
- [grf](https://grf-labs.github.io/grf/) - R package for generalized random forests, including causal forests and instrumental forests.
- [DoubleML](https://docs.doubleml.org/stable/index.html) - Python and R implementation of double/debiased machine learning.
- [Meta-learners for Estimating Heterogeneous Treatment Effects](https://arxiv.org/abs/1706.03461) - Kunzel et al. paper on S-, T-, X-, and related learners.
- [Generalized Random Forests](https://projecteuclid.org/journals/annals-of-statistics/volume-47/issue-2/Generalized-random-forests/10.1214/18-AOS1709.full) - Athey, Tibshirani, and Wager paper underlying GRF methods.
- [Policy Learning with Observational Data](https://arxiv.org/abs/1702.02896) - Athey and Wager on learning treatment assignment policies.

## Sensitivity, Robustness, and Diagnostics

- [sensemakr](https://github.com/carloscinelli/sensemakr) - R package for omitted-variable-bias sensitivity analysis in linear regression.
- [EValue](https://cran.r-project.org/package=EValue) - R package for E-values and sensitivity analysis for unmeasured confounding.
- [DoWhy refuters](https://www.pywhy.org/dowhy/v0.14/user_guide/refuting_causal_estimates/index.html) - Refutation tests such as placebo treatments, random common causes, and data subsets.
- [EconML sensitivity tools](https://www.pywhy.org/EconML/spec/estimation/dml.html#sensitivity-analysis) - Sensitivity summaries and robustness values for selected orthogonal ML estimators.
- [Making Sense of Sensitivity](https://academic.oup.com/jrsssb/article/82/1/39/7056082) - Cinelli and Hazlett on omitted variable bias sensitivity analysis.
- [A/A tests and sample ratio mismatch](https://exp-platform.com/) - Practical experimentation diagnostics collected by the ExP platform.

## Causal Discovery and Time Series

- [causal-learn](https://causal-learn.readthedocs.io/en/latest/index.html) - Python package for causal discovery, including PC, FCI, GES, LiNGAM-style methods, and independence tests.
- [Tigramite](https://jakobrunge.github.io/tigramite/) - Python package for causal discovery and causal effect estimation in time-series data.
- [DoDiscover](https://github.com/py-why/dodiscover) - Experimental PyWhy library focused on causal discovery workflows.
- [Causal Discovery Toolbox](https://fentechsolutions.github.io/CausalDiscoveryToolbox/html/index.html) - Python toolbox for graph and pairwise causal discovery methods.
- [Causal inference for time series](https://www.nature.com/articles/s43017-023-00431-y) - Review of causal questions, assumptions, and methods for time-series settings.
- [Review of Causal Discovery Methods Based on Graphical Models](https://www.frontiersin.org/articles/10.3389/fgene.2019.00524/full) - Glymour, Zhang, and Spirtes survey.

## Python Libraries

- [PyWhy](https://www.pywhy.org/) - Open-source ecosystem around causal inference, causal discovery, and causal ML.
- [DoWhy](https://www.pywhy.org/dowhy/) - End-to-end causal inference workflow with explicit assumptions and refutation checks.
- [EconML](https://econml.azurewebsites.net/) - Causal ML and heterogeneous treatment effect estimation.
- [CausalML](https://causalml.readthedocs.io/) - Uplift modeling and CATE methods.
- [DoubleML](https://docs.doubleml.org/stable/index.html) - Double/debiased machine learning in Python and R.
- [causal-learn](https://causal-learn.readthedocs.io/en/latest/index.html) - Causal discovery algorithms and independence tests.
- [pgmpy](https://pgmpy.org/) - Probabilistic graphical models with causal inference support.
- [Tigramite](https://jakobrunge.github.io/tigramite/) - Time-series causal discovery and effect estimation.
- [CausalPy](https://causalpy.readthedocs.io/en/latest/) - Bayesian causal inference in Python with PyMC.
- [causallib](https://causallib.readthedocs.io/en/latest/) - Python package for reusable causal inference estimators and evaluation.
- [zEpid](https://zepid.readthedocs.io/en/latest/) - Epidemiology-focused causal inference and survival analysis utilities.

## R Libraries

- [MatchIt](https://kosukeimai.github.io/MatchIt/) - Matching and nonparametric preprocessing.
- [WeightIt](https://ngreifer.github.io/WeightIt/) - Balancing weights for observational studies.
- [cobalt](https://ngreifer.github.io/cobalt/) - Covariate balance diagnostics.
- [grf](https://grf-labs.github.io/grf/) - Generalized random forests and causal forests.
- [DoubleML](https://docs.doubleml.org/stable/index.html) - Double/debiased ML for R and Python.
- [did](https://bcallaway11.github.io/did/) - Modern DiD estimators for multiple periods and groups.
- [fixest](https://lrberge.github.io/fixest/) - High-dimensional fixed-effects estimation.
- [rdrobust](https://rdpackages.github.io/rdrobust/) - Regression discontinuity inference and visualization.
- [Synth](https://cran.r-project.org/package=Synth) - Synthetic control methods.
- [synthdid](https://synth-inference.github.io/synthdid/) - Synthetic DiD.
- [CausalImpact](https://google.github.io/CausalImpact/CausalImpact.html) - Bayesian structural time-series causal impact analysis.
- [sensemakr](https://github.com/carloscinelli/sensemakr) - Omitted-variable-bias sensitivity analysis.
- [dagitty](https://cran.r-project.org/package=dagitty) - R interface to DAGitty.
- [DeclareDesign](https://declaredesign.org/r/declaredesign/) - Declare and diagnose research designs.
- [randomizr](https://declaredesign.org/r/randomizr/) - Random assignment for experiments.
- [estimatr](https://declaredesign.org/r/estimatr/) - Design-based estimators.

## Datasets and Benchmarks

- [ACIC Data Challenge](https://acic2026datachallenge.github.io/) - Semi-synthetic and benchmark data challenges for causal inference methods.
- [CMU causal-learn benchmarks](https://www.cmu.edu/dietrich/causality/causal-learn/) - Benchmark datasets for causal discovery.
- [CauseMe](https://causeme.uv.es/) - Platform for benchmarking causal discovery from time-series data.
- [LaLonde / National Supported Work data](https://users.nber.org/~rdehejia/nswdata.html) - Classic benchmark data for program evaluation and matching.
- [IHDP benchmark](https://www.fredjo.com/) - Common semi-synthetic benchmark for treatment effect estimation.

Benchmarks are useful for debugging and comparison, not proof that a method identifies your real-world causal effect. Treat every benchmark result as conditional on the data-generating process used to create it.

## Industry Case Studies

- [Ocelot: Scaling observational causal inference at LinkedIn](https://www.linkedin.com/blog/engineering/data-science/ocelot-scaling-observational-causal-inference-at-linkedin) - Platform and review process for observational causal studies at LinkedIn.
- [LinkedIn T-REX experimentation infrastructure](https://engineering.linkedin.com/content/engineering/en-us/blog/2020/our-evolution-towards-t-rex--the-prehistory-of-experimentation-i) - Experiment assignment, ramping, and reporting at scale.
- [Experimentation Platform at Netflix: Building Useful Inference](https://research.netflix.com/publication/experimentation-platform-at-netflix-building-useful-inference) - Netflix Research paper on an experimentation platform built for scientific workflows.
- [ExP Platform papers](https://exp-platform.com/) - Microsoft and industry lessons on sample ratio mismatch, metrics, guardrails, and trustworthy online experiments.
- [Experiment like Spotify](https://confidence.spotify.com/blog/experiment-like-spotify) - Spotify's public writing on experimentation tooling and practice.

## Communities and Related Lists

- [PyWhy](https://www.pywhy.org/) - Community and ecosystem for causal machine learning.
- [CAUSALab](https://hsph.harvard.edu/research/causalab/) - Harvard group with books, courses, software, and applied causal inference research.
- [Stanford Causal Science Center](https://datascience.stanford.edu/causal) - Seminars, workshops, and interdisciplinary causal inference resources.
- [Online Causal Inference Seminar](https://datascience.stanford.edu/causal/online-causal-inference-seminars) - Seminar series and recordings from researchers across causal inference.
- [awesome-causal-inference](https://github.com/matteocourthoud/awesome-causal-inference) - Broad existing awesome list of causal inference resources.

## Curation Checklist

Before adding a resource, ask:

- What causal question does this help answer?
- Does it clarify the estimand, identification strategy, assignment mechanism, or diagnosis?
- Are assumptions stated clearly enough to critique?
- Is it maintained, canonical, or historically important?
- Does it include examples, code, proofs, diagnostics, or failure modes?
- Could a reader misuse this resource as an estimator recipe without understanding design?

Prefer official docs, open course pages, peer-reviewed papers, maintained packages, and technically detailed industry writeups. Avoid thin vendor pages, generic SEO content, and resources that imply causal validity without discussing assumptions.

## Contributing

Contributions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request.

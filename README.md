# Awesome Causal Inference for Experimentation [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Link Check](https://github.com/WilliamWJHuang/awesome-causal-inference/actions/workflows/link-check.yml/badge.svg)](https://github.com/WilliamWJHuang/awesome-causal-inference/actions/workflows/link-check.yml)
[![Awesome Lint](https://github.com/WilliamWJHuang/awesome-causal-inference/actions/workflows/awesome-lint.yml/badge.svg)](https://github.com/WilliamWJHuang/awesome-causal-inference/actions/workflows/awesome-lint.yml)

A selective list of resources for causal inference, experimentation, quasi-experiments, uplift modeling, causal machine learning, and decisions from data.

Causal inference is not a menu of estimators. The useful work is in naming the estimand, defending the comparison, checking the assumptions, and saying exactly where the claim could break.

<!--lint disable double-link-->
<!--lint disable awesome-list-item-->

## Contents

- [Scope](#scope)
- [How to Use This List](#how-to-use-this-list)
- [Start Here](#start-here)
- [Starter Paths](#starter-paths)
- [Causal Questions by Design](#causal-questions-by-design)
- [How to Judge a Causal Claim](#how-to-judge-a-causal-claim)
- [Common Failure Modes](#common-failure-modes)
- [Common Bad Claims](#common-bad-claims)
- [Methods Are Not Magic](#methods-are-not-magic)
- [Core Papers](#core-papers)
- [Foundations and Books](#foundations-and-books)
- [Courses and Lecture Notes](#courses-and-lecture-notes)
- [Causal Diagrams and Identification](#causal-diagrams-and-identification)
- [Randomized Experiments and A/B Testing](#randomized-experiments-and-ab-testing)
- [Experiment Health, Guardrails, and SRM](#experiment-health-guardrails-and-srm)
- [Variance Reduction and Sequential Testing](#variance-reduction-and-sequential-testing)
- [Cluster, Network, and Marketplace Experiments](#cluster-network-and-marketplace-experiments)
- [Quasi-Experiments and Observational Designs](#quasi-experiments-and-observational-designs)
- [Target Trials and Observational Design](#target-trials-and-observational-design)
- [Instrumental Variables and Encouragement Designs](#instrumental-variables-and-encouragement-designs)
- [Missing Data, Attrition, and Censoring](#missing-data-attrition-and-censoring)
- [Heterogeneous Effects, Uplift, and Policy Learning](#heterogeneous-effects-uplift-and-policy-learning)
- [Recommender Systems, Ads, and ML Product Loops](#recommender-systems-ads-and-ml-product-loops)
- [Sensitivity, Robustness, and Diagnostics](#sensitivity-robustness-and-diagnostics)
- [Causal Discovery and Time Series](#causal-discovery-and-time-series)
- [Python Libraries](#python-libraries)
- [R Libraries](#r-libraries)
- [Datasets and Benchmarks](#datasets-and-benchmarks)
- [Industry Case Studies](#industry-case-studies)
- [Healthcare and Policy Case Studies](#healthcare-and-policy-case-studies)
- [Communities and Related Lists](#communities-and-related-lists)
- [Curation Checklist](#curation-checklist)

## Scope

Use this repo when the question is causal, not merely predictive:

- Did this product, policy, model, treatment, or intervention cause a change?
- Can we learn from an A/B test, quasi-experiment, rollout, or observational study?
- Which assumptions make the estimate credible, and which assumptions are doing too much work?
- How should we diagnose confounding, selection bias, interference, noncompliance, attrition, metric issues, or treatment heterogeneity?
- Which software is appropriate for a given design?

The emphasis is experimentation and applied decision-making. There are already broad causal inference lists; this one should earn its keep by being selective, explicit about assumptions, and useful at the moment someone has to defend a result.

## How to Use This List

Start with the reason treatment varies. The estimator comes later.

- **Treatment was randomized:** read the experimentation sections first. Check assignment, exposure, sample ratio mismatch, guardrails, peeking, and whether the unit of randomization matches the unit of analysis.
- **Treatment followed a rollout, date, geography, or policy threshold:** start with DiD, event studies, RDD, synthetic control, and pre-treatment fit or pre-trend diagnostics.
- **Treatment was encouraged, nudged, or partly complied with:** use the IV and encouragement-design material. Be precise about the local population whose behavior the instrument moved.
- **Treatment was self-selected in observational data:** draw the DAG, define the target trial if possible, inspect overlap, and treat matching or weighting as preprocessing rather than proof.
- **Units affect one another:** go to cluster, network, marketplace, ads, and recommender-system resources before assuming independent observations.
- **Outcomes disappear or are measured only for survivors/engaged users:** read the missing-data and censoring material before interpreting the main effect.
- **The real question is who benefits:** make the main design credible first, then use heterogeneous-effect, uplift, or policy-learning tools.

Resource tags are intentionally simple:

- `first read` means the best entry point for that topic.
- `core paper` means a foundational or still-cited technical reference.
- `core reference` means a book, course, or collection that is broader than one paper.
- `software` means a package or tool you can use directly.
- `diagnostics` means it helps catch bad assumptions or broken experiments.
- `case study` means an applied example worth reading for practice, not just method names.
- `advanced` means useful, but easy to misuse without the setup.

## Start Here

If you are new to the field, start with design before software:

- **New to causal inference:** [The Effect](https://theeffectbook.net/), [Causal Inference: What If](https://miguelhernan.org/whatifbook), and [DAGitty](https://www.dagitty.net/).
- **Product experimentation:** [Trustworthy Online Controlled Experiments](https://experimentguide.com/), [ExP Platform](https://exp-platform.com/), and [GrowthBook](https://docs.growthbook.io/).
- **Observational product or policy analysis:** [Causal Inference: The Mixtape](https://mixtape.scunning.com/), [MatchIt](https://kosukeimai.github.io/MatchIt/), [WeightIt](https://ngreifer.github.io/WeightIt/), [cobalt](https://ngreifer.github.io/cobalt/), and [did](https://bcallaway11.github.io/did/).
- **Causal machine learning:** [DoWhy](https://www.pywhy.org/dowhy/), [EconML](https://econml.azurewebsites.net/), [DoubleML](https://docs.doubleml.org/stable/index.html), and [grf](https://grf-labs.github.io/grf/).
- **Robustness and critique:** [A Crash Course in Good and Bad Controls](https://ftp.iza.org/dp13659.pdf), [sensemakr](https://github.com/carloscinelli/sensemakr), and [DoWhy refuters](https://www.pywhy.org/dowhy/v0.14/user_guide/refuting_causal_estimates/index.html).

## Starter Paths

- **Product analysts:** start with online experimentation, variance reduction, sample ratio mismatch, guardrail metrics, and the failure modes around peeking, exposure, and interference.
- **Economists and policy researchers:** start with design-based quasi-experiments, IV, DiD, RDD, synthetic control, and sensitivity analysis.
- **ML researchers:** start with identification, CATE, off-policy evaluation, recommendation-as-treatment, and the distinction between predictive performance and causal validity.
- **Epidemiologists and healthcare researchers:** start with target trials, longitudinal causal inference, missing data, censoring, positivity, and sensitivity analysis.
- **Experiment platform builders:** start with assignment, logging, metric validity, CUPED/CUPAC-style variance reduction, sequential monitoring, and review processes.

## Causal Questions by Design

<!--lint disable table-pipe-alignment-->

| Situation | Natural design family | First resources to check |
| --- | --- | --- |
| We randomized users, sessions, markets, or units. | Online experiments, field experiments, A/A tests, guardrails, sequential monitoring. | [Trustworthy Online Controlled Experiments](https://experimentguide.com/), [ExP Platform](https://exp-platform.com/), [Field Experiments](https://wwnorton.com/books/Field-Experiments/), [randomizr](https://declaredesign.org/r/randomizr/), [estimatr](https://declaredesign.org/r/estimatr/) |
| Treatment rolled out by time, geography, eligibility, or policy threshold. | Difference-in-differences, event studies, regression discontinuity, synthetic control. | [Causal Inference: The Mixtape](https://mixtape.scunning.com/), [did](https://bcallaway11.github.io/did/), [fixest](https://lrberge.github.io/fixest/), [rdrobust](https://rdpackages.github.io/rdrobust/), [synthdid](https://synth-inference.github.io/synthdid/) |
| We only have observational data and treatment was not randomized. | DAGs, matching, weighting, target trial emulation, sensitivity analysis. | [Causal Inference: What If](https://miguelhernan.org/whatifbook), [DAGitty](https://www.dagitty.net/), [MatchIt](https://kosukeimai.github.io/MatchIt/), [WeightIt](https://ngreifer.github.io/WeightIt/), [sensemakr](https://github.com/carloscinelli/sensemakr) |
| We expect effects to vary by user, patient, context, or market. | CATE, uplift modeling, causal forests, policy learning. | [EconML](https://econml.azurewebsites.net/), [CausalML](https://causalml.readthedocs.io/), [grf](https://grf-labs.github.io/grf/), [DoubleML](https://docs.doubleml.org/stable/index.html) |
| We have time series around an intervention. | Interrupted time series, Bayesian structural time series, synthetic control, causal time-series discovery. | [CausalImpact](https://google.github.io/CausalImpact/CausalImpact.html), [Synth](https://cran.r-project.org/package=Synth), [synthdid](https://synth-inference.github.io/synthdid/), [Tigramite](https://jakobrunge.github.io/tigramite/) |
| We want to discover candidate causal structure. | Causal discovery, invariance, graphical model search, time-series causal discovery. | [Elements of Causal Inference](https://is.mpg.de/ics/en/publications/petjansch17), [Tetrad](https://www.cmu.edu/dietrich/philosophy/tetrad/), [causal-learn](https://causal-learn.readthedocs.io/en/latest/index.html), [Tigramite](https://jakobrunge.github.io/tigramite/) |

<!--lint enable table-pipe-alignment-->

Design labels are not guarantees. They are starting points for asking whether the assignment mechanism, comparison group, timing, measurements, and assumptions can support the causal claim.

## How to Judge a Causal Claim

Before trusting a causal estimate, ask:

- What is the intervention, treatment, exposure, or policy being evaluated?
- What is the estimand: ATE, ATT, CATE, LATE, local effect near a cutoff, or something else?
- What is the assignment mechanism, and was it randomized, as-if randomized, thresholded, rolled out, self-selected, or inferred?
- What comparison identifies the missing counterfactual?
- Which assumptions are necessary for identification?
- Which covariates are pre-treatment, and which could be mediators, colliders, or consequences of treatment?
- What diagnostics, placebo tests, balance checks, pre-trend checks, manipulation checks, sensitivity analyses, or refuters were run?
- What would make the claim fail?
- Are the uncertainty intervals, multiple-testing choices, and stopping rules consistent with the analysis plan?
- Does the result generalize beyond the studied units, time period, market, or exposure pattern?

## Common Failure Modes

- **Post-treatment and collider adjustment:** conditioning on variables affected by treatment, or common effects of treatment and outcome causes, can create bias or change the estimand.
- **Control variables used without a design:** adding instruments, proxies, or high-dimensional predictors may improve fit while worsening precision, overlap, or interpretability.
- **Prediction mistaken for identification:** high predictive accuracy does not identify a causal effect.
- **Sample ratio mismatch:** experiment traffic counts do not match the planned allocation, often signaling logging, targeting, or assignment problems.
- **Interference and spillovers:** one unit's treatment affects another unit's outcome, violating simple independent-treatment assumptions.
- **Noncompliance and exposure mismatch:** assigned treatment differs from received or noticed treatment.
- **Attrition and missingness:** outcome availability depends on treatment, engagement, survival, or follow-up.
- **Peeking and sequential testing:** repeated looks at noisy metrics inflate false positives unless the design accounts for them.
- **Metric validity problems:** the measured metric is not the decision-relevant outcome, or it can be gamed by the intervention.
- **Positivity violations:** some units have no realistic chance of receiving each treatment condition, making comparisons extrapolative.
- **Heterogeneous effects hidden by averages:** a positive average treatment effect may mask harmed subgroups or operationally important variation.

## Common Bad Claims

These are not banned sentences; they are prompts to ask for the design that would make them true.

- **"We controlled for everything important."** Which variables were pre-treatment, and which were colliders, mediators, or consequences of treatment?
- **"The metric went up after launch, so the launch worked."** What would the counterfactual trend have been without the launch?
- **"Matching made the groups comparable."** Comparable on measured covariates is not comparable on unmeasured causes; show balance, overlap, and sensitivity.
- **"The model predicts the outcome well, so the effect estimate is credible."** Prediction can help with nuisance functions or variance reduction, but it does not identify the effect.
- **"Randomization means we do not need diagnostics."** Randomization protects the design only if assignment, exposure, logging, and analysis followed the plan.
- **"The average effect is positive, so the intervention is safe."** Check harms, heterogeneous effects, guardrails, and whether the treated population changed.
- **"The instrument affects treatment, so IV is valid."** Relevance is only one condition; exclusion and independence usually carry the argument.
- **"CUPED/CUPAC found significance, so the product effect is real."** Variance reduction can improve precision; it does not fix bad assignment, biased logging, or post-treatment adjustment.
- **"No pre-trend difference means DiD is proven."** Pre-trends are a diagnostic, not a proof of the untreated counterfactual.
- **"This benchmark shows the method works."** Benchmarks test behavior under their own data-generating process; your study still needs identification.

## Methods Are Not Magic

- **Matching:** improves observed covariate balance; it does not fix unmeasured confounding, bad overlap, or post-treatment adjustment.
- **Weighting:** targets a specific population; extreme weights often signal weak overlap or unstable extrapolation.
- **Difference-in-differences:** needs a credible untreated counterfactual trend; staggered timing and heterogeneous effects require care.
- **Instrumental variables:** require relevance, exclusion, independence, and usually monotonicity; weak instruments can be worse than no instrument.
- **Regression discontinuity:** estimates a local effect near the cutoff; bandwidth choice and manipulation around the threshold matter.
- **Synthetic control:** depends on donor-pool quality, pre-treatment fit, and no spillovers from treated to control units.
- **Causal forests and CATE models:** estimate heterogeneity after a causal design is credible; they do not create identification by themselves.
- **Double/debiased ML:** helps with nuisance estimation under assumptions; it does not rescue a poorly defined estimand or confounded assignment.
- **CUPED and covariate adjustment:** can reduce variance in randomized experiments when covariates are pre-treatment and predictive; they change precision, not identification.

<!--lint enable awesome-list-item-->

## Core Papers

Start here when you need the canonical reference behind a method. Read these as design papers, not just estimator papers.

- [Controlled experiments on the web: survey and practical guide](https://link.springer.com/article/10.1007/s10618-008-0114-1) - Kohavi, Henne, and Sommerfield on web experiments, pitfalls, and practical design. `core paper`.
- [CUPED](https://exp-platform.com/cuped/) - Deng, Xu, Kohavi, and Walker on using pre-experiment data to reduce variance in online controlled experiments. `core paper`.
- [Leveraging covariate adjustments at scale in online A/B testing](https://proceedings.mlr.press/v218/masoero23a.html) - Masoero, Hains, and McQueen on scalable covariate adjustment for online experiments. `core paper`.
- [Always Valid Inference: Bringing Sequential Analysis to A/B Testing](https://arxiv.org/abs/1512.04922) - Johari, Pekelis, and Walsh on continuous monitoring and always-valid p-values. `core paper`.
- [Design and analysis of group sequential tests based on the type I error spending rate function](https://cir.nii.ac.jp/crid/1360574093923261312) - Kim and DeMets on alpha-spending boundaries for interim monitoring. `core paper`.
- [Difference-in-Differences with Multiple Time Periods](https://arxiv.org/abs/1803.09015) - Callaway and Sant'Anna on staggered DiD, group-time effects, covariates, and doubly robust estimation. `core paper`.
- [Difference-in-Differences with Variation in Treatment Timing](https://www.nber.org/papers/w25018) - Goodman-Bacon on what two-way fixed effects average when treatment timing varies. `core paper`.
- [Estimating Dynamic Treatment Effects in Event Studies with Heterogeneous Treatment Effects](https://arxiv.org/abs/1804.05785) - Sun and Abraham on contamination in two-way fixed-effects event-study coefficients. `core paper`.
- [Revisiting Event Study Designs: Robust and Efficient Estimation](https://arxiv.org/abs/2108.12419) - Borusyak, Jaravel, and Spiess on imputation-style event-study estimation with heterogeneous effects. `core paper`.
- [Regression Discontinuity Designs: A Guide to Practice](https://www.nber.org/papers/w13039) - Imbens and Lemieux on practical and theoretical issues in RD implementation. `core paper`.
- [Regression Discontinuity Designs in Economics](https://www.nber.org/papers/w14723) - Lee and Lemieux's applied user guide to RD validity, estimation, and interpretation. `core paper`.
- [Synthetic Control Methods for Comparative Case Studies](https://www.nber.org/papers/t0335) - Abadie, Diamond, and Hainmueller on synthetic control for aggregate policy evaluation. `core paper`.
- [Identification of Causal Effects Using Instrumental Variables](https://www.nber.org/papers/t0136) - Angrist, Imbens, and Rubin on IV identification and local average treatment effects. `core paper`.
- [Using Big Data to Emulate a Target Trial When a Randomized Trial Is Not Available](https://pmc.ncbi.nlm.nih.gov/articles/PMC4832051/) - Hernan and Robins on specifying the trial protocol before analyzing observational data. `core paper`.
- [Trimming for Bounds on Treatment Effects with Missing Outcomes](https://www.nber.org/papers/t0277) - Lee on bounding treatment effects under missing outcomes and monotonic selection. `core paper`.
- [Principal Stratification in Causal Inference](https://pubmed.ncbi.nlm.nih.gov/11890317/) - Frangakis and Rubin on causal effects within strata defined by post-treatment variables. `core paper`.
- [Single World Intervention Graphs: A Primer](https://arxiv.org/abs/1301.3908) - Richardson and Robins on graphical representations of counterfactual causal models. `core paper`.
- [A Crash Course in Good and Bad Controls](https://ftp.iza.org/dp13659.pdf) - Cinelli, Forney, and Pearl on when controls help, hurt, or change the estimand. `core paper` `diagnostics`.
- [Generalized Random Forests](https://projecteuclid.org/journals/annals-of-statistics/volume-47/issue-2/Generalized-random-forests/10.1214/18-AOS1709.full) - Athey, Tibshirani, and Wager on forests for heterogeneous effects and related estimands. `core paper`.
- [Meta-learners for Estimating Heterogeneous Treatment Effects](https://arxiv.org/abs/1706.03461) - Kunzel et al. on S-, T-, X-, and related treatment-effect learners. `core paper`.
- [Recommendations as Treatments](https://www.microsoft.com/en-us/research/?p=398366) - Schnabel et al. on debiasing learning and evaluation for recommender systems. `core paper`.
- [Network experiment designs for inferring causal effects under interference](https://www.frontiersin.org/journals/big-data/articles/10.3389/fdata.2023.1128649/full) - Designs for estimating effects when treatment spills across network edges. `core paper`.
- [Interference, Bias, and Variance in Two-Sided Marketplace Experimentation](https://www.gsb.stanford.edu/faculty-research/working-papers/interference-bias-variance-two-sided-marketplace-experimentation) - Marketplace experiment design under interference. `core paper` `case study`.

## Foundations and Books

- [Causal Inference: What If](https://miguelhernan.org/whatifbook) - Free book by Miguel Hernan and James Robins; especially strong on target trials, longitudinal data, exchangeability, positivity, and consistency. `first read`.
- [Causal Inference: The Mixtape](https://mixtape.scunning.com/) - Scott Cunningham's applied econometrics book covering regression, matching, IV, DiD, RDD, and synthetic control. `first read`.
- [The Effect](https://theeffectbook.net/) - Nick Huntington-Klein's accessible research-design-first book with code examples and a strong emphasis on identification. `first read`.
- [Causal Inference for the Brave and True](https://matheusfacure.github.io/python-causality-handbook/landing-page) - Python-first online book with practical examples across experiments, matching, DiD, RDD, synthetic controls, and causal ML. `first read`.
- [Introduction to Causal Inference from a Machine Learning Perspective](https://www.bradyneal.com/causal-inference-course) - Brady Neal's course text and lectures bridging graphical models, potential outcomes, and ML. `first read`.
- [Elements of Causal Inference](https://is.mpg.de/ics/en/publications/petjansch17) - Peters, Janzing, and Scholkopf on causal discovery, invariance, and structural causal models. `advanced`.
- [Design of Observational Studies](https://link.springer.com/book/10.1007/978-1-4419-1213-8) - Rosenbaum's design-centered treatment of observational studies and sensitivity analysis. `advanced`.
- [Field Experiments](https://wwnorton.com/books/Field-Experiments/) - Gerber and Green on designing and analyzing randomized field experiments. `core reference`.
- [Mostly Harmless Econometrics](https://press.princeton.edu/books/paperback/9780691120355/mostly-harmless-econometrics) - A classic design-based econometrics reference.
- [Mastering 'Metrics](https://press.princeton.edu/books/paperback/9780691152844/mastering-metrics) - A gentler companion focused on core empirical strategies.

## Courses and Lecture Notes

- [Causal Diagrams: Draw Your Assumptions Before Your Conclusions](https://harvardonline.harvard.edu/course/causal-diagrams-draw-your-assumptions-your-conclusions) - Harvard Online course by Miguel Hernan on DAGs, SWIGs, bias, and adjustment. `first read` `diagnostics`.
- [A Crash Course in Causality](https://www.coursera.org/learn/crash-course-in-causality) - University of Pennsylvania course on potential outcomes, DAGs, matching, IPTW, and IV.
- [Causal Inference](https://www.coursera.org/learn/causal-inference) - Columbia/Coursera course covering potential outcomes, ignorability, matching, weighting, and ML extensions.
- [Machine Learning & Causal Inference: A Short Course](https://www.gsb.stanford.edu/faculty-research/labs-initiatives/sil/research/methods/ai-machine-learning/short-course) - Stanford short course on ML for treatment effects, heterogeneity, and treatment assignment policies.
- [Causality, Decision Making, and Data Science](https://stanford-causal-inference-class.github.io/materials.html) - Stanford course materials including randomized experiments, online experiments, IV, DiD, RDD, and policy learning. `first read`.
- [DoWhy + EconML Tutorial](https://www.pywhy.org/dowhy/v0.14/example_notebooks/tutorial-causalinference-machinelearning-using-dowhy-econml.html) - Hands-on notebook connecting causal assumptions, identification, estimation, and refutation. `software`.
- [Mixtape Sessions](https://github.com/Mixtape-Sessions) - Workshop material around modern causal inference and econometric methods.

## Causal Diagrams and Identification

- [DAGitty](https://www.dagitty.net/) - Browser-based tool and R package for drawing and analyzing causal DAGs and adjustment sets. `first read` `software`.
- [DoWhy](https://www.pywhy.org/dowhy/) - Python library organized around model, identify, estimate, and refute. `software`.
- [pgmpy](https://pgmpy.org/) - Causal queries, adjustment sets, and do-operator support for graphical models in Python.
- [Tetrad](https://www.cmu.edu/dietrich/philosophy/tetrad/) - CMU project for graphical causal modeling and causal discovery.
- [Single World Intervention Graphs: A Primer](https://arxiv.org/abs/1301.3908) - Richardson and Robins on SWIGs for counterfactual causal models. `core paper`.
- [A Crash Course in Good and Bad Controls](https://ftp.iza.org/dp13659.pdf) - Cinelli, Forney, and Pearl on when controls help, hurt, or change the estimand. `first read` `diagnostics`.

## Randomized Experiments and A/B Testing

- [Trustworthy Online Controlled Experiments](https://experimentguide.com/) - Kohavi, Tang, and Xu's practical guide to A/B testing, metrics, trustworthiness checks, and experimentation platforms. `first read`.
- [ExP Platform](https://exp-platform.com/) - Papers and resources from Ronny Kohavi and collaborators on online controlled experiments at scale. `core reference`.
- [Controlled experiments on the web: survey and practical guide](https://link.springer.com/article/10.1007/s10618-008-0114-1) - Open-access survey on web experiments, common pitfalls, and practical design. `core paper`.
- [Online Experimentation at Microsoft](https://www.microsoft.com/en-us/research/?p=696748) - Lessons from Microsoft's experimentation platform and culture. `case study`.
- [GrowthBook](https://docs.growthbook.io/) - Open-source feature flagging and experimentation platform. `software`.
- [PlanOut](https://github.com/facebookarchive/planout) - Archived framework for parameterized experiments and deterministic random assignment logic.
- [Ax](https://ax.dev/) - Adaptive experimentation and Bayesian optimization platform.
- [DeclareDesign](https://declaredesign.org/r/declaredesign/) - R framework for declaring, simulating, and diagnosing research designs before implementation. `software` `diagnostics`.
- [randomizr](https://declaredesign.org/r/randomizr/) - R package for random assignment procedures.
- [estimatr](https://declaredesign.org/r/estimatr/) - R package for design-based estimators with robust and clustered standard errors.

## Experiment Health, Guardrails, and SRM

Do not analyze experiment effects until the experiment itself looks healthy. SRM, broken triggering, exposure leakage, denominator shifts, metric bugs, and skipped guardrails can flip the sign of a result.

- [Diagnosing Sample Ratio Mismatch in Online Controlled Experiments](https://www.microsoft.com/en-us/research/publication/diagnosing-sample-ratio-mismatch-in-online-controlled-experiments-a-taxonomy-and-rules-of-thumb-for-practitioners/) - Fabijan et al. taxonomy and rules of thumb for finding SRM root causes. `diagnostics`.
- [Diagnosing Sample Ratio Mismatch in A/B Testing](https://www.microsoft.com/en-us/research/articles/diagnosing-sample-ratio-mismatch-in-a-b-testing/) - Microsoft ExP walkthrough of why SRM can invalidate product conclusions. `first read` `diagnostics`.
- [Three Key Checklists and Remedies for Trustworthy Analysis of Online Controlled Experiments at Scale](https://www.microsoft.com/en-us/research/publication/three-key-checklists-and-remedies-for-trustworthy-analysis-of-online-controlled-experiments-at-scale/) - Checklists for setup, analysis, and decision review in large-scale experimentation. `diagnostics`.
- [A Dirty Dozen: Twelve Common Metric Interpretation Pitfalls in Online Controlled Experiments](https://www.microsoft.com/en-us/research/publication/a-dirty-dozen-twelve-common-metric-interpretation-pitfalls-in-online-controlled-experiments/) - Examples of metric denominator shifts, ratio traps, and misleading movements. `diagnostics`.
- [p-Values for Your p-Values](https://www.microsoft.com/en-us/research/articles/p-values-for-your-p-values-validating-metric-trustworthiness-by-simulated-a-a-tests/) - Simulated A/A tests for validating metric and testing-system behavior. `diagnostics`.
- [The Anatomy of a Large-Scale Experimentation Platform](https://www.microsoft.com/en-us/research/publication/the-anatomy-of-a-large-scale-experimentation-platform/) - Platform architecture for assignment, logging, analysis, and trustworthiness at scale. `case study`.
- [Safe Velocity](https://www.microsoft.com/en-us/research/publication/safe-velocity-a-practical-guide-to-software-deployment-at-scale-using-controlled-rollout/) - Controlled rollout as a bridge between deployment safety and experiment learning. `case study`.
- [Top Challenges from the first Practical Online Controlled Experiments Summit](https://www.microsoft.com/en-us/research/publication/top-challenges-from-the-first-practical-online-controlled-experiments-summit/) - Cross-company summary of operating challenges in experimentation programs. `case study`.

## Variance Reduction and Sequential Testing

- [CUPED](https://exp-platform.com/cuped/) - Deng, Xu, Kohavi, and Walker paper on using pre-experiment data to reduce variance in online controlled experiments. `core paper`.
- [Deep Dive Into Variance Reduction](https://www.microsoft.com/en-us/research/articles/deep-dive-into-variance-reduction/) - Microsoft ExP article on what variance reduction does and does not change in A/B testing. `first read`.
- [Leveraging covariate adjustments at scale in online A/B testing](https://proceedings.mlr.press/v218/masoero23a.html) - Masoero, Hains, and McQueen on scalable covariate adjustment for online experiments. `core paper`.
- [Improving Experimental Power through CUPAC](https://careersatdoordash.com/blog/improving-experimental-power-through-control-using-predictions-as-covariate-cupac/) - DoorDash article on using ML predictions as covariates in switchback and online experiments. `case study`.
- [Meet Dash-AB](https://careersatdoordash.com/blog/meet-dash-ab-the-statistics-engine-of-experimentation-at-doordash/) - DoorDash's experimentation statistics engine, including CUPED, CUPAC, fixed-horizon tests, and sequential tests. `case study`.
- [Always Valid Inference: Bringing Sequential Analysis to A/B Testing](https://arxiv.org/abs/1512.04922) - Johari, Pekelis, and Walsh on continuous monitoring and always-valid p-values for A/B tests. `core paper`.
- [Design and analysis of group sequential tests based on the type I error spending rate function](https://cir.nii.ac.jp/crid/1360574093923261312) - Kim and DeMets on alpha-spending boundaries for interim looks. `core paper`.
- [Online multiple hypothesis testing](https://pmc.ncbi.nlm.nih.gov/articles/PMC7615519/) - Survey of online false discovery rate control and sequential testing ideas.
- [Covariate adjustment and CUPED methodology](https://launchdarkly.com/docs/guides/statistical-methodology/cuped) - Practical documentation on CUPED, ANCOVA-style adjustment, pre-treatment covariates, and implementation caveats. `first read`.

## Cluster, Network, and Marketplace Experiments

- [Toward Causal Inference in Cluster Randomized Trials](https://prevention.nih.gov/education-training/methods-mind-gap/toward-causal-inference-cluster-randomized-trials-estimands-and-reflection-current-practice) - NIH webinar on estimands and practice in cluster randomized trials. `first read`.
- [Network experiment designs for inferring causal effects under interference](https://www.frontiersin.org/journals/big-data/articles/10.3389/fdata.2023.1128649/full) - Designs for direct and total effects when treatment spills over across network edges. `core paper`.
- [Interference, Bias, and Variance in Two-Sided Marketplace Experimentation](https://www.gsb.stanford.edu/faculty-research/working-papers/interference-bias-variance-two-sided-marketplace-experimentation) - Practitioner-oriented paper on marketplace experiment bias and variance tradeoffs. `core paper` `case study`.
- [Causal Inference in the Presence of Interference in Sponsored Search Advertising](https://www.frontiersin.org/journals/big-data/articles/10.3389/fdata.2022.888592/full) - Advertising example where the outcome for one unit depends on other units' placements.

## Quasi-Experiments and Observational Designs

- [Difference-in-Differences with Multiple Time Periods](https://arxiv.org/abs/1803.09015) - Callaway and Sant'Anna paper behind modern staggered DiD estimands and doubly robust estimation. `core paper`.
- [Difference-in-Differences with Variation in Treatment Timing](https://www.nber.org/papers/w25018) - Goodman-Bacon decomposition of two-way fixed effects with staggered adoption. `core paper`.
- [Estimating Dynamic Treatment Effects in Event Studies with Heterogeneous Treatment Effects](https://arxiv.org/abs/1804.05785) - Sun and Abraham on why conventional event-study leads and lags can be contaminated under heterogeneous effects. `core paper`.
- [Revisiting Event Study Designs: Robust and Efficient Estimation](https://arxiv.org/abs/2108.12419) - Borusyak, Jaravel, and Spiess on imputation estimators and tests for event-study identifying assumptions. `core paper`.
- [Regression Discontinuity Designs: A Guide to Practice](https://www.nber.org/papers/w13039) - Imbens and Lemieux on RD implementation, bandwidths, and interpretation. `core paper`.
- [Regression Discontinuity Designs in Economics](https://www.nber.org/papers/w14723) - Lee and Lemieux's broader user guide to RD validity and design logic. `core paper`.
- [did](https://bcallaway11.github.io/did/) - R package for modern difference-in-differences with multiple periods and staggered treatment timing. `software`.
- [fixest](https://lrberge.github.io/fixest/) - Fast fixed-effects estimation in R, including event-study and DiD workflows. `software`.
- [rdrobust](https://rdpackages.github.io/rdrobust/) - Robust inference, bandwidth selection, and plots for regression discontinuity designs. `software`.
- [Synth](https://cran.r-project.org/package=Synth) - R implementation of synthetic control methods for comparative case studies. `software`.
- [synthdid](https://synth-inference.github.io/synthdid/) - R package for synthetic difference-in-differences. `software`.
- [CausalImpact](https://google.github.io/CausalImpact/CausalImpact.html) - Bayesian structural time-series approach for estimating impacts of interventions on time series. `software`.
- [MatchIt](https://kosukeimai.github.io/MatchIt/) - R package for matching and preprocessing before causal estimation. `software`.
- [WeightIt](https://ngreifer.github.io/WeightIt/) - R package for balancing weights across binary, multi-category, continuous, and longitudinal treatments. `software`.
- [cobalt](https://ngreifer.github.io/cobalt/) - Covariate balance diagnostics and Love plots for matching and weighting workflows. `software` `diagnostics`.

## Target Trials and Observational Design

When treatment is self-selected, first write the protocol for the randomized trial you wish you could run. Eligibility, time zero, treatment strategies, follow-up, outcomes, and causal contrasts should be explicit before choosing matching, weighting, regression, or ML.

- [Using Big Data to Emulate a Target Trial When a Randomized Trial Is Not Available](https://pmc.ncbi.nlm.nih.gov/articles/PMC4832051/) - Hernan and Robins on making the target trial explicit in observational databases. `core paper`.
- [Target Trial Emulation](https://pubmed.ncbi.nlm.nih.gov/36508210/) - Hernan, Wang, and Leaf guide to target-trial emulation as a framework for observational causal inference. `first read`.
- [Target Trial Emulation to Improve Causal Inference from Observational Data](https://pmc.ncbi.nlm.nih.gov/articles/PMC10400102/) - Practical guide to specifying and emulating target trials in healthcare data. `first read`.
- [Causal inference from observational data and target trial emulation](https://pubmed.ncbi.nlm.nih.gov/36063988/) - Short applied discussion of target-trial thinking for observational studies. `first read`.
- [Causal Inference: What If](https://miguelhernan.org/whatifbook) - Book-length treatment of target trials, longitudinal strategies, exchangeability, positivity, and consistency. `core reference`.
- [DAGitty](https://www.dagitty.net/) - Draw assumptions before choosing adjustment sets for observational analyses. `software` `diagnostics`.

## Instrumental Variables and Encouragement Designs

- [Identification of Causal Effects Using Instrumental Variables](https://www.nber.org/papers/t0136) - Angrist, Imbens, and Rubin paper on IV identification and local average treatment effects. `core paper`.
- [Tutorial in Biostatistics: Instrumental Variable Methods for Causal Inference](https://pmc.ncbi.nlm.nih.gov/articles/PMC4201653/) - Applied tutorial covering IV assumptions, estimation, sensitivity analysis, and randomized encouragement trials. `first read`.
- [Causal Inference With Instrumental Variables](https://prevention.nih.gov/education-training/methods-mind-gap/causal-inference-instrumental-variables) - NIH webinar on LATE/CACE-style instrumental-variable reasoning.
- [Quasi-Experimental Designs for Causal Inference](https://pmc.ncbi.nlm.nih.gov/articles/PMC6086368/) - Overview of quasi-experimental designs, including IV and encouragement designs.

## Missing Data, Attrition, and Censoring

Missing outcomes are not just smaller samples. Ask whether missingness is pre-treatment, post-treatment, outcome-dependent, or caused by survival/engagement before treating complete cases as the analysis population.

- [Addressing missing data in randomized clinical trials](https://journals.plos.org/plosone/doi?id=10.1371/journal.pone.0234349) - Causal-inference perspective on MCAR, MAR, MNAR, selective attrition, and Lee-bound-style approaches. `first read`.
- [Analysis of Semiparametric Regression Models for Repeated Outcomes in the Presence of Missing Data](https://cir.nii.ac.jp/crid/1361137044262135936) - Robins, Rotnitzky, and Zhao paper introducing inverse-probability-of-censoring weighted estimators. `core paper`.
- [Trimming for Bounds on Treatment Effects with Missing Outcomes](https://www.nber.org/papers/t0277) - Lee bounds for treatment effects when outcomes are missing under monotonic selection. `core paper`.
- [Principal Stratification in Causal Inference](https://pubmed.ncbi.nlm.nih.gov/11890317/) - Frangakis and Rubin on causal effects defined by joint potential values of post-treatment variables. `core paper`.
- [Adjusting for Nonignorable Drop-Out Using Semiparametric Nonresponse Models](https://cir.nii.ac.jp/crid/1360576122324029056) - Scharfstein, Rotnitzky, and Robins on sensitivity analysis for nonignorable dropout. `advanced`.
- [Causal Inference With Outcome-Dependent Missingness And Self-Censoring](https://pmc.ncbi.nlm.nih.gov/articles/PMC11905187/) - Work on causal identification when missingness depends on outcomes or self-censoring.
- [Causal Inference with Corrupted Data](https://www.nber.org/books-and-chapters/data-privacy-protection-and-conduct-applied-research-methods-approaches-and-their-consequences/causal-inference-corrupted-data-measurement-error-missing-values-discretization-and-differential) - NBER chapter on measurement error, missing values, discretization, and privacy transformations.

## Heterogeneous Effects, Uplift, and Policy Learning

- [EconML](https://econml.azurewebsites.net/) - Python library from Microsoft Research for CATE estimation, orthogonal ML, causal forests, IV methods, and policy interpretation. `software`.
- [CausalML](https://causalml.readthedocs.io/) - Python package for uplift modeling, CATE estimation, meta-learners, causal trees, and model validation. `software`.
- [grf](https://grf-labs.github.io/grf/) - R package for generalized random forests, including causal forests and instrumental forests. `software`.
- [DoubleML](https://docs.doubleml.org/stable/index.html) - Python and R implementation of double/debiased machine learning. `software`.
- [Meta-learners for Estimating Heterogeneous Treatment Effects](https://arxiv.org/abs/1706.03461) - Kunzel et al. paper on S-, T-, X-, and related learners. `core paper`.
- [Generalized Random Forests](https://projecteuclid.org/journals/annals-of-statistics/volume-47/issue-2/Generalized-random-forests/10.1214/18-AOS1709.full) - Athey, Tibshirani, and Wager paper underlying GRF methods. `core paper`.
- [Policy Learning with Observational Data](https://arxiv.org/abs/1702.02896) - Athey and Wager on learning treatment assignment policies. `core paper`.

## Recommender Systems, Ads, and ML Product Loops

Offline evaluation is not proof of live causal impact. Logged policies, exposure propensities, delayed feedback, slate position, retraining loops, and long-horizon user behavior are part of the causal design.

- [Tutorial on Causal Inference and Counterfactual Reasoning](https://www.microsoft.com/en-us/research/publication/tutorial-on-causal-inference-and-counterfactual-reasoning/) - KDD tutorial with recommender systems, social media, health, education, and governance examples.
- [Recommendations as Treatments](https://www.microsoft.com/en-us/research/?p=398366) - Schnabel et al. on debiasing learning and evaluation for recommender systems using causal inference ideas. `core paper`.
- [Estimating the Causal Impact of Recommendation Systems from Observational Data](https://www.microsoft.com/en-us/research/publication/estimating-the-causal-impact-of-recommendation-systems-from-observational-data/) - Sharma, Hofman, and Watts on IV-style identification for recommendation-system effects. `core paper`.
- [Unbiased Offline Evaluation of Contextual-bandit-based News Article Recommendation Algorithms](https://arxiv.org/abs/1003.5956) - Li, Chu, Langford, and Wang on replay evaluation with random logged traffic. `core paper`.
- [Counterfactual Evaluation and Learning for Search, Recommendation and Ad Placement](https://www.cs.cornell.edu/~adith/CfactSIGIR2016/) - Joachims and Swaminathan tutorial on logged feedback, propensities, and counterfactual learning. `first read`.
- [Off-policy evaluation for slate recommendation](https://papers.nips.cc/paper/6954-off-policy-evaluation-for-slate-recommendation) - Logged-policy evaluation for ranked recommendations and ads. `core paper`.
- [A survey on causal inference for recommendation](https://pmc.ncbi.nlm.nih.gov/articles/PMC10901840/) - Survey of causal recommendation methods and taxonomies. `first read`.
- [Breaking Feedback Loops in Recommender Systems with Causal Inference](https://arxiv.org/abs/2207.01616) - Krauth, Wang, and Jordan on recommender feedback loops and causal adjustment. `core paper`.
- [RecSim NG](https://google-research.github.io/recsim_ng/) - Probabilistic simulator for multi-agent recommender ecosystems and counterfactual policy experimentation. `software`.

## Sensitivity, Robustness, and Diagnostics

- [sensemakr](https://github.com/carloscinelli/sensemakr) - R package for omitted-variable-bias sensitivity analysis in linear regression. `software` `diagnostics`.
- [EValue](https://cran.r-project.org/package=EValue) - R package for E-values and sensitivity analysis for unmeasured confounding. `software` `diagnostics`.
- [DoWhy refuters](https://www.pywhy.org/dowhy/v0.14/user_guide/refuting_causal_estimates/index.html) - Refutation tests such as placebo treatments, random common causes, and data subsets. `diagnostics`.
- [EconML sensitivity tools](https://www.pywhy.org/EconML/spec/estimation/dml.html#sensitivity-analysis) - Sensitivity summaries and robustness values for selected orthogonal ML estimators.
- [Making Sense of Sensitivity](https://escholarship.org/uc/item/0pg6471b) - Cinelli and Hazlett on omitted variable bias sensitivity analysis. `core paper`.
- [A/A tests and sample ratio mismatch](https://exp-platform.com/) - Practical experimentation diagnostics collected by the ExP platform. `diagnostics`.

## Causal Discovery and Time Series

- [causal-learn](https://causal-learn.readthedocs.io/en/latest/index.html) - Python package for causal discovery, including PC, FCI, GES, LiNGAM-style methods, and independence tests. `software`.
- [Tigramite](https://jakobrunge.github.io/tigramite/) - Python package for causal discovery and causal effect estimation in time-series data. `software`.
- [DoDiscover](https://github.com/py-why/dodiscover) - Experimental PyWhy library focused on causal discovery workflows.
- [Causal Discovery Toolbox](https://fentechsolutions.github.io/CausalDiscoveryToolbox/html/index.html) - Python toolbox for graph and pairwise causal discovery methods.
- [Causal inference for time series](https://www.nature.com/articles/s43017-023-00431-y) - Review of causal questions, assumptions, and methods for time-series settings. `first read`.
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
- [CausalRivers](https://causalrivers.github.io/) - Real-world river-discharge benchmark for time-series causal discovery.
- [LaLonde / National Supported Work data](https://users.nber.org/~rdehejia/nswdata.html) - Classic benchmark data for program evaluation and matching.
- [IHDP benchmark](https://www.fredjo.com/) - Common semi-synthetic benchmark for treatment effect estimation.

Benchmarks are useful for debugging and comparison, not proof that a method identifies your real-world causal effect. Treat every benchmark result as conditional on the data-generating process used to create it.

## Industry Case Studies

- [Ocelot: Scaling observational causal inference at LinkedIn](https://www.linkedin.com/blog/engineering/data-science/ocelot-scaling-observational-causal-inference-at-linkedin) - Platform and review process for observational causal studies at LinkedIn.
- [LinkedIn T-REX experimentation infrastructure](https://engineering.linkedin.com/content/engineering/en-us/blog/2020/our-evolution-towards-t-rex--the-prehistory-of-experimentation-i) - Experiment assignment, ramping, and reporting at scale.
- [Experimentation Platform at Netflix: Building Useful Inference](https://research.netflix.com/publication/experimentation-platform-at-netflix-building-useful-inference) - Netflix Research paper on an experimentation platform built for scientific workflows.
- [ExP Platform papers](https://exp-platform.com/) - Microsoft and industry lessons on sample ratio mismatch, metrics, guardrails, and trustworthy online experiments.
- [Experiment like Spotify](https://confidence.spotify.com/blog/experiment-like-spotify) - Spotify's public writing on experimentation tooling and practice.

## Healthcare and Policy Case Studies

- [Target Trial Emulation](https://pubmed.ncbi.nlm.nih.gov/36508210/) - Hernan, Wang, and Leaf framework for designing observational studies around the randomized trial one would have liked to run.
- [Target Trial Emulation to Improve Causal Inference from Observational Data](https://pmc.ncbi.nlm.nih.gov/articles/PMC10400102/) - Practical healthcare-oriented guide to target-trial specification and emulation.
- [Synthetic Control Methods for Comparative Case Studies](https://www.nber.org/papers/t0335) - California tobacco-control program case study introducing synthetic control for aggregate policy evaluation.
- [A Causal Roadmap for Generating High-Quality Real-World Evidence](https://www.microsoft.com/en-us/research/?p=941538) - Roadmap for real-world evidence with design, assumptions, and diagnostics.

## Communities and Related Lists

- [PyWhy](https://www.pywhy.org/) - Community and ecosystem for causal machine learning.
- [CAUSALab](https://hsph.harvard.edu/research/causalab/) - Harvard group with books, courses, software, and applied causal inference research.
- [Stanford Causal Science Center](https://datascience.stanford.edu/causal) - Seminars, workshops, and interdisciplinary causal inference resources.
- [Online Causal Inference Seminar](https://datascience.stanford.edu/causal/online-causal-inference-seminars) - Seminar series and recordings from researchers across causal inference.
- [awesome-causal-inference](https://github.com/matteocourthoud/awesome-causal-inference) - Broad existing awesome list of causal inference resources.

<!--lint disable awesome-list-item-->

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

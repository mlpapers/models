# Machine learning and statistical models

## Linear and generalized linear models

- **[Least squares and ridge](https://scikit-learn.org/stable/modules/linear_model.html)** — Least squares minimizes squared prediction errors; ridge adds a squared-coefficient penalty to stabilize fits with correlated predictors. Includes implementation and solver guidance.
- **[Lasso](https://doi.org/10.1111/j.2517-6161.1996.tb02080.x)** — 1996. Constrains the sum of absolute regression coefficients, shrinking some exactly to zero. Combines estimation and variable selection.
- **[Elastic net](https://scikit-learn.org/stable/modules/linear_model.html#elastic-net)** — Combines L1 and L2 penalties, allowing sparse coefficients while retaining ridge-style shrinkage. A useful alternative to lasso for correlated predictors.
- **[Generalized linear models](https://www.maths.usyd.edu.au/u/jchan/GLM/Nelder1972GLM.pdf)** — 1972. Connects an exponential-family response mean to a linear predictor through a link function. Unifies models fitted by iteratively weighted linear regression.
- **[Logistic regression](https://scikit-learn.org/stable/modules/linear_model.html#logistic-regression)** — Models binary class probability through a logistic link applied to a linear score. The documented implementation also supports multiclass classification and regularization.
- **[Generalized linear mixed models](https://doi.org/10.1080/01621459.1993.10594284)** — 1993. Adds random effects to GLMs for correlated observations and overdispersion. Breslow–Clayton develops approximate inference using penalized quasi-likelihood.
- **[Tests as linear models](https://lindeloev.github.io/tests-as-linear/)** — 2019. Worked connections between regression, t-tests, correlation and ANOVA. Rank-based analogues are also discussed; some equivalences are approximate.

## Additive models and adaptive splines

- **[Generalized additive models](https://doi.org/10.1214/ss/1177013604)** — 1986. Replaces a GLM's linear predictor terms with smooth functions of individual inputs. Local scoring extends additive regression to different response distributions.
- **[MARS](https://doi.org/10.1214/aos/1176347963)** — 1991. Builds regression models from products of spline basis functions, selecting their number, variables and knot locations from data. Separates additive contributions from interactions.
- **[Generalized additive neural networks](https://doi.org/10.1145/312129.312228)** — 1999. Potts's KDD reference on neural additive models.
- **[Intelligible classification and regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf)** — 2012. Studies additive models whose individual feature contributions can be plotted, comparing fitting methods and the accuracy cost of restricting interactions.
- **[GA2M](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd13.pdf)** — 2013. Extends additive models with selected pairwise interactions. FAST ranks candidate feature pairs, keeping explanations as one- and two-dimensional functions.
- **[Intelligible healthcare models](https://www.microsoft.com/en-us/research/publication/intelligible-models-healthcare-predicting-pneumonia-risk-hospital-30-day-readmission/)** — 2015. Pneumonia and readmission case studies use additive models with pairwise interactions to expose unexpected learned associations and revise models.
- **[GAMs with autoregressive terms](https://link.springer.com/article/10.1186/1471-2288-12-165)** — 2012. Combines nonlinear covariate terms with autoregression for serially correlated outcomes. Demonstrated on temperature and daily mortality.
- **[Neural Additive Models](https://arxiv.org/abs/2004.13912)** — 2020. Jointly trains a separate neural network for each input feature, then combines their outputs linearly. Learns flexible univariate shapes while preserving additive structure.
- **[How trustworthy are GAMs?](https://arxiv.org/abs/2006.06466)** — 2020. Shows that similarly accurate GAMs can learn conflicting feature shapes. Compares inductive biases, sparsity and behavior on rare subpopulations; accuracy alone does not validate an explanation.

## Trees and tabular prediction

- **[CART](https://scikit-learn.org/stable/modules/tree.html)** — Recursively partitions feature space into regions with simple predictions. Depth and pruning control complexity; individual trees can be unstable under changes to training data.
- **[Random forests](https://link.springer.com/article/10.1023/A:1010933404324)** — 2001. Combines randomized trees, including random feature selection at splits. Analyzes how individual tree strength and dependence affect ensemble error.
- **[Bayesian additive regression trees](https://arxiv.org/abs/0806.3286)** — 2008. Represents a response as a sum of trees with a regularization prior that keeps individual trees weak. Bayesian backfitting samples the model and its predictive uncertainty.
- **[XGBoost](https://arxiv.org/abs/1603.02754)** — 2016. Gradient-boosted trees with sparsity-aware split finding and a weighted quantile sketch for approximate tree learning. The paper also addresses cache access and distributed computation.
- **[CatBoost](https://arxiv.org/abs/1706.09516)** — 2017. Uses ordered boosting and categorical-feature processing to address prediction shift caused by target leakage during training.
- **[TabPFN: original classifier](https://arxiv.org/abs/2207.01848)** — 2022. Pretrains a transformer on synthetic classification tasks. At inference, labeled training rows provide context for predictions without updating the model weights; the original scope is small tabular datasets.
- **[TabPFN: classification and regression](https://www.nature.com/articles/s41586-024-08328-6)** — 2025. Extends prior-data-fitted tabular prediction to regression, categorical inputs and missing values. A pretrained transformer performs in-context prediction from labeled examples.
- **[TabM](https://arxiv.org/abs/2410.24210)** — 2024. Builds parameter-sharing ensembles of multilayer perceptrons for tabular prediction. Joint training produces multiple predictions without storing a separate full network for every ensemble member.
- **[TabICL](https://arxiv.org/abs/2502.05564)** — 2025. Combines representations of table rows with a transformer for in-context classification. Synthetic-task pretraining supports prediction on new tables without task-specific weight updates.

### Observation protocols

- **[Repeated measurements](https://arxiv.org/abs/2610.16801v1)** - 2026 preprint. More readings with independent noise at fixed inputs can harm new-input predictions. Priors coupling input density and responses can count repeated locations as fresh input evidence; TabPFN-v3 also depends on row count.
- **[Repetition evidence](https://arxiv.org/abs/2610.16801v1)** - TabPFN-v3 (8-member ensemble), six 1D functions, 20 seeds, 12 sites, 64 readings/site, noise SD 0.05: median new-input MSE 0.015 (one reading), 0.049 (separate rows), 0.0094 (means). Count reset weakens gains at SD 0.30/0.50.

### Compression of tabular models

- **[Shallow TFMs](https://arxiv.org/abs/2610.13253v1)** - 2026 preprint. Uses affine block replacement, following [ReplaceMe](https://mlpapers.org/neural-nets/#pruning-quantization-and-efficient-execution), with per-feature maps for dual-axis models. Across 171 classification datasets and eight models, halving depth loses at most 0.002 median AUROC per model.
- **[Compression limits](https://arxiv.org/abs/2610.13253v1)** - On 41 regression datasets, retaining one block costs TabPFN-3 0.132 median R2. Regression windows use labelled calibration R2; classification uses output KL. Maps are fitted to the target table's activations.
- **[Compression cost](https://arxiv.org/abs/2610.13253v1)** - MIMIC-III: one-block TabPFN-3 on RTX 5090 gives 1.2x speedup for 512-query re-encoding, 2.4x for a cached single query. On i9-14900K (fp32, batch 512), re-encoding gains are 1.4x for TabPFN-3 and 12.4x for TabPFNv2.

## Local and conditional-independence classifiers

- **[Nearest-neighbor classification](https://isl.stanford.edu/~cover/papers/transIT/0021cove.pdf)** — 1967. Predicts from nearby labeled examples. Cover and Hart bound asymptotic one-neighbor error by twice Bayes error under their assumptions; this is neither a finite-sample guarantee nor a guarantee for an arbitrary learned distance.
- **[Naive Bayes](https://link.springer.com/article/10.1023/A:1007413511361)** — 1997 analysis. Multiplies class-conditional feature probabilities under an independence model. Domingos and Pazzani show that correct class decisions can survive some dependence violations even when estimated probabilities are inaccurate.

## Support-vector methods

- **[Support-vector networks](https://link.springer.com/article/10.1007/BF00994018)** — 1995. Constructs a linear decision surface in a nonlinear feature space and extends the approach to nonseparable training data. A foundation for kernel-based classification.
- **[SVM implementations](https://scikit-learn.org/stable/modules/svm.html)** — Linear and kernel classification, regression and outlier detection. Decision scores are not probabilities; probability estimation adds a separate fitting step.

## Probabilistic prediction, survival and treatment effects

- **[Quantile regression forests](https://jmlr.csail.mit.edu/papers/volume7/meinshausen06a/meinshausen06a.pdf)** — 2006. Extends random forests to estimate the conditional response distribution and its quantiles, rather than only a conditional mean.
- **[Extreme NO2 forecasting](https://arxiv.org/abs/2003.11356)** — 2020. Compares probabilistic models for high-pollution episodes, including threshold-exceedance probabilities. A case study in evaluating forecast distributions rather than only mean predictions.
- **[Kaplan–Meier](https://doi.org/10.1080/01621459.1958.10501452)** — 1958. Estimates a survival curve from incomplete lifetime observations using a product-limit estimator. Independent censoring is a substantive assumption, explicitly discussed in the paper.
- **[Cox regression](https://doi.org/10.1111/j.2517-6161.1972.tb00899.x)** — 1972. Models covariate effects as multipliers of an unspecified baseline hazard. Handles censored event times without choosing a parametric baseline distribution.
- **[DeepSurv](https://arxiv.org/abs/1606.00931)** — 2016. Uses a neural network for the risk function in a Cox proportional-hazards model, allowing nonlinear covariate interactions in survival prediction.
- **[Treatment-effect meta-learners](https://arxiv.org/abs/1706.03461)** — 2017. Builds estimators of conditional average treatment effects from existing regression learners. Introduces the X-learner and studies settings with unequal treatment-group sizes.
- **[Simpson's paradox](https://arxiv.org/abs/1912.01422)** — 2019. Constructs examples where conditioning on additional variables reverses an association. Illustrates the dependence of aggregated comparisons on the variables included in an analysis.
- **[NGBoost](https://arxiv.org/abs/1910.03225)** — 2019. Boosts parameters of a conditional probability distribution using natural gradients, extending boosting from point estimates to probabilistic regression.

## Classical forecasting and latent states

- **[Forecasting: Principles and Practice, second edition](https://otexts.com/fpp2/index.html)** — 2018. Historical R reference covering forecasting methods, diagnostics and evaluation, with examples based on the forecast package.
- **[Forecasting: Principles and Practice, third edition](https://otexts.com/fpp3/index.html)** — 2021. Updated forecasting reference using tsibble and fable. Covers data exploration, statistical models, uncertainty and forecast evaluation.
- **[ARIMA and seasonal ARIMA](https://otexts.com/fpp3/arima.html)** — 2021. Combines differencing, autoregressive terms and moving-average errors. Seasonal extensions add corresponding terms at seasonal lags. Reference: FPP3, Chapter 9.
- **[Holt–Winters and ETS](https://otexts.com/fpp3/expsmooth.html)** — 2021. Smooths level, trend and seasonality recursively. ETS supplies statistical state-space formulations and forecast distributions. Reference: FPP3, Chapter 8.
- **[STL decomposition](https://otexts.com/fpp3/stl.html)** — 2021. Uses Loess smoothing to separate trend, seasonal and remainder components. Seasonal variation may change over time; robust fitting limits outlier influence on the smooth components.
- **[Dynamic regression](https://otexts.com/fpp3/dynamic.html)** — 2021. Combines regression predictors with ARIMA errors. Forecasts require future predictor values or scenarios; ordinary intervals condition on these values rather than propagating their uncertainty.
- **[Vector autoregression](https://otexts.com/fpp3/VAR.html)** — 2021. Models several series jointly, regressing each on lags of all series. Stationarity and differencing determine the appropriate specification.
- **[GARCH](https://www.sciencedirect.com/science/article/pii/0304407686900631)** — 1986. Generalizes ARCH by allowing past conditional variances into the current variance equation. Studies stationarity, estimation and testing for time-varying volatility.
- **[Kalman filtering](https://doi.org/10.1115/1.3662552)** — 1960. Formulates linear filtering through state transitions and recursive error-covariance updates. Treats stationary and nonstationary prediction problems in a common framework.
- **[Hidden Markov models](https://doi.org/10.1109/5.18626)** — 1989. Rabiner reviews Markov models with hidden states and probabilistic observations, with applications to speech recognition. A reference for the model's statistical structure and inference problems.
- **[Infinite HMM](https://papers.nips.cc/paper/1956-the-infinite-hidden-markov-model.pdf)** — 2001. Uses Dirichlet processes to extend HMMs to countably many possible hidden states, integrating out transition parameters rather than fixing a finite state count in advance.
- **[Dynamic time warping](https://doi.org/10.1109/TASSP.1978.1163055)** — 1978. Aligns sequences by optimizing a nonlinear time-warping path with dynamic programming. Sakoe–Chiba studies path constraints for spoken-word matching; this is an alignment method, not a forecasting model.

## Neural forecasting

- **[DeepAR](https://arxiv.org/abs/1704.04110)** — 2017. Trains an autoregressive recurrent network across related time series to produce probabilistic forecasts, sharing statistical information across series.
- **[N-BEATS](https://arxiv.org/abs/1905.10437)** — 2019. Uses fully connected blocks with forward and backward residual connections for forecasting. Provides generic and explicitly interpretable configurations.
- **[Temporal Fusion Transformer](https://arxiv.org/abs/1912.09363)** — 2019. Combines recurrent processing and attention for multi-horizon forecasts. Separately accommodates static covariates, known future inputs and historically observed variables.
- **[Chronos](https://arxiv.org/abs/2403.07815)** — 2024. Scales and quantizes time-series values into tokens, then trains transformer language models with cross-entropy. Sampling token sequences produces probabilistic forecasts.
- **[PatchTST](https://arxiv.org/abs/2211.14730)** — 2022. Treats time-series patches as tokens and processes each channel separately with shared embedding and transformer weights; designed for forecasting and self-supervised pretraining.

## Dynamical and mechanistic models

- **[Simple discrete dynamics](https://www.nature.com/articles/261459a0)** — 1976. Shows how simple first-order nonlinear difference equations can produce stable equilibria, cycles or irregular fluctuations. A foundation for studying deterministic complexity.
- **[Predator–prey inference](https://mc-stan.org/learn-stan/case-studies/lotka-volterra-predator-prey.html)** — 2018. Fits Lotka–Volterra differential equations with a statistical observation model to lynx–hare pelt counts. Demonstrates Bayesian parameter inference and posterior predictive checks.
- **[Lorenz dynamics](https://doi.org/10.1175/1520-0469%281963%29020%3C0130%3ADNF%3E2.0.CO%3B2)** — 1963. Studies a deterministic nonlinear convection model whose nearby initial states can diverge. Connects nonperiodic dynamics to limits of long-range prediction.
- **[Bass diffusion](https://doi.org/10.1287/mnsc.15.5.215)** — 1969. Models initial product adoption using innovative and imitative behavior: purchase timing depends on previous buyers. The original study tests the model on consumer durables.
- **[Bass model retrospective](https://doi.org/10.1287/mnsc.1040.0300)** — 2004. Reviews the origins, applications and extensions of the product-diffusion model, identifying subsequent research directions.
- **[SIR epidemic dynamics](https://doi.org/10.1098/rspa.1927.0118)** — 1927. Models infection and removal in a susceptible population under simplifying assumptions about contact and immunity. Epidemics can end while susceptible individuals remain.
- **[DICE](https://elischolar.library.yale.edu/cowles-discussion-paper-series/1252/)** — 1992. Describes an integrated climate–economy model for dynamic optimization of climate policy. Documents the structure and assumptions behind its cost–benefit analysis.

## Evaluation and software

- **[Conformal prediction overview](https://arxiv.org/abs/2107.07511)** — 2021. Reviews calibration-score methods for prediction sets with finite-sample marginal coverage under exchangeability. This guarantee does not imply coverage at each individual input.
- **[Forecast evaluation](https://otexts.com/fpp3/accuracy.html)** — 2021. Compare against naïve and seasonal-naïve baselines. Evaluate held-out point forecasts and distributions separately; scaled errors support comparisons across series with different units.
- **[Rolling-origin validation](https://otexts.com/fpp3/tscv.html)** — 2021. Repeatedly trains on past observations and evaluates later ones. Use forecast horizons matching deployment; fitting residuals do not measure future forecast accuracy.
- **[rpart](https://cran.r-project.org/web/packages/rpart/)** — R implementation of recursive partitioning for classification, regression and survival trees, based on CART.
- **[party](https://cran.r-project.org/web/packages/party/)** — R toolbox for conditional-inference trees, forests and model-based recursive partitioning. Supports response types including censored and multivariate outcomes.
- **[mgcv](https://cran.r-project.org/web/packages/mgcv/index.html)** — R implementation of generalized additive and additive mixed models, with smoothing-parameter estimation and several response-distribution families.

## Related Topics

- [Neural Networks](https://mlpapers.org/neural-nets/)
- [Ensemble Learning](https://mlpapers.org/ensemble-learning/)
- [Bayesian Networks](https://mlpapers.org/bayesian-nets/)
- [Interpretability](https://mlpapers.org/interpretability/)
- [Optimization](https://mlpapers.org/optimization/)
- [Clustering](https://mlpapers.org/clustering/)

# Machine Learning and Statistical Models

🔒 Full text at this link requires payment or institutional access. Unmarked links may be unchecked.

## Linear and generalized linear models

- **Least squares and ridge** - Least squares minimizes squared prediction errors; ridge adds a squared-coefficient penalty to stabilize fits with correlated predictors. [docs](<https://scikit-learn.org/stable/modules/linear_model.html>).
- **Generalized linear models** - Connects an exponential-family response mean to a linear predictor through a link function. Unifies models fitted by iteratively weighted linear regression. [Nelder and Wedderburn 1972](<https://www.maths.usyd.edu.au/u/jchan/GLM/Nelder1972GLM.pdf> "Generalized Linear Models; JRSS A").
- **Generalized linear mixed models** - Adds random effects to GLMs for correlated observations and overdispersion. Breslow-Clayton develops approximate inference using penalized quasi-likelihood. [Breslow and Clayton 1993](<https://doi.org/10.1080/01621459.1993.10594284> "Approximate Inference in Generalized Linear Mixed Models; JASA").
- **Lasso** - Constrains the sum of absolute regression coefficients, shrinking some exactly to zero. Combines estimation and variable selection. [Tibshirani 1996](<https://doi.org/10.1111/j.2517-6161.1996.tb02080.x> "Regression Shrinkage and Selection Via the Lasso; JRSS B").
- **Logistic regression** - Models binary class probability through a logistic link applied to a linear score. The documented implementation also supports multiclass classification and regularization. [docs](<https://scikit-learn.org/stable/modules/linear_model.html#logistic-regression>).
- **Elastic net** - Combines L1 and L2 penalties, allowing sparse coefficients while retaining ridge-style shrinkage. A useful alternative to lasso for correlated predictors. [Zou and Hastie 2005](<https://doi.org/10.1111/j.1467-9868.2005.00503.x> "Regularization and Variable Selection Via the Elastic Net; JRSS B"); [docs](<https://scikit-learn.org/stable/modules/linear_model.html#elastic-net>).
- **Tests as linear models** - Worked connections between regression, t-tests, correlation and ANOVA. Rank-based analogues are also discussed; some equivalences are approximate. [Lindeløv 2019](<https://lindeloev.github.io/tests-as-linear/> "Common statistical tests are linear models (or: how to teach stats); online article").

## Additive models and adaptive splines

- **Generalized additive models** - Replaces a GLM's linear predictor terms with smooth functions of individual inputs. Local scoring extends additive regression to different response distributions. [Hastie and Tibshirani 1986](<https://doi.org/10.1214/ss/1177013604> "Generalized Additive Models; Statist. Sci.").
- **MARS** - Builds regression models from products of spline basis functions, selecting their number, variables and knot locations from data. Separates additive contributions from interactions. [Friedman 1991](<https://doi.org/10.1214/aos/1176347963> "Multivariate Adaptive Regression Splines; Ann. Statist.").
- **Intelligible classification and regression** - Studies additive models whose individual feature contributions can be plotted, comparing fitting methods and the accuracy cost of restricting interactions. [Lou et al. 2012](<https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf> "Intelligible models for classification and regression; KDD").
- **GAMs with autoregressive terms** - Combines nonlinear covariate terms with autoregression for serially correlated outcomes. Demonstrated on temperature and daily mortality. [Yang et al. 2012](<https://link.springer.com/article/10.1186/1471-2288-12-165> "Using a generalized additive model with autoregressive terms to study the effects of daily temperature on mortality; BMC Med Res Methodol").
- **GA2M** - Extends additive models with selected pairwise interactions. FAST ranks candidate feature pairs, keeping explanations as one- and two-dimensional functions. [Lou et al. 2013](<https://www.cs.cornell.edu/~yinlou/papers/lou-kdd13.pdf> "Accurate intelligible models with pairwise interactions; KDD").
- **Intelligible healthcare models** - Pneumonia and readmission case studies use additive models with pairwise interactions to expose unexpected learned associations and revise models. [Caruana et al. 2015](<https://www.microsoft.com/en-us/research/publication/intelligible-models-healthcare-predicting-pneumonia-risk-hospital-30-day-readmission/> "Intelligible Models for HealthCare: Predicting Pneumonia Risk and Hospital 30-day Readmission; KDD").
- **Neural Additive Models** - Jointly trains a separate neural network for each input feature, then combines their outputs linearly. Learns flexible univariate shapes while preserving additive structure. [Agarwal et al. 2021](<https://arxiv.org/abs/2004.13912> "Neural Additive Models: Interpretable Machine Learning with Neural Nets; NeurIPS").
- **How trustworthy are GAMs?** - Shows that similarly accurate GAMs can learn conflicting feature shapes. Compares inductive biases, sparsity and behavior on rare subpopulations; accuracy alone does not validate an explanation. [Chang et al. 2021](<https://arxiv.org/abs/2006.06466> "How Interpretable and Trustworthy are GAMs?; KDD").

## Trees and tabular prediction

- **CART** - Recursively partitions feature space into regions with simple predictions. Depth and pruning control complexity; individual trees can be unstable under changes to training data. [docs](<https://scikit-learn.org/stable/modules/tree.html>).
- **Random forests** - Combines randomized trees, including random feature selection at splits. Analyzes how individual tree strength and dependence affect ensemble error. [Breiman 2001](<https://link.springer.com/article/10.1023/A:1010933404324> "Random Forests; Mach. Learn.").
- **Bayesian additive regression trees** - Represents a response as a sum of trees with a regularization prior that keeps individual trees weak. Bayesian backfitting samples the model and its predictive uncertainty. [Chipman et al. 2010](<https://arxiv.org/abs/0806.3286> "BART: Bayesian additive regression trees; Ann. Appl. Stat.").
- **XGBoost** - Gradient-boosted trees with sparsity-aware split finding and a weighted quantile sketch for approximate tree learning. The paper also addresses cache access and distributed computation. [Chen and Guestrin 2016](<https://arxiv.org/abs/1603.02754> "XGBoost: A Scalable Tree Boosting System; KDD").
- **CatBoost** - Uses ordered boosting and categorical-feature processing to address prediction shift caused by target leakage during training. [Prokhorenkova et al. 2018](<https://arxiv.org/abs/1706.09516> "CatBoost: unbiased boosting with categorical features; NeurIPS").
- **TabPFN: original classifier** - Pretrains a transformer on synthetic classification tasks. At inference, labeled training rows provide context for predictions without updating the model weights; the original scope is small tabular datasets. [Hollmann et al. 2023](<https://arxiv.org/abs/2207.01848> "TabPFN: A Transformer That Solves Small Tabular Classification Problems in a Second; ICLR").
    - **TabPFN: classification and regression** - Extends prior-data-fitted tabular prediction to regression, categorical inputs and missing values. A pretrained transformer performs in-context prediction from labeled examples. [Hollmann et al. 2025](<https://www.nature.com/articles/s41586-024-08328-6> "Accurate predictions on small data with a tabular foundation model; Nature").
- **TabM** - Builds parameter-sharing ensembles of multilayer perceptrons for tabular prediction. Joint training produces multiple predictions without storing a separate full network for every ensemble member. [Gorishniy et al. 2025](<https://arxiv.org/abs/2410.24210> "TabM: Advancing Tabular Deep Learning with Parameter-Efficient Ensembling; ICLR").
- **TabICL** - Combines representations of table rows with a transformer for in-context classification. Synthetic-task pretraining supports prediction on new tables without task-specific weight updates. [Qu et al. 2025](<https://arxiv.org/abs/2502.05564> "TabICL: A Tabular Foundation Model for In-Context Learning on Large Data; ICML").

### Observation protocols

- **Repeated measurements** - At low noise, repeats can harm new-input prediction. IID priors linking inputs and responses count repeats as fresh input evidence even with exact inference; TabPFN-v3's row-count-dependent attention adds harm. Averaging often helps with many repeats. [Liu et al. 2026](<https://arxiv.org/abs/2610.16801v1> "When Repeated Measurements Hurt Tabular Foundation Models; arXiv").

### Compression of tabular models

- **Tabular-model compression** - Fits affine replacements to target-table activations. Across eight models and 171 classification datasets, halving depth costs at most 0.002 median AUROC per model; single-block regression deteriorates more sharply. [Cannistraci and Vogt 2026](<https://arxiv.org/abs/2610.13253v1> "Tabular Foundation Models Are Effectively Shallow; arXiv").

## Local and conditional-independence classifiers

- **Nearest-neighbor classification** - Predicts from nearby labeled examples. Cover and Hart bound asymptotic one-neighbor error by twice Bayes error under their assumptions; this is neither a finite-sample guarantee nor a guarantee for an arbitrary learned distance. [Cover and Hart 1967](<https://isl.stanford.edu/~cover/papers/transIT/0021cove.pdf> "Nearest neighbor pattern classification; IEEE Trans. Inform. Theory").
- **Naive Bayes** - Multiplies class-conditional feature probabilities under an independence model. Domingos and Pazzani show that correct class decisions can survive some dependence violations even when estimated probabilities are inaccurate. [Domingos and Pazzani 1997](<https://link.springer.com/article/10.1023/A:1007413511361> "On the Optimality of the Simple Bayesian Classifier under Zero-One Loss; Mach. Learn.").

## Support-vector methods

- **Support-vector networks** - Constructs a linear decision surface in a nonlinear feature space and extends the approach to nonseparable training data. A foundation for kernel-based classification. [Cortes and Vapnik 1995](<https://link.springer.com/article/10.1007/BF00994018> "Support-vector networks; Mach. Learn.").
- **SVM implementations** - Linear and kernel classification, regression and outlier detection. Decision scores are not probabilities; probability estimation adds a separate fitting step. [docs](<https://scikit-learn.org/stable/modules/svm.html>).

## Probabilistic prediction, survival and treatment effects

- **Kaplan-Meier** - Estimates a survival curve from incomplete lifetime observations using a product-limit estimator. Independent censoring is a substantive assumption, explicitly discussed in the paper. [Kaplan and Meier 1958](<https://doi.org/10.1080/01621459.1958.10501452> "Nonparametric Estimation from Incomplete Observations; JASA").
- **Cox regression** - Models covariate effects as multipliers of an unspecified baseline hazard. Handles censored event times without choosing a parametric baseline distribution. [Cox 1972](<https://doi.org/10.1111/j.2517-6161.1972.tb00899.x> "Regression Models and Life-Tables; JRSS B").
    - **DeepSurv** - Uses a neural network for the risk function in a Cox proportional-hazards model, allowing nonlinear covariate interactions in survival prediction. [Katzman et al. 2018](<https://arxiv.org/abs/1606.00931> "DeepSurv: Personalized Treatment Recommender System Using A Cox Proportional Hazards Deep Neural Network; BMC Med Res Methodol").
- **Quantile regression forests** - Extends random forests to estimate the conditional response distribution and its quantiles, rather than only a conditional mean. [Meinshausen 2006](<https://jmlr.csail.mit.edu/papers/volume7/meinshausen06a/meinshausen06a.pdf> "Quantile Regression Forests; JMLR").
- **Treatment-effect meta-learners** - Builds estimators of conditional average treatment effects from existing regression learners. Introduces the X-learner and studies settings with unequal treatment-group sizes. [Künzel et al. 2019](<https://arxiv.org/abs/1706.03461> "Meta-learners for Estimating Heterogeneous Treatment Effects using Machine Learning; PNAS").
- **Simpson's paradox** - Constructs examples where conditioning on additional variables reverses an association. Illustrates the dependence of aggregated comparisons on the variables included in an analysis. [Fenton et al. 2019](<https://arxiv.org/abs/1912.01422> "Simpson&#x27;s Paradox and the implications for medical trials; arXiv").
- **NGBoost** - Boosts parameters of a conditional probability distribution using natural gradients, extending boosting from point estimates to probabilistic regression. [Duan et al. 2020](<https://arxiv.org/abs/1910.03225> "NGBoost: Natural Gradient Boosting for Probabilistic Prediction; ICML").

## Classical forecasting and latent states

- **Kalman filtering** - Formulates linear filtering through state transitions and recursive error-covariance updates. Treats stationary and nonstationary prediction problems in a common framework. [Kalman 1960](<https://doi.org/10.1115/1.3662552> "A New Approach to Linear Filtering and Prediction Problems; Journal of Basic Engineering").
- **Dynamic time warping** - Aligns sequences by optimizing a nonlinear time-warping path with dynamic programming. Sakoe-Chiba studies path constraints for spoken-word matching; this is an alignment method, not a forecasting model. [Sakoe and Chiba 1978](<https://doi.org/10.1109/TASSP.1978.1163055> "Dynamic programming algorithm optimization for spoken word recognition; IEEE Trans. Acoust., Speech, Signal Process.").
- **Hidden Markov models** - Rabiner reviews Markov models with hidden states and probabilistic observations, with applications to speech recognition. A reference for the model's statistical structure and inference problems. [Rabiner 1989](<https://doi.org/10.1109/5.18626> "A tutorial on hidden Markov models and selected applications in speech recognition; Proc. IEEE").
- **Infinite HMM** - Uses Dirichlet processes to extend HMMs to countably many possible hidden states, integrating out transition parameters rather than fixing a finite state count in advance. [Beal et al. 2001](<https://papers.nips.cc/paper/1956-the-infinite-hidden-markov-model.pdf> "The Infinite Hidden Markov Model; NeurIPS").
- **Forecasting models** - ARIMA, exponential smoothing and conditional-volatility models address different temporal structures. See [Time Series Forecasting](https://mlpapers.org/time-series-forecasting/) for methods and comparisons.

## Neural forecasting

- **Neural forecasting methods** - Global models share information across series; pretrained forecasters transfer across datasets. See [Time Series Forecasting](https://mlpapers.org/time-series-forecasting/) for architectures and comparative evidence.

## Dynamical and mechanistic models

- **SIR epidemic dynamics** - Models infection and removal in a susceptible population under simplifying assumptions about contact and immunity. Epidemics can end while susceptible individuals remain. [Kermack and McKendrick 1927](<https://doi.org/10.1098/rspa.1927.0118> "A contribution to the mathematical theory of epidemics; Proc. R. Soc. A").
- **Predator-prey inference** - Fits Lotka-Volterra differential equations with a statistical observation model to lynx-hare pelt counts. Demonstrates Bayesian parameter inference and posterior predictive checks. [docs](<https://mc-stan.org/learn-stan/case-studies/lotka-volterra-predator-prey.html>).
- **Lorenz dynamics** - Studies a deterministic nonlinear convection model whose nearby initial states can diverge. Connects nonperiodic dynamics to limits of long-range prediction. [Lorenz 1963](<https://doi.org/10.1175/1520-0469%281963%29020%3C0130%3ADNF%3E2.0.CO%3B2> "Deterministic Nonperiodic Flow; J. Atmos. Sci.").
- **Bass diffusion** - Models initial product adoption using innovative and imitative behavior: purchase timing depends on previous buyers. The original study tests the model on consumer durables. [Bass 1969](<https://doi.org/10.1287/mnsc.15.5.215> "A New Product Growth for Model Consumer Durables; Management Science").
    - **Bass model retrospective** - Reviews the origins, applications and extensions of the product-diffusion model, identifying subsequent research directions. [Bass 2004](<https://doi.org/10.1287/mnsc.1040.0300> "Comments on “A New Product Growth for Model Consumer Durables The Bass Model”; Management Science").
- **Simple discrete dynamics** - Shows how simple first-order nonlinear difference equations can produce stable equilibria, cycles or irregular fluctuations. A foundation for studying deterministic complexity. [May 1976 🔒](<https://www.nature.com/articles/261459a0> "Simple mathematical models with very complicated dynamics; Nature").
- **DICE** - Describes an integrated climate-economy model for dynamic optimization of climate policy. Documents the structure and assumptions behind its cost-benefit analysis. [Nordhaus 1992](<https://elischolar.library.yale.edu/cowles-discussion-paper-series/1252/> "The ‘Dice’ Model: Background and Structure of a Dynamic Integrated Climate-Economy Model of the Economics of Global Warming; Cowles discussion paper").

<a id="evaluation-and-software"></a>

## Evaluation

- **Conformal prediction overview** - Reviews calibration-score methods for prediction sets with finite-sample marginal coverage under exchangeability. This guarantee does not imply coverage at each individual input. [Angelopoulos and Bates 2023](<https://arxiv.org/abs/2107.07511> "A Gentle Introduction to Conformal Prediction and Distribution-Free Uncertainty Quantification; Foundations and Trends in Machine Learning").
- **Decision-focused prediction** - Prediction error and downstream decision cost are different training targets. See [Optimization](https://mlpapers.org/optimization/) for learning predictions through the decisions they induce.

## Software

- **rpart** - R implementation of recursive partitioning for classification, regression and survival trees, based on CART. [code](<https://cran.r-project.org/web/packages/rpart/>).
- **party** - R toolbox for conditional-inference trees, forests and model-based recursive partitioning. Supports response types including censored and multivariate outcomes. [code](<https://cran.r-project.org/web/packages/party/>).
- **mgcv** - R implementation of generalized additive and additive mixed models, with smoothing-parameter estimation and several response-distribution families. [code](<https://cran.r-project.org/web/packages/mgcv/index.html>).

## Related topics

- [Neural Networks](https://mlpapers.org/neural-nets/)
- [Ensemble Learning](https://mlpapers.org/ensemble-learning/)
- [Bayesian Networks](https://mlpapers.org/bayesian-nets/)
- [Interpretability](https://mlpapers.org/interpretability/)
- [Optimization](https://mlpapers.org/optimization/)
- [Clustering](https://mlpapers.org/clustering/)
- [Time Series Forecasting](https://mlpapers.org/time-series-forecasting/)

# Machine learning and statistical models

### General
- **Linear models**
  - `y = Xβ + ε`
  - [Common statistical tests are linear models (or: how to teach stats)]() *Jonas Kristoffer Lindeløv*
- **GLM**
  - [Generalized Linear Model](https://docs.ufpr.br/~taconeli/CE225/Artigo.pdf) (1972) *J. A. Nelder, R. W. M. Wedderburn*
- **GLMM** Generalized linear mixed-effect model
  - `y = Xβ + Zu + ε`
- **LASSO**
- **MARS/Earth** Multivariate Adaptive Regression Splines
  - `y = ΣcⱼBⱼ(x)`
- **GAM, GA2M, GAMM** Additive Models ([Wiki](https://en.wikipedia.org/wiki/Generalized_additive_model))
  - `g(E(y)) = β + Σfⱼ(xⱼ)` or `g(E(y)) = β + Σfⱼ(xⱼ)+ Σfᵢⱼ(xᵢ,xⱼ)`
  - [Generalized Additive Models](https://projecteuclid.org/euclid.ss/1177013604) (1986) *T. Hastie, R. Tibshirani*
  - [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) (2012) *Yin Lou, Rich Caruana, Johannes Gehrke*
  - [Accurate Intelligible Models with Pairwise Interactions](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd13.pdf) (2013) *Yin Lou, Rich Caruana, Johannes Gehrke, Giles Hooker*
  - [Intelligible Models for HealthCare: Predicting Pneumonia Risk and Hospital 30-day Readmission](https://www.microsoft.com/en-us/research/publication/intelligible-models-healthcare-predicting-pneumonia-risk-hospital-30-day-readmission/) (2015) *Rich Caruana, Paul Koch, Yin Lou, Marc Sturm, Johannes Gehrke, Noemie Elhadad*
  - [Using a generalized additive model with autoregressive terms to study the effects of daily temperature on mortality](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3549928/#!po=1.47059) (2012) *Lei Yang, Guoyou Qin, Guixiang Song*
  - [Generalized additive neural networks](https://dl.acm.org/doi/10.1145/312129.312228) (1999) *William J. E. Potts*
  - [Neural Additive Models:Interpretable Machine Learning with Neural Nets](https://arxiv.org/pdf/2004.13912.pdf) (2020) *Rishabh Agarwal, Nicholas Frosst, Xuezhou Zhang, Rich Caruana, Geoffrey E. Hinton*
- **Simpson Paradox** ([Wiki](https://en.wikipedia.org/wiki/Simpson's_paradox))
  - [Simpson's Paradox and the implications for medical trials](https://arxiv.org/pdf/1912.01422) (2019) *Norman Fenton, Martin Neil, Anthony Constantinou*
- **Quantile Regression** ([Wiki](https://en.wikipedia.org/wiki/Quantile_regression))
  - [Quantile Regression Forests](http://jmlr.csail.mit.edu/papers/volume7/meinshausen06a/meinshausen06a.pdf) (2006) *Nicolai Meinshausen*
  - [Probabilistic forecasting approaches for extreme NO2 episodes: acomparison of models](https://arxiv.org/pdf/2003.11356.pdf) (2020) *Sebastian Perez Vasseur, Jose L. Aznarte*

### Trees
- **CART**
  - rpart ([CRAN](https://cran.r-project.org/web/packages/rpart/))
  - party ([CRAN](https://cran.r-project.org/web/packages/party/))
- **BART** Bayesian Additive Regression Trees### Uplift models

### Survival models

### Timeseries
- **Hidden Markov Model** ([Wiki](https://en.wikipedia.org/wiki/Hidden_Markov_model))
- **ARIMA** Autoregressive Integrated Moving Average
- **ARIMAX** (Seasonal)
- **ARMA-GARCH**
- **SSM** State Space Models
- **VAR** Vector autoregressions
- **Holt-Winters exponential smoothing**
- **Loess model** Seasonal decomposition
- **CHARME** Conditional Heteroscedastic Autoregressive Mixture of Experts
- **Dynamic time warping** [Wiki](https://en.wikipedia.org/wiki/Dynamic_time_warping)

### Systems modeling
- **Predator-Prey** Lotka–Volterra equations ([Wiki](https://en.wikipedia.org/wiki/Lotka%E2%80%93Volterra_equations))
  - [Using predator-prey models on the Canadian lynx series](https://statmodeling.stat.columbia.edu/2012/01/28/the-last-word-on-the-canadian-lynx-series/)

### [Bayesian networks](https://github.com/mlpapers/bayesian-nets)
### [Ensembles](https://github.com/mlpapers/ensemble-learning)
### [Neural nets](https://github.com/mlpapers/neural-nets)


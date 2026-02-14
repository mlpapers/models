---
title: "Machine Learning and Statistical Models"
aliases: ["ML models", "Statistical models", "Predictive models"]
tags:
  - supervised
  - regression
  - classification
---
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
  - [How Interpretable and Trustworthy are GAMs?](https://arxiv.org/pdf/2006.06466.pdf) (2020) *Chun-Hao Chang, Sarah Tan, Ben Lengerich, Anna Goldenberg, Rich Caruana*
- **Simpson Paradox** ([Wiki](https://en.wikipedia.org/wiki/Simpson's_paradox))
  - [Simpson's Paradox and the implications for medical trials](https://arxiv.org/pdf/1912.01422) (2019) *Norman Fenton, Martin Neil, Anthony Constantinou*
- **Quantile Regression** ([Wiki](https://en.wikipedia.org/wiki/Quantile_regression))
  - [Quantile Regression Forests](http://jmlr.csail.mit.edu/papers/volume7/meinshausen06a/meinshausen06a.pdf) (2006) *Nicolai Meinshausen*
  - [Probabilistic forecasting approaches for extreme NO2 episodes: acomparison of models](https://arxiv.org/pdf/2003.11356.pdf) (2020) *Sebastian Perez Vasseur, Jose L. Aznarte*

### Trees
- **CART** Classification And Regression Tree
  - rpart ([CRAN](https://cran.r-project.org/web/packages/rpart/))
  - party ([CRAN](https://cran.r-project.org/web/packages/party/))
- **BART** Bayesian Additive Regression Trees### Uplift models

### SVM

### Survival models

### Timeseries
- [Forecasting: Principles and Practice](https://otexts.com/fpp2/) (2018) *Rob J Hyndman, George Athanasopoulos*
- **Kalman Filters** ([Wiki](https://en.wikipedia.org/wiki/Kalman_filter))
  - [A new approach to linear filtering and prediction problems](http://www.cs.unc.edu/~welch/kalman/media/pdf/Kalman1960.pdf) (1960) *R. E. Kalman*
- **Hidden Markov Model** ([Wiki](https://en.wikipedia.org/wiki/Hidden_Markov_model))
  - [A tutorial on Hidden Markov Models and selected applications in speech recognition](https://www.ece.ucsb.edu/Faculty/Rabiner/ece259/Reprints/tutorial%20on%20hmm%20and%20applications.pdf) (1989) *Lawrence R. Rabiner*
  - [The Infinite Hidden Markov Model](http://papers.nips.cc/paper/1956-the-infinite-hidden-markov-model.pdf) *Matthew J. Beal, Zoubin Ghahramani, Carl Edward Rasmussen*
- **ARIMA** Autoregressive Integrated Moving Average
- **ARIMAX** (Seasonal)
- **ARMA-GARCH**
- **SSM** State Space Models
- **VAR** Vector autoregressions
- **Holt-Winters exponential smoothing**
- **Loess model** Seasonal decomposition
- **Dynamic regression models**
- **CHARME** Conditional Heteroscedastic Autoregressive Mixture of Experts
- **Dynamic time warping** [Wiki](https://en.wikipedia.org/wiki/Dynamic_time_warping)

### Systems modeling
> The coming century will be dominated by major social, political turmoil. And it will result primarily because people are doing what they think they should do, but do not realize that what they’re doing are causing these problems. So, I think the hope for this coming century is to develop a sufficiently large percentage of the population that have true insight into the nature of the complex systems within which they live. - Jay Forrester
- **Logistic Chaos**
  - [Logistic Equation](https://www.stsci.edu/~lbradley/seminar/logdiffeqn.html)
- **Predator-Prey** Lotka–Volterra equations ([Wiki](https://en.wikipedia.org/wiki/Lotka%E2%80%93Volterra_equations))
  - [Using predator-prey models on the Canadian lynx series](https://statmodeling.stat.columbia.edu/2012/01/28/the-last-word-on-the-canadian-lynx-series/)
- **Lorenz attractor** ([Wiki](https://en.wikipedia.org/wiki/Lorenz_system))
- **Bass diffusion model** ([Wiki](https://en.wikipedia.org/wiki/Bass_diffusion_model))
  - [Comments on “A New Product Growth for Model Consumer Durables The Bass Model”](https://pubsonline.informs.org/doi/10.1287/mnsc.1040.0300) (2004) *Frank M. Bass*
- **SIR, SEIR**
- **DICE** Dynamic Integrated Climate-Economy model ([Wiki](https://en.wikipedia.org/wiki/DICE_model))
  - [The "Dice" Model: Background and Structure of a Dynamic Integrated Climate-Economy Model of the Economics of Global Warming](http://cowles.yale.edu/sites/default/files/files/pub/d10/d1009.pdf) (1992) *W. Nordhaus*




## Related Topics
- [Neural Networks](https://mlpapers.org/neural-nets/)
- [Ensemble Learning](https://mlpapers.org/ensemble-learning/)
- [Bayesian Networks](https://mlpapers.org/bayesian-nets/)
- [Interpretability](https://mlpapers.org/interpretability/)
- [Optimization](https://mlpapers.org/optimization/)
- [Clustering](https://mlpapers.org/clustering/)

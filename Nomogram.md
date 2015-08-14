#### rms

rms on CRAN: [tutorial](http://cran.r-project.org/web/packages/rms/rms.pdf), github [demo codes](https://github.com/harrelfe/rms), or a more friendly tutorial on [R Documentation](http://www.rdocumentation.org/packages/rms),
its [main web](http://biostat.mc.vanderbilt.edu/wiki/Main/RmS) is maintained by Dr. Frank E Harrell Jr.

E.g.
Three updated papers: 2015 on JCO from Dr. He - for [Resected Non–Small-Cell Lung Cancer](http://jco.ascopubs.org/content/33/8/861.long), attached coding in supp

2014 Updated Prognostic Model (http://jco.ascopubs.org/content/32/7/671.long) on JCO from [Duke Cancer Center](https://www.cancer.duke.edu/Nomogram/), 2013 Prognostic Model on [JNCI](http://jnci.oxfordjournals.org/content/105/22/1729.long), both of them in Prostate Cancer.
2003 [Prognostic Model](http://jco.ascopubs.org/content/21/7/1232.full) for Predicting Survival in Men With Hormone-Refractory Metastatic Prostate Cancer on JCO from Duke Center.

2012 [Nomogram prediction](http://www.nature.com/bjc/journal/v107/n6/full/bjc2012340a.html) for overall survival of patients diagnosed with cervical cancer on BJC

##### Developing Packages (based on rms)

[SvyNom](https://cran.r-project.org/web/packages/SvyNom/index.html) package and the paper "Building a Nomogram for Survey-Weighted Cox Models Using R" on [JSS](http://www.jstatsoft.org/v64/c01/paper), on the CRAN Task View: [Survival Analysis](https://cran.r-project.org/web/views/Survival.html).

[DynNom](https://cran.r-project.org/web/packages/DynNom/index.html) package: A Dynamic Nomogram for Linear and Generalized Linear Models as [Shiny Applications](http://www.xueqing.cc/course/index/view/id/24). 



--
Popular [machineLearning](http://cran.r-project.org/web/views/MachineLearning.html) tools includes `glmnet` package, `penalized` package.

#### glmnet
[glmnet_vignette](http://web.stanford.edu/~hastie/Papers/Glmnet_Vignette.pdf) from UStanford

[glmnet](http://www.rdocumentation.org/packages/glmnet/functions/glmnet):
glmnet(x, y, family=c("gaussian","binomial","poisson","multinomial","cox","mgaussian"), weights, alpha = 1, nlambda = 100,
standardize = TRUE, penalty.factor = rep(1, nvars), lower.limits=-Inf, type.multinomial="grouped",
`alpha` - 0 for ridge, 1 for lasso (elastic-net mixing parameter α)

[plot.glmnet](http://www.rdocumentation.org/packages/glmnet/functions/plot.glmnet):
plot(x, xvar = c("norm", "lambda", "dev"), label = FALSE,type.coef=c("coef","2norm"), ...)

[predict.glmnet](http://www.rdocumentation.org/packages/glmnet/functions/predict.glmnet):
predict(object, newx, s = c(...,...), 
type=c("link","response","coefficients","nonzero","class"), exact = FALSE, ...): 
`link` - log(odds), **`response`** - odds, `coef` - when s, `nonzero` - indices, `class` - binominal/multinomial
s - `lambda.min` in predict.cv.glmnet

[cv.glmnet](http://www.rdocumentation.org/packages/glmnet/functions/cv.glmnet):
(x, y, family = , weights, s = , type.measure = ..., nfolds, foldid, grouped, ...), 
type.multinomial = "grouped", `mse` - cox, poisson, `class` - binominal/multinomial,
opt.lam = c(cvfit$lambda.min, cvfit$lambda.1se)
coef(cvfit, s = `opt.lam`)

[plot.cv.glmnet](http://www.rdocumentation.org/packages/glmnet/functions/plot.cv.glmnet)

[predict.cv.glmnet](http://www.rdocumentation.org/packages/glmnet/functions/predict.cv.glmnet):
predict(cvfit, newx, s="lambda.min", type...), type is the *same* as predict.glmnet: `class` - binominal/multinomial

#### penalzied 
[penalized](http://www.rdocumentation.org/packages/penalized); 
[penalized_vignettes](http://cran.r-project.org/web/packages/penalized/vignettes/penalized.pdf)

#### random survival forest
[randomForestSRC](http://cran.r-project.org/web/packages/randomForestSRC/index.html) for survival analysis and
[ggRandomForests](http://cran.r-project.org/web/packages/ggRandomForests/) for plot - CRAN, github l[ink](https://github.com/ehrlinger/ggRandomForests), handy [doc](http://www.rdocumentation.org/packages/ggRandomForests).


Q & A:

Brier score and Harrel's C-Index in glmnet [something wrong](http://r.789695.n4.nabble.com/Interperting-results-of-glmnet-and-coxph-plot-Brier-score-and-Harrel-s-C-Index-am-I-doing-something--td4677166.html);

[warning message](https://stat.ethz.ch/pipermail/r-help/2012-May/312029.html) from stat.ethz.ch


#### Examples:
How to build and interpret [a nomogram for cancer prognosis](http://jco.ascopubs.org/content/26/8/1364.long),
citations in [2011](http://www.ncbi.nlm.nih.gov/pubmed/22084366), [2012,a](http://www.ncbi.nlm.nih.gov/pubmed/22253459), [2012,b](http://www.ncbi.nlm.nih.gov/pubmed/22734034) and [2014](http://www.ncbi.nlm.nih.gov/pubmed/24419130) on JCO. 
[Nomograms in oncology](http://www.sciencedirect.com/science/article/pii/S1470204514711167): more than meets the eye on Lancet Oncol. 2015.

[NAT](http://onlinelibrary.wiley.com/doi/10.1002/cncr.28447/full) - esophageal cancer, 2014

[Clinical Prediction Models](http://onlinelibrary.wiley.com/doi/10.1111/j.1751-5823.2009.00085_22.x): A Practical Approach to Development, Validation, and Updating, 2009. 
Data sets and `R` code were also supplied, e.g. [case study on survival data](http://www.clinicalpredictionmodels.org/doku.php?id=rcode_and_data:chapter23). This chapter went through the *seven steps* of the checklist for developing valid prediction models.
It was cited by, [a new framework](http://www.sciencedirect.com/science/article/pii/S0895435614002753) to enhance the interpretation of external validation studies of clinical prediction models, 2015.
The author also summarized some useful [links](http://www.clinicalpredictionmodels.org/doku.php?id=links:start), marker research in [methodological work](http://www.clinicalpredictionmodels.org/doku.php?id=markers:start), [NRI](http://www.clinicalpredictionmodels.org/doku.php?id=presentations:start) presentation slides, [review](http://annals.org/article.aspx?articleid=1814428) of NRI - Net Reclassification Improvement.




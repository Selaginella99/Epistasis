[MachineLearning](http://cran.r-project.org/web/views/MachineLearning.html) includes `glmnet` package, `penalized` package.

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
[penalized](http://www.rdocumentation.org/packages/penalized)
[penalized_vignettes](http://cran.r-project.org/web/packages/penalized/vignettes/penalized.pdf)


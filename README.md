# Statistical Modeling and Mixed Models with R

This repo contains slides and exercise materials for my workshop on statistical modeling and mixed models with R. Previous instances of this workshop:

- The first instance of this workshop was held as part of the [Data on the Mind 2017](http://www.dataonthemind.org/2017-workshop). Title: *Statistical Models for Dependent Data: An Introduction to Mixed Models in R*
- One day workshop at the University of Freiburg in June 2018. Title: *Mixed Models in R – An Applied Introduction*
- One day tutorial at CogSci 2018 in Madison (Wisconsin). Title: *Mixed Models in R – An Applied Introduction*

The mixed model part of the workshop are loosely based on my chapter: [An introduction to linear mixed modeling in experimental psychology.](http://singmann.org/download/publications/singmann_kellen-introduction-mixed-models.pdf)
Read the chapter to get a more comprehensive overview.


The repo currently contains three `html` presentations:

- [Part 0: Introduction to Modern `R`](https://singmann.github.io/mixed_model_workshop_2day/part0-introduction/introduction.html)
- [Part 1: Statistical Modeling in R](https://singmann.github.io/mixed_model_workshop_2day/part1-statistical-modeling-in-r/statistical_modeling.html)
- [Part 2: Mixed Models in R](https://singmann.github.io/mixed_model_workshop_2day/part2-mixed-models-in-r/mixed_models.html)

In addition, the repo contains a [`pdf` handout](https://github.com/singmann/mixed_model_workshop_2day/raw/master/handout/mixed_model_handout.pdf) providing a concise overview. 

### Requirements
- A recent version of `R` (currently `R 3.5.2`): `https://cran.rstudio.com/`
- `R` packages necessary for the analysis (install with `install.packages("package")` at `R` prompt): `afex` (which automatically installs the additional requirements `emmeans`, `lme4`, and `car`) and `psych` and `MEMSS` (for example data)
- `R` package `tidyverse` as well as `broom` for the exercises (we mainly need `dplyr`, `broom`, `tidyr`, `purrr`, and `ggplot2`).
- `R` package `xaringan` to compile the slides.
- `R` package `sjstats` for Intraclass Correlation Coefficient (ICC).
- `R` package `GGally` for some plots.
- Possibly `R` packages `sjPlot` and `MuMIn` for some examples.
- A html 5 compatible browser to view the slides.
- `RStudio`: https://www.rstudio.com/products/rstudio/download3/#download

### An introduction to modern R, statistical modeling, and mixed models.

This workshop will cover several topics in an integrative fashion. The first half day will be devoted to an overview of modern tools for data science in R: Rmarkdown and the tidyverse. Based on this knowledge, the second half day will be devoted to an introduction to statistical modeling in R. The second day will introduce mixed models. Mixed models are a generalization of ordinary regression models that explicitly capture dependencies among related data points via random-effects parameters. Such dependencies are ubiquitous in psychology due to collecting more than one data point from the same participant and/or from the same item. Compared to traditional analyses approaches that ignore these dependencies, mixed models provide more accurate (and generalizable) estimates, improved statistical power, and non-inflated Type I errors. The workshop will introduce the functionality of lme4, the gold standard for estimating mixed models in R. In addition, it will introduce the functionality of afex, which simplifies many aspects of using lme4, such as the calculation of p-values for mixed models. Attendants are expected to have knowledge of R. 


### Longer Overview

In order to increase statistical power and precision, many data sets in cognitive and behavioral sciences contain more than one data point from each unit of observation (e.g., participant), often across different experimental conditions. Such *repeated-measures* pose a problem to most standard statistical procedures such as ordinary least-squares regression, (between-subjects) ANOVA, or generalized linear models (e.g., logistic regression) as these procedures assume that the data points are *independent and identically distributed*. In case of repeated measures, the independence assumption is expected to be violated. For example, observations coming from the same participant are usually correlated - they are more likely to be similar to each other than two observations coming from two different participants. 

The goal of this workshop is to introduce a class of statistical models that is able to account for most of the cases of non-independence that are typically encountered in cognitive science – *linear mixed-effects models* (Baayen, Davidson, & Bates, 2008), or mixed models for short. Mixed models are a generalization of ordinary regression that explicitly capture the dependency among data points via random-effects parameters.  Compared to traditional analyses approaches that ignore these dependencies, mixed models provide more accurate (and generalizable) estimates of the effects, improved statistical power, and non-inflated Type I errors (e.g., Barr, Levy, Scheepers, & Tily, 2013).

In recent years, mixed models have become increasingly popular. One of the main reason for this is that a number of software packages have appeared that allow to estimate large classes of mixed models in a relatively convenient manner. The workshop will focus on `lme4` (Bates, Mächler, Bolker, & Walker, 2015), the gold standard for estimating mixed models in `R` (R Core Team, 2018). In addition, it will introduce the functionality of `afex` (Singmann, Bolker, Westfall, & Aust, 2017), which simplifies many aspects of using `lme4`, such as the calculation of p-values for mixed models. `afex` was specifically developed with a focus on factorial designs that are common in cognitive and behavioral sciences.

Despite a number of high impact publications that introduce mixed models to a wide variety of audiences (e.g., Baayen et al., 2008; Judd, Westfall, & Kenny, 2012) the application of mixed models in practice is far from trivial. Applying mixed models requires a number of steps and decisions that are not necessarily part of the methodological arsenal of every researcher. The goal of the workshop is to change this and to introduce mixed models in such a way that they can be effectively used and the results communicated.

The workshop is split into three parts. The first half day will be devoted to an overview of modern tools for data science in `R`: `Rmarkdown` and the `tidyverse`. Based on this knowledge, the second half day will be devoted to an introduction to statistical modeling in `R`. The second day will introduce mixed models using the `lme4` package, the gold standard for estimating mixed models in R. In addition, it will introduce the functionality of `afex` (the package of the convenor), which simplifies many aspects of using lme4, such as the calculation of p-values for mixed models.

Participants of the workshop need some basic knowledge of R. For example, they should be able to read in data, select subsets of the data, and estimate a linear regression model. Participants without any R knowledge will likely nor profit from the workshop. 

### References

- Baayen, H., Davidson, D. J., & Bates, D. (2008). Mixed-effects modeling with crossed random effects for subjects and items. *Journal of Memory and Language*, 59(4), 390–412. https://doi.org/10.1016/j.jml.2007.12.005
- Bates, D., Mächler, M., Bolker, B., & Walker, S. (2015). Fitting Linear Mixed-Effects Models Using lme4. *Journal of Statistical Software*, 67(1). https://doi.org/10.18637/jss.v067.i01
- Barr, D. J., Levy, R., Scheepers, C., & Tily, H. J. (2013). Random effects structure for confirmatory hypothesis testing: Keep it maximal. *Journal of Memory and Language*, 68(3), 255–278. https://doi.org/10.1016/j.jml.2012.11.001 
- Judd, C. M., Westfall, J., & Kenny, D. A. (2012). Treating stimuli as a random factor in social psychology: A new and comprehensive solution to a pervasive but largely ignored problem. *Journal of Personality and Social Psychology*, 103(1), 54–69. https://doi.org/10.1037/a0028347
- Singmann, H., Bolker, B., Westfall, J., & Aust, F. (2017). *afex: Analysis of Factorial Experiments.* R package version 0.18-0. http://cran.r-project.org/package=afex 
- R Core Team. (2017). *R: A Language and Environment for Statistical Computing*. Vienna, Austria: R Foundation for Statistical Computing. http://www.R-project.org/
- Wickham, H., & Grolemund, G. (2017). *R for Data Science: Import, Tidy, Transform, Visualize, and Model Data.* Sebastopol  CA: O’Reilly.

---

Last edited: May 2019

---

All code in this repository is released under the [GPL v2 or later license](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html). All non-code materials is released under the [CC-BY-SA license](https://creativecommons.org/licenses/by-sa/4.0/).

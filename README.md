### About

This repository contains an R script for performing power analyses in the setting of our Regression Discontinuity Design study on alteplase effectiveness.

---

### Power Calculation

The question for this power calculation is: given an approximately known effect size, how many subjects would we need in an RDD study to detect this difference? The calculation uses the following quantities:

* Effect size: The ECASS 3 trial found that for patients presenting between 3 and 4.5 hours, 52.4% had a good outcome (mRS of 0 or 1) vs 45.2% did not have a good outcome. The effect size typically used is Cohen's *h*, which is a transformation of these proportions.

* Compliance: Not all patients presenting before the treatment threshold received alteplase, and some received alteplase after the threshold. Compliance is the difference between these two proportions. Perfect compliance would increase the observed effect size of alteplase and would increase the power of the study.

* Design effect: RDD studies are not RCTs, and lose some power because of that. One important reason for this is because there's a correlation between time with symptoms, and alteplase treatment; patients arriving before the threshold (ideally) receive alteplase, and those arriving after the threshold do not receive alteplase. Thus, there is a correlation between *time until presentation* and alteplase administration status. In an RCT, there would be no such correlation because patients receiving alteplase would have the same distribution of *time until presentation*. Most estimates of this effect are 3-4 (i.e., that 3-4x more subjects are required for RDD vs RCT).


---

### References and Requirements

This script requires the *pwr* package, which can be found [here](https://cran.r-project.org/web/packages/pwr/pwr.pdf). This package implements power calculations from Cohen's book:

* Cohen, J. (1988). Statistical power analysis for the behavioral sciences (2nd ed.). Hillsdale, NJ:
Lawrence Erlbaum

This power calculation uses results from the ECASS 3 trial, as well as some guidance in the form of a blog post about RDD power calculations:

1. Hacke, Werner, et al. "Thrombolysis with alteplase 3 to 4.5 hours after acute ischemic stroke." New England Journal of Medicine 359.13 (2008): 1317-1329.

2. McKenzie, D. (2016, September 6). Power Calculations for Regression Discontinuity Evaluations: Part 1. Retrieved from: https://blogs.worldbank.org/impactevaluations/power-calculations-regression-discontinuity-evaluations-part-1

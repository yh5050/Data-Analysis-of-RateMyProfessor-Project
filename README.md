# Data Analysis of RateMyProfessor Project

IDS Capstone group project analysis by Team Mochi.

This project analyzes RateMyProfessor data to study how professor ratings relate to gender, perceived difficulty, descriptive tags, attractiveness indicators, and geography. The analysis combines hypothesis testing, weighted regression, tag-based modeling, classification, and exploratory visualization.

## Files

- `Team Mochi.ipynb` - original notebook version of the analysis.
- `Team Mochi.py` - Python script exported from the notebook.
- `Team Mochi.pdf` - project report or presentation export. This PDF was repaired and rewritten so it can render correctly in PDF viewers such as GitHub's embedded preview.

## Data

The Python script expects these local CSV files when rerunning the analysis:

- `rmpCapstoneNum.csv`
- `rmpCapstoneTags.csv`
- `rmpCapstoneQual.csv`

These data files are not included in this repository.

## Report Summary

The report starts from a raw RateMyProfessor dataset of 89,892 entries and refines it to approximately 70,004 observations. The preprocessing removes ambiguous gender labels, excludes professors with zero ratings, imputes missing numerical values with medians, normalizes tag counts by number of ratings, and uses number of ratings as an analytical weight. This weighting gives more influence to professors with more stable review histories while avoiding a hard minimum-review threshold.

The first section tests whether there is evidence of a pro-male bias in average professor ratings. A weighted least squares model with robust standard errors finds no evidence of a pro-male rating boost. The estimated male coefficient is slightly negative and statistically insignificant under the project's strict alpha level.

The next section studies whether ratings differ in spread by professor gender. Levene's test finds a statistically significant difference in variance: ratings for male professors are slightly more dispersed than ratings for female professors. The practical effect is small, but it suggests male professors receive somewhat more polarized ratings.

The report then estimates effect sizes for both average ratings and rating spread. The average-rating difference is small, with female professors estimated to receive slightly higher ratings, while male professors show a slightly larger standard deviation in ratings. Both effects are real statistically, but modest on a five-point scale.

For descriptive tags, the project compares normalized tag frequencies across gender. Most tags show statistically significant gender differences. The report finds that students use different language patterns when evaluating male and female professors, even when numeric difficulty ratings do not differ meaningfully.

The difficulty analysis finds no statistically significant gender difference in average difficulty. The estimated difference is extremely small, and Cohen's d is negligible. This suggests that students may use gendered descriptive language without systematically rating one gender as more difficult.

The predictive modeling section builds weighted regression models for average rating and difficulty. Numerical metadata explains about 53.5% of the variance in average rating, with perceived difficulty acting as the strongest negative predictor. Tag-based models show that tags such as "Amazing lectures" and "Inspirational" are associated with higher ratings, while "Tough grader" strongly predicts lower ratings and higher perceived difficulty.

The classification section models the RateMyProfessor "Pepper" indicator for perceived attractiveness. A logistic regression model achieves moderate predictive power, with an AUROC of about 0.678. The findings suggest that perceived attractiveness is linked with other positive teaching-quality signals, supporting a halo-effect interpretation.

The extra-credit geographic analysis compares professor ratings across West Coast, East Coast, and Inland regions. The regional differences are statistically significant but practically tiny, explaining only about 0.1% of rating variance. The report concludes that individual professor traits matter much more than geographic region.

## Main Takeaways

- There is no evidence of a pro-male boost in average ratings under the weighted model.
- Male professors show slightly more polarized ratings, but the effect is small.
- Gendered differences appear more strongly in descriptive tags than in difficulty ratings.
- Perceived difficulty is the strongest negative predictor of average rating.
- Tags are useful predictors of both rating and difficulty.
- The "Pepper" indicator has moderate predictability and appears connected to broader positive perceptions.
- Geographic region has statistically detectable but practically negligible impact.

## Authors

- Yishu Yang
- Yihe Huang
- Sahil Parupudi

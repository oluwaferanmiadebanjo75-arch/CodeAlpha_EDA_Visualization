# CodeAlpha_EDA_Visualization

**CodeAlpha Data Analytics Internship, Task 2 (Exploratory Data Analysis) and Task 3 (Data Visualization)**

Dataset: Breast Cancer Wisconsin (Diagnostic), 569 tumours and 30 numeric features (bundled with scikit-learn).

## Questions asked before analysis
1. Is the data balanced between malignant and benign cases?
2. Is the data clean (missing values, duplicates)?
3. Which features separate malignant from benign tumours most?
4. Are those differences statistically significant?
5. Which features are redundant (highly correlated)?
6. Are there outliers?

## Key findings
- **Clean data:** 0 missing values, 0 duplicates. 63% benign / 37% malignant (moderate imbalance).
- **Strongest separators:** worst concave points (Cohen's d = 2.60), worst perimeter (2.37), mean concave points (2.33), worst radius (2.32).
- **Hypothesis tests (Welch t-test):** 26 of 30 features differ significantly between classes at the 5% level.
- **Multicollinearity:** 21 feature pairs have |r| > 0.9 (e.g. radius, perimeter and area at about 0.99). Use feature selection or PCA before modelling.
- **Outliers (IQR rule):** area error (65), radius error (38) and perimeter error (38) are the most affected, and are right-skewed.

## Visuals (`/visuals`)
Class balance, top-feature distributions, boxplots, effect sizes, correlation heatmap, pairplot, outlier counts.

## Run
pip install pandas numpy matplotlib seaborn scipy scikit-learn
python eda_visualization.py

## Next steps
Log-transform skewed features, drop redundant features, then build a classifier.

# What Makes Nations Happy?
### Economics, inequality, and a Simpson's paradox in global well-being

A machine learning project predicting national life satisfaction for 140+ countries from 2005 to 2024, built in Python with scikit-learn.

**Author:** Rita Campos, Economics & Psychology

## Key findings

- **Six factors explain ~70% of happiness differences between countries.** A linear regression reached R² = 0.68 on countries it never saw during training (average error: 0.45 points on a 0–10 scale).
- **GDP and social support matter most.** Once all factors are put on the same scale, GDP per capita (0.49) and social support (0.32) are the strongest predictors, followed by freedom, health, and generosity.
- **Simpler won.** A random forest (R² = 0.66) did not beat linear regression, suggesting the relationships are mostly linear.
- **Latin America is happier than its economics predict (+0.40); Southeast Asia is less happy (−0.39).** This matches the "Latin American happiness paradox" described in prior research.
- **A Simpson's paradox in inequality.** Across all countries, income inequality appears linked to slightly *higher* happiness. Within the same region, the relationship reverses: more inequality goes with *lower* happiness. Latin America, both highly unequal and unusually happy, masked the real pattern.

## Methods

- **Country-grouped validation:** models are always tested on countries they never trained on, so they can't "memorize" a country from other years.
- **Standardized coefficients** to compare factors measured in different units.
- **Residual analysis** to find which countries and regions are happier or less happy than predicted.
- **Region controls** to test whether inequality's effect changes within regions.

## Data

- [World Happiness Report panel data, 2005–present](https://www.kaggle.com/datasets/usamabuttar/world-happiness-report-2005-present) (Kaggle)
- World Bank Gini index (SI.POV.GINI), pulled automatically via the World Bank API

## How to run

1. Open `world_happiness_model.ipynb` and click **Open in Colab**.
2. Download the Kaggle dataset above and upload the CSV to Colab's Files panel.
3. Go to **Runtime → Run all**.

## Tools

Python · pandas · scikit-learn · matplotlib · seaborn · Google Colab

## Limitations

Results show correlation, not causation. Inequality is averaged over 2000–2024 and missing for some countries, and happiness is self-reported, so cultural differences in how people answer surveys may affect the results.

# Household Income, Gender, and School Enrollment Inequality: Evidence from Nigeria MICS6 (2021)

## Research Question

Does household income predict school enrollment more strongly than gender does among Nigerian children?

## Dataset

Source: Nigeria MICS6 (2021), UNICEF/NBS.

Relevant files used:

*   `hh.sav` (Households → for wealth/income proxy)
*   `hl.sav` (Household members → for school attendance, gender, age)
*   `fs.sav` (Children age 5–17 → main education outcomes like enrollment, attendance, grade level)

## Variables of Interest

*   **Dependent variable (Y):** `enrolled` (1 = enrolled in school, 0 = not enrolled) → derived from `FS4` in `fs.sav`.
*   **Independent variables (X):**
    *   `wealth_index` (proxy for household income, `wscoreMICS_x`) → from `hh.sav`.
    *   `gender` (male/female, `HL4_x`) → from `hl.sav`.
    *   `urban_rural` (location type, `HH6_x`) → from `hh.sav`.

## Methodology

1.  **Data Preparation**: Loaded SPSS files (`hh.sav`, `hl.sav`, `fs.sav`) using `pandas`. Merged household, member, and child datasets using common IDs (`HH1`, `HH2`, `HL1`/'LN'). Cleaned missing values in key variables.
2.  **Descriptive Statistics**: Calculated overall enrollment rates and enrollment rates by gender and income quintile. Visualized these using bar charts.
3.  **Inferential Analysis**: Ran a logistic regression model to predict the probability of school enrollment based on wealth index, gender, and urban/rural location:
    `𝑃(enrolled = 1) = 𝛽0 + 𝛽1(income) + 𝛽2(gender) + 𝛽3(urban_rural)`.
    Calculated and interpreted odds ratios.
4.  **Visualization**: Generated bar plots for descriptive statistics and a line plot for predicted probabilities from the logistic regression.

## Results

*   **Descriptive Statistics**: Overall enrollment rates and enrollment rates by gender and income quintile were visualized, showing a positive relationship between wealth index and enrollment.
*   **Inferential Analysis (Logistic Regression)**:
    *   Higher wealth index is associated with increased odds of school enrollment (statistically significant).
    *   Gender difference in enrollment odds is not statistically significant after controlling for wealth and location.
    *   Being in an urban area is associated with significantly higher odds of school enrollment compared to rural areas, when controlling for wealth and gender.

## Conclusions

Household income (wealth index) is a stronger predictor of school enrollment among Nigerian children than gender. Urban/rural location also significantly impacts enrollment. Socioeconomic factors and geographic location are important determinants of educational access in Nigeria.

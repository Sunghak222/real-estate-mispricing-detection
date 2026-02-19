# Real Estate Mispricing Detection Framework

## 1. Problem Statement

While predictive models estimate housing prices with reasonable accuracy, 
can we go one step further and use model errors to detect potential mispricing opportunities?

This project extends a traditional regression modeling approach into a 
mispricing detection framework using out-of-fold (OOF) residual analysis.

The goal is not only prediction, but structured screening for pricing bias 
and tail-based investment opportunities.

---

## 2. Methodology

### 2.1 Predictive Modeling

- Target transformed using `log1p`
- Gradient Boosting Regressor (GBR)
- 5-fold cross-validation
- Out-of-fold (OOF) predictions generated

### 2.2 Relative Error Definition

We define relative pricing error as:

rel_error = (actual_price - predicted_price) / predicted_price

Interpretation:

- rel_error < 0 → Underpriced
- rel_error > 0 → Overpriced

Using OOF predictions prevents in-sample bias and ensures fair residual estimation.

---

## 3. Analytical Framework

The analysis proceeds in three layers:

### (1) Market-Level Efficiency

Histogram of rel_error shows that most properties cluster around zero, 
suggesting overall market efficiency with limited systematic bias.

### (2) Structural Segment Bias

Mean relative error is aggregated by:

- Neighborhood
- Overall Quality

This reveals potential structural pricing differences across segments.

### (3) Tail-Based Screening

Extreme negative tail observations are isolated to identify 
potential underpriced investment candidates.

---

## 4. Dashboard

An interactive Tableau dashboard was built to:

- Visualize pricing error distribution
- Detect structural bias by neighborhood
- Dynamically filter properties by segment
- Screen extreme mispricing candidates
- 
<img width="923" height="706" alt="Tableau Screenshot" src="https://github.com/user-attachments/assets/dce4192c-b22a-4726-b81a-94765c9fe253" />

Tableau Public Link:
[Link](https://public.tableau.com/app/profile/sunghak.heo/viz/PropertyMispricingDetection/PropertyMispricingDetection)

---

## 5. Key Insights

- Housing prices are largely efficient at the aggregate level.
- Certain premium neighborhoods exhibit consistent pricing deviations.
- Extreme negative residuals form a small but actionable screening set.

---

## 6. Tech Stack

- Python
- Pandas / NumPy
- Scikit-learn (GBR, KFold OOF)
- Tableau (Interactive Dashboard)

---

## 7. Project Positioning

This project demonstrates:

- Out-of-fold validation understanding
- Residual-based analytical thinking
- Segment-level bias detection
- Decision-support dashboard development

It reframes predictive modeling into an applied mispricing analysis framework.

# House Price Prediction — Kaggle Competition

## 📌 Project Overview
This project predicts residential home sale prices using machine learning, built as part of the **Intermediate Machine Learning** course on Kaggle Learn. The goal was to train a regression model that estimates a house's `SalePrice` based on a set of property features, then submit predictions to the **[Housing Prices Competition for Kaggle Learn Users](https://www.kaggle.com/c/home-data-for-ml-course)**.

The model used is a **Random Forest Regressor** — an ensemble of decision trees whose predictions are averaged together to produce more accurate and stable results than a single decision tree.

### Features used
- `LotArea` — Lot size (sq ft)
- `YearBuilt` — Original construction year
- `1stFlrSF` — First floor square footage
- `2ndFlrSF` — Second floor square footage
- `FullBath` — Number of full bathrooms
- `BedroomAbvGr` — Bedrooms above ground
- `TotRmsAbvGrd` — Total rooms above ground

---

## 🧠 What I Learned

- **Feature selection** — Choosing a focused, meaningful set of numeric predictors that relate directly to a home's value, rather than using every available column.
- **Train/validation splitting** — Holding out a portion of labeled data (`train_test_split`) to fairly evaluate model performance on data the model hasn't seen, simulating how it will perform on the real test set.
- **Model comparison via Mean Absolute Error (MAE)** — Training multiple Random Forest configurations and comparing their validation MAE (average dollar difference between predicted and actual prices) to objectively identify the best-performing model, rather than guessing.
- **Hyperparameter tuning** — Testing how different settings affect performance, including:
  - Number of trees (`n_estimators`)
  - Splitting criterion (`criterion='absolute_error'` vs. default)
  - Tree depth restriction (`max_depth`)
  - Minimum samples required to split a node (`min_samples_split`)
- **Generalization** — Understanding why the model with the *lowest* validation error is preferred, since it indicates the smallest average prediction mistake on unseen houses.

---

## 📊 Result

| Metric | Score |
|---|---|
| Validation MAE (best model) | **23,528** |
| Model used | Random Forest (`n_estimators=100`, `criterion='absolute_error'`) |

This means the model's predicted sale prices were, on average, about **$23,528** away from the true sale price on validation data.

---

## 🔗 Competition Link
[Housing Prices Competition for Kaggle Learn Users](https://www.kaggle.com/c/home-data-for-ml-course)

---

## 🛠️ Tools & Libraries
- Python
- pandas
- scikit-learn (`RandomForestRegressor`, `train_test_split`, `mean_absolute_error`)

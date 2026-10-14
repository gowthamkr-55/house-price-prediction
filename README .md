# 🏠 House Price Prediction (Boston Housing)

A beginner-friendly machine learning project that predicts the **price of a house** from features such as the number
of rooms, crime rate, pollution and distance to jobs. Built step by step in a Jupyter Notebook using Python and scikit-learn.

---

## 📌 Project Overview

This is a **regression** problem, because the output (house price) is a number.
The notebook uses **Linear Regression** and explains every step in simple language.

**Workflow:**

```
Load data → EDA → Train-test split → Handle missing values → Scaling → Train Linear Regression → Evaluate → Predict
```

## 📂 Dataset

- **Name:** Boston Housing dataset
- **Size:** 506 houses, 13 features + 1 target
- **Target:** `MEDV` (median house price in $1000s)
- **Missing values:** 20 each in `CRIM`, `ZN`, `INDUS`, `CHAS`, `AGE`, `LSTAT`

| Group | Columns |
|---|---|
| Size | `RM` (average rooms) |
| Location | `CRIM`, `ZN`, `INDUS`, `CHAS`, `NOX`, `DIS`, `RAD`, `TAX`, `PTRATIO`, `LSTAT` |
| Target | `MEDV` |

> The column `B` is based on the racial makeup of each town. It is **not used** in this project because it is unfair
> to predict prices with it (this is also why the dataset was removed from scikit-learn). To include it, remove `"B"`
> from the `drop` list in the notebook.

## 🛠️ Technologies Used

- Python 3
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- Jupyter Notebook

## 🔍 Steps in the Notebook

1. **Load and explore data:** price distribution, feature histograms, boxplots, correlation heatmap, scatter plots
2. **Train/Test split:** 80% train, 20% test (done *before* preprocessing to avoid data leakage)
3. **Handle missing data:** fill with the **median** of the training data
4. **Normalization:** `StandardScaler` (fitted on train data only)
5. **Train model:** Linear Regression
6. **Evaluate:** MSE, RMSE, MAE, R², baseline comparison, train vs test check
7. **Analyse:** actual vs predicted plot, residual plot, feature coefficients
8. **Predict** the price of new houses

## 📊 Results (20% test set)

| Metric | Value |
|---|---|
| MSE | 23.66 |
| RMSE | 4.86 (about $4,900) |
| MAE | 3.08 |
| R² Score | 0.68 |
| Baseline MSE (always predict the average) | 75.05 |

**Key findings**
- The model cuts the error (MSE) from 75 to about 24 compared with a simple average guess
- Train R² (0.73) and test R² (0.68) are close, so there is no overfitting
- More rooms (`RM`) increase the price, a higher lower-income % (`LSTAT`) decreases it
- Prices are capped at 50 in the data, so the model is weaker for very expensive houses

## 📁 Project Structure

```
house-price-prediction/
│
├── House_Price_Prediction.ipynb   # Complete step-by-step notebook
├── HousingData.csv                # Dataset
├── requirements.txt               # Python libraries
└── README.md
```

## ⚙️ How to Run

**1. Clone the repository or download the files**
```bash
git clone <your-repository-url>
cd house-price-prediction
```

**2. (Optional) Create a virtual environment**
```bash
python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # Mac / Linux
```

**3. Install the libraries**
```bash
pip install -r requirements.txt
```

**4. Open the notebook**
```bash
jupyter notebook House_Price_Prediction.ipynb
```

Then click **Run → Run All Cells**. Keep `HousingData.csv` in the same folder as the notebook.

## 🚀 Future Improvements

- Try Ridge, Lasso, Random Forest and Gradient Boosting and compare the MSE
- Use cross-validation for a more reliable score
- Add polynomial features or use `log(price)` to catch curved patterns
- Handle outliers and test the effect
- Build a Streamlit app where users enter house details and get a price

## 👤 Author

**Gowtham K R**
BCA (Computer Science) student
GitHub: [gowthamkr-55](https://github.com/gowthamkr-55)

## 📄 License

This project is for learning and educational purposes.

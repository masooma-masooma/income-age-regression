# Income vs Age: Linear & Polynomial Regression

Predicting **average income by age** using Swedish regional income data (2020), comparing **linear regression** with **polynomial regression** of different degrees.

## 🎯 What this project does
1. **Custom CSV loader:** reads the data with basic Python file I/O (no pandas or csv library)
2. **Linear regression from scratch:** uses the **Normal Equation** with NumPy
3. **Custom MSE function:** evaluates predictions without sklearn's metrics
4. **Data cleaning:** converts text ages like `"25 years"` to numbers and averages income across all regions with `groupby`
5. **Polynomial regression:** tests degrees 2, 3, 5 and 8 and picks the best with validation MSE

## 📊 Results

| Model | Data | Validation MSE |
|-------|------|---------------:|
| Linear regression | Subset (ages 20–50) | 334.0 |
| Linear regression | Full dataset (all ages) | 11,924.7 |
| Polynomial, degree 2 | Full dataset | 2,514.9 |
| Polynomial, degree 3 | Full dataset | 272.2 |
| Polynomial, degree 5 | Full dataset | 213.9 |
| Polynomial, degree 8 | Full dataset | 203.5 |

**Key finding:** between ages 20 and 50, income grows almost in a straight line, so linear regression works well. Across all ages, income rises, peaks in middle age and then falls after retirement. A straight line cannot follow that curve, so the MSE becomes very high. Polynomial regression captures the curve and lowers the MSE from about 11,900 to about 200.

## 🛠️ Tech Stack
Python · NumPy · pandas · scikit-learn · Matplotlib · Seaborn · Jupyter

## 🚀 How to Run
```bash
pip install -r requirements.txt
jupyter notebook income_regression.ipynb
```
## 📂 Data
The datasets were provided through the course and are **not included** in this repository. All outputs and graphs are saved in the notebook, so the results can be viewed without running it.

To run the notebook yourself, place these files in the same folder:
- `inc_subset.csv`: average income by age (ages 20–50)
- `inc_utf.csv`: average income by age and region

## 📁 Files
```
├── income_regression.ipynb   # Main notebook
├── requirements.txt
└── README.md
```

## 👤 Author
Masooma, MSc Applied AI, Year 1

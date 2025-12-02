# Wine Price Modeling with Linear Regression  
Predicting Bordeaux Wine Auction Prices Using Climate Data, Aging, and Winery Effects

## 📌 Project Overview
This repo builds a series of linear regression models to predict Bordeaux wine auction prices.  
Using both aggregated and disaggregated datasets, the analysis explores:

- How climate variables (rainfall, temperature) impact pricing  
- How wine age contributes to market value  
- How multicollinearity affects model stability  
- Whether winery-specific effects significantly improve predictive accuracy  

The workflow demonstrates statistical modeling, diagnostics, model refinement, and predictive evaluation using Out-of-Sample R².

---

## 📂 Datasets
### **wine_agg.csv**
Contains annual, aggregated information:
- LogAuctionIndex (log-transformed wine price index)  
- Seasonal rainfall and temperatures  
- Wine age  
- Population and alcohol consumption variables  

### **wine_disagg.csv**
A more detailed dataset including:
- Individual wine observations  
- A categorical `Winery` variable  
- Climate and aging variables  
- LogAuction (log price)

---

## 🔍 Key Steps & Findings

### **1. Exploratory Data Analysis**
- Assessed distribution of LogAuctionIndex  
- Visualized correlations to identify strong relationships  
- Found early signs of multicollinearity among time-related variables (Age, FrancePop, USAlcConsump)

### **2. Baseline Linear Regression**
The initial full model showed high multicollinearity:
- FrancePop and Age nearly perfectly correlated  
- Very high VIF values (> 60)  
- OSR² ≈ **0.54**, meaning the model did not generalize well

### **3. Model Refinement**
A stepwise approach removed problematic variables:
- Removed FrancePop → VIF dropped  
- Removed USAlcConsump → VIF significantly improved  
- Removed HarvestTemp (statistically insignificant)

**Final continuous model predictors:**
- WinterRain  
- HarvestRain  
- GrowTemp  
- Age  

**Final continuous model performance:**
- R² = **0.785**
- Adjusted R² = **0.752**
- OSR² = **0.747**

This model generalized well and avoided overfitting.

### **4. Adding Winery as a Categorical Variable**
Using the disaggregated dataset, we extended the model to include:

The categorical encoding revealed strong winery-specific effects:

- **Cheval Blanc:** ~5x price premium  
- **Lafite Rothschild:** ~6.6x price premium  

### Winery Model Performance
- **R² = 0.851**  
- **Adjusted R² = 0.834**  
- **OSR² = 0.807** (excellent generalization)

### 5. Visualizations
- Predicted vs Actual plots show tight clustering around the 45° line for the winery model  
- Coefficient bar chart illustrates winery reputation effects  

---

## 📊 Key Skills Demonstrated

- Linear regression modeling  
- R² vs Adjusted R² vs OSR²  
- Multicollinearity diagnostics (VIF, condition number)  
- Feature selection & model refinement  
- Interpreting categorical variables  
- Train/test splitting  
- Hypothesis testing (t-tests, F-tests)  
- Visualization & communication of model performance  

---

## 🛠️ Tools & Libraries

- Python  
- pandas  
- numpy  
- statsmodels  
- matplotlib / seaborn  
- Jupyter Notebook  

---

## 🧠 Conclusion

This project demonstrates a complete end-to-end regression analysis.  
By diagnosing and reducing multicollinearity and incorporating categorical 
winery effects, the final model achieves strong interpretability and excellent 
predictive performance on unseen data.

The analysis showcases statistical thinking, model evaluation techniques, and 
clear communication—essential skills for data science and analytics roles.

---

## 📬 Contact

If you’d like to discuss the project or have feedback, feel free to connect!


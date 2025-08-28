# Ridge Regression (Sklearn vs Scratch)

This project is about understanding and implementing **Ridge Regression** (a regularized version of Linear Regression) using both **Scikit-Learn** and a **scratch-coded implementation**.  

The main goal was to compare results between the two approaches and build intuition for how Ridge Regression works.

---

## 📌 Project Steps

1. **Dataset**  
   - Used the **Diabetes dataset** from `sklearn.datasets`.
   - Split into **train (80%)** and **test (20%)** sets.  
   - Random state fixed at `4`.

2. **Using Sklearn Ridge**  
   - Imported Ridge from `sklearn.linear_model`.  
   - Parameters used:  
     - `alpha = 0.1` (penalty term)  
     - `solver = "cholesky"` (to match our scratch implementation).  
   - Fit the model and got results:  
     - **R² Score:** `0.4693`  
     - **Intercept:** `150.89`  

3. **Scratch Implementation (Class: `MyRidge`)**
   - Custom Ridge Regression implementation using **Cholesky decomposition**.
   - Key features:
     - `__init__(alpha=0.1)`: constructor with user-defined penalty.  
     - `fit(X_train, y_train)`:  
       - Added column of `1s` in X for intercept (`β₀`).  
       - Created identity matrix `I` for regularization.  
       - Applied formula:  
         \[
         \beta = \left(X^T X + \alpha I\right)^{-1} X^T y
         \]
     - Extracted intercept (`β₀`) from index 0, coefficients from remaining values.  
     - `predict(X_test)`: returned predictions.  

4. **Results (Scratch Implementation)**  
   - Created object `mr = MyRidge(alpha=0.1)`.  
   - Fitted and predicted.  
   - **R² Score:** ~`0.46` (same as sklearn result).  

---

## 📊 Outcomes

- Both **Sklearn** and **Scratch implementation** gave **similar R² scores**.  
- Intercept and coefficients matched closely.  
- Learned how Ridge modifies the Linear Regression formula by adding **`αI` (regularization)** to reduce overfitting.  

---

## 🚀 Next Steps

- Extend this project to implement **Ridge Regression using Gradient Descent**.  
- Compare results with **OLS (Normal Equation)**, **Batch Gradient Descent**, and **Stochastic Gradient Descent**.

---

## 🛠️ Tech Stack

- Python  
- Numpy  
- Scikit-Learn  

---

## 📂 File Structure


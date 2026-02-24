**Data Generation using Modelling & Simulation**

**Project Overview**

This project demonstrates synthetic data generation using mathematical modelling and evaluates the performance of multiple machine learning regression models on the generated dataset.

Instead of using real-world datasets, we:

- Designed a nonlinear mathematical simulator
- Generated 1000 synthetic samples
- Trained multiple regression models
- Compared their performance using MSE and R²
- Visualized results using graphs

The goal is to understand how different models behave when learning from nonlinear simulated systems.

---

**Problem Statement**

Can machine learning models accurately learn and predict outputs generated from a nonlinear mathematical simulator with added noise?

We simulate data using a nonlinear equation that includes:
- A sine component
- A quadratic term
- Random Gaussian noise

The objective is to predict the output variable `y` using the input parameters.

---

**Methodology**

**1.Mathematical Model (Simulator)**

The output variable **y** is generated using the following equation:

y = a·sin(bx) + c·x² + d + ε

Where:

- `a` → amplitude coefficient (0.5 to 5)
- `b` → frequency coefficient (0.1 to 2)
- `c` → quadratic coefficient (-2 to 2)
- `d` → bias term (-5 to 5)
- `x` → input variable (0 to 10)
- `ε` → Gaussian noise (mean = 0, standard deviation = 1)

This ensures:
- Nonlinearity (sine + quadratic)
- Controlled randomness
- Realistic noisy behaviour


**2.Data Generation**

- Total samples generated: 1000
- Random seed fixed for reproducibility
- Features: `a, b, c, d, x`
- Target variable: `y`

**Dataset Structure**

| Feature | Description |
|----------|-------------|
| a | Sine amplitude |
| b | Sine frequency |
| c | Quadratic coefficient |
| d | Bias term |
| x | Input variable |
| y | Simulated output |


**3.Train-Test Split**

- 80% Training data
- 20% Testing data
- Random state = 42

This ensures fair and reproducible evaluation.


**4.Models Used**

The following regression models were implemented:

- Linear Regression
- Ridge Regression
- Lasso Regression
- Decision Tree Regressor
- Random Forest Regressor
- K-Nearest Neighbors (KNN)
- Support Vector Regressor (SVR)
- Gradient Boosting Regressor


**5.Evaluation Metrics**

Two performance metrics were used:

(i) Mean Squared Error (MSE)
Measures the average squared difference between predicted and actual values.  
Lower values indicate better performance.

(ii) R² Score
Represents how well the model explains variance in the data.  
Closer to 1 indicates better performance.

---

**Results**

**Performance Comparison Table**

| Model | MSE | R² Score |
|--------|--------|--------|
| Gradient Boosting | 24.73 | 0.9907 |
| Random Forest | 25.34 | 0.9905 |
| Decision Tree | 74.55 | 0.9720 |
| KNN | 276.92 | 0.8958 |
| Lasso | 1265.79 | 0.5238 |
| Ridge | 1275.68 | 0.5201 |
| Linear Regression | 1275.77 | 0.5201 |
| SVR | 1804.27 | 0.3213 |

---
**Result Graph Explanation**

A bar graph was plotted to compare R² scores across models.

**Observations:**

- Ensemble methods (Gradient Boosting & Random Forest) achieved the highest R² (~0.99).
- Decision Tree performed well but slightly lower than ensemble methods.
- Linear models clustered around R² ≈ 0.52.
- SVR performed the worst in this setup.
- Clear separation between linear and nonlinear learners.

This confirms that nonlinear models are better suited for nonlinear simulated systems.

---

**Key Insights**

1. Synthetic simulation allows controlled experimentation.
2. Nonlinear systems require nonlinear models.
3. Ensemble models provide high accuracy and robustness.
4. Noise has minimal effect on ensemble methods.
5. Linear models tend to underfit nonlinear relationships.

---

**Technologies Used**

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
---

**Conclusion**

This project demonstrates how modelling and simulation can be used to:

- Generate synthetic datasets
- Benchmark machine learning models
- Analyze model behavior on nonlinear systems

Tree-based ensemble models achieved the best performance due to their ability to capture complex nonlinear relationships.

is project useful, feel free to fork or star the repository!

<h1 align="center">🏡 House Price Regression Analysis – Final Project</h1>

<p align="center"><i>Built as part of IBM's <b>Data Analysis with Python</b> course under the Skills Network program</i></p>

<p align="center">
  <a href="LICENSE">
    <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="MIT License">
  </a>
  <a href="https://www.python.org/">
    <img src="https://img.shields.io/badge/Python-3.8+-blue?logo=python" alt="Python 3.8+">
  </a>
  <a href="https://scikit-learn.org/stable/">
    <img src="https://img.shields.io/badge/scikit--learn-Used-blue?logo=scikit-learn" alt="scikit-learn Used">
  </a>
  <a href="https://github.com/hamaylzahid/house-price-regression-analysis">
    <img src="https://img.shields.io/github/repo-size/hamaylzahid/house-price-regression-analysis?color=lightgrey" alt="Repo Size">
  </a>
  <a href="https://github.com/hamaylzahid/house-price-regression-analysis/commits">
    <img src="https://img.shields.io/github/last-commit/hamaylzahid/house-price-regression-analysis?color=blue" alt="Last Commit">
  </a>
  <a href="https://github.com/hamaylzahid/house-price-regression-analysis/stargazers">
    <img src="https://img.shields.io/github/stars/hamaylzahid/house-price-regression-analysis?style=social" alt="GitHub Stars">
  </a>
  <img src="https://img.shields.io/badge/Project%20Status-Completed-brightgreen" alt="Project Status">
</p>
<p > This project is a hands-on application of regression techniques to predict housing prices using real data from  <b>King County, Washington (USA)</b>. It serves as the <b>final project</b> for IBM’s Data Analysis with Python course.

The dataset includes features like square footage, location, number of bedrooms/bathrooms, and more. The goal is simple:  </p>

> 💡 *Can we build accurate models to predict a house's price based on its attributes?*

### 🔍 What’s Inside

- 📊 Exploratory Data Analysis (EDA)
- 🧹 Data Cleaning & Feature Selection
- 📈 Linear and Ridge Regression Models
- 🔁 Polynomial Transformation (2nd order)
- 📉 Model Evaluation using R² Score

This project follows practical data science workflows and showcases clean, interpretable, and well-documented results — ideal for portfolios and real-world problem-solving.


> ⚠️ **Note:** This project is part of the IBM Skills Network curriculum. All rights and acknowledgments belong to **IBM®**.

---

<h2 align="center">📌 Features</h2>

<ul>
  <li>✅ Real-world dataset from <strong>King County House Sales</strong></li>
  <li>✅ Data preprocessing with <code>pandas</code> & <code>scikit-learn</code></li>
  <li>✅ Exploratory Data Analysis (EDA) with insightful visuals</li>
  <li>✅ Linear & Ridge Regression modeling</li>
  <li>✅ Polynomial feature transformation for non-linear relationships</li>
  <li>✅ Model evaluation using <strong>R² Score</strong></li>
</ul>

---

<h2 align="center">📖 Table of Contents</h2>

- [🧠 Project Overview](#-project-overview)
- [🎯 Objectives](#-objectives)
- [📊 Dataset Info](#-dataset-info)
- [🛠️ Workflow Breakdown](#️-workflow-breakdown)
- [📈 Metrics & Results](#-metrics--results)
- [📉 Polynomial Ridge Regression](#-polynomial-ridge-regression)
- [⚙️ Setup & Installation](#️-setup--installation)
- [📚 Core Libraries Used](#-core-libraries-used)
- [🙏 Acknowledgments](#-acknowledgments)
- [📜 License](#-license)

---

<h2 align="center">🧠 Project Overview</h2>

This project delivers a practical and analytical exploration of **house price prediction** using real estate data from **King County, Washington, USA**. It represents the capstone effort of the **Data Analysis with Python** course by IBM, combining core concepts of data wrangling, statistical analysis, and machine learning into a cohesive workflow.

By applying both **linear** and **ridge regression models**, along with **polynomial transformations**, the project investigates how multiple housing features—such as number of bedrooms, square footage, location, and waterfront views—affect property prices.

In addition to predictive modeling, the project emphasizes:
- 📊 Meaningful visualizations to support insights  
- 🧹 Clean data pipelines for reproducibility  
- 📈 Interpretable results using R² scores  
- 🧠 Logical reasoning behind each transformation

> ✅ Whether you're a homeowner, data analyst, or aspiring ML engineer, this project showcases how real-world housing data can inform intelligent decision-making through the power of regression.

---

<h2 align="center">🎯 Objectives</h2>

- Load and preprocess the dataset using pandas  
- Perform Exploratory Data Analysis (EDA)  
- Build Linear and Ridge regression models  
- Apply Polynomial transformation for second-order effects  
- Evaluate model performance with R² scores  
- Visualize predictions and residuals

---

<h2 align="center">📊 Dataset Info</h2>

- **Source**: House Sales in King County, USA  
- **Records**: 21,613 rows × 21 columns  
- **Target**: `price`  
- **Features**: Includes `sqft_living`, `bedrooms`, `bathrooms`, `grade`, `location` (lat/long), etc.

---

<h2 align="center">🛠️ Workflow Breakdown</h2>

1. Import libraries and load dataset  
2. Clean data (handle missing values, types)  
3. Visualize feature-target relationships  
4. Prepare features and target variables  
5. Train Linear & Ridge regression models  
6. Apply second-order polynomial transformation  
7. Evaluate and compare results using R²  
8. Visualize residuals and predictions

---

<h2 align="center">📈 Metrics & Results</h2>

| Model                          | R² Score (Test) |
|-------------------------------|-----------------|
| Linear Regression             | ~0.70           |
| Ridge Regression (α=0.1)      | ~0.71           |
| Polynomial Ridge Regression   | ~0.75+          |

> 📌 *Polynomial regression improved model fit, indicating non-linear feature effects on house pricing.*

---

<h2 align="center">📉 Polynomial Ridge Regression</h2>

The final step applied a second-order polynomial transform to capture interaction effects among features. Ridge regularization helped avoid overfitting.

```python
from sklearn.linear_model import Ridge
from sklearn.preprocessing import PolynomialFeatures

poly = PolynomialFeatures(degree=2)
x_train_poly = poly.fit_transform(x_train)
x_test_poly = poly.transform(x_test)

ridge = Ridge(alpha=0.1)
ridge.fit(x_train_poly, y_train)

r2 = ridge.score(x_test_poly, y_test)
print("Polynomial Ridge R²:", r2)
```

---

<h2 align="center">⚙️ Setup & Installation</h2>

```bash
# Optional: create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install numpy pandas matplotlib seaborn scikit-learn
```

---

<h2 align="center">📚 Core Libraries Used</h2>

<p align="center">
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy"/>
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"/>
  <img src="https://img.shields.io/badge/Matplotlib-008080?style=for-the-badge&logo=python&logoColor=white" alt="Matplotlib"/>
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white" alt="Scikit-learn"/>
</p>

---

<h2 align="center">🙏 Acknowledgments</h2>

This project was completed as part of the **Data Analysis with Python** course offered by **IBM®** through the **Skills Network** platform.

Special thanks to the **course instructors** for their clear explanations and practical examples, and to **IBM Skills Network** for providing a hands-on learning experience with real-world datasets and tools.

Your guidance played a key role in helping me apply data science techniques to solve real analytical problems. 🙌


---

<br><h2 align="center">🤝 Contact & Contribution</h2><br>

<p >
  <a href="mailto:maylzahid588@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-maylzahid588%40gmail.com-red?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail Badge">
  </a>
  <a href="https://www.linkedin.com/in/hamaylzahid/" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-Hamayl%20Zahid-blue?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn Badge">
  </a>
</p>

<p align="center">
  <a href="https://github.com/hamaylzahid/house-price-regression-analysis/stargazers">
    <img src="https://img.shields.io/github/stars/hamaylzahid/house-price-regression-analysis?style=for-the-badge&logo=github" alt="Star Badge">
  </a>
  <a href="https://github.com/hamaylzahid/house-price-regression-analysis/fork">
    <img src="https://img.shields.io/badge/PRs-Welcome-brightgreen?style=for-the-badge&logo=github" alt="PRs Welcome Badge">
  </a>
</p>

<p align="center">
  Have feedback, want to collaborate, or just say hello?<br>
  <strong>Let’s connect and build something amazing together!</strong>
</p>


---

<br><h2 align="center">📜 License</h2><br>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="MIT License"></a>
  <a href="https://github.com/hamaylzahid/house-price-regression-analysis/commits/main">
    <img src="https://img.shields.io/github/last-commit/hamaylzahid/house-price-regression-analysis?color=blue" alt="Last Commit">
  </a>
  <a href="https://github.com/hamaylzahid/house-price-regression-analysis">
    <img src="https://img.shields.io/github/repo-size/hamaylzahid/house-price-regression-analysis?color=lightgrey" alt="Repo Size">
  </a>
</p>

<p align="center">
  This project is licensed under the <strong>MIT License</strong> – free to use, modify, and distribute.
</p>

<p align="center">
  ✅ <strong>Project Status:</strong> Completed and ready for portfolio showcase  
  <br>
  🧾 <strong>License:</strong> MIT – <a href="LICENSE">View License »</a>
</p>

 ---

 
<p align="center">
  <img src="https://img.shields.io/badge/Built%20with-Python-blue?style=flat-square&logo=python&logoColor=white" alt="Python Badge" />
  <img src="https://img.shields.io/badge/EDA-Pandas%20%7C%20Matplotlib%20%7C%20Seaborn-1180aa?style=flat-square&logo=data:image/svg+xml;base64,PHN2ZyBmaWxsPSIjZmZmIiB3aWR0aD0iMjQiIGhlaWdodD0iMjQiPjxwYXRoIGQ9Ik0wIDBoMjR2MjRIMFYweiIvPjwvc3ZnPg==" alt="EDA Badge" />
  <img src="https://img.shields.io/badge/Regression-Linear%20%7C%20Ridge-blueviolet?style=flat-square" alt="Regression Badge" />
</p>

<p align="center">
  <b>Crafted with purpose & precision</b> 🧠  
</p>

<p align="center">
  <a href="https://github.com/hamaylzahid">
    <img src="https://img.shields.io/badge/GitHub-%40hamaylzahid-181717?style=flat-square&logo=github" alt="GitHub" />
  </a>
  •  
  <a href="mailto:maylzahid588@gmail.com">
    <img src="https://img.shields.io/badge/Email-Contact%20Me-red?style=flat-square&logo=gmail&logoColor=white" alt="Email Badge" />
  </a>
  •  
  <a href="https://github.com/hamaylzahid/house-price-regression-analysis">
    <img src="https://img.shields.io/badge/Repo-Link-blueviolet?style=flat-square&logo=github" alt="Repo" />
  </a>
  <br>
  <a href="https://github.com/hamaylzahid/house-price-regression-analysis/fork">
    <img src="https://img.shields.io/badge/Fork%20This%20Project-Start%20Building-2ea44f?style=flat-square&logo=github" alt="Fork Project Badge" />
  </a>
</p>

<p align="center">
  <sub><i>Inspired by learning. Driven by analysis. Designed to inform.</i></sub>
</p>

<p align="center">
  🔍 <b>Use this project to strengthen your Data Science portfolio</b>  
  <br>
  📦 Clone it, explore it, learn from it — and build something valuable.



<b>Ready to explore the notebook?</b> Click [here](./House_Price_Regression_Analysis_Final.ipynb) to dive in.

</p>

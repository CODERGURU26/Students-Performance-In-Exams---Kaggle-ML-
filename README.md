# 📚 Students Performance in Exams - Data Science Project

A comprehensive data science project analyzing student performance based on various demographic and educational factors. This project includes exploratory data analysis (EDA), feature engineering, data visualization, and machine learning to predict student success.

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=for-the-badge&logo=python&logoColor=white)

---

## 📑 Table of Contents

- [Project Overview](#project-overview)
- [Dataset Information](#dataset-information)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Project Workflow](#project-workflow)
- [Data Analysis](#data-analysis)
- [Visualizations](#visualizations)
- [Machine Learning Model](#machine-learning-model)
- [Key Findings](#key-findings)
- [Technologies Used](#technologies-used)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [Author](#author)

---

## 🎯 Project Overview

This project analyzes the performance of students in three subjects (Math, Reading, and Writing) based on various factors including:
- Gender
- Parental education level
- Test preparation course completion
- Lunch type
- Race/Ethnicity

**Objectives:**
- 📊 Perform comprehensive exploratory data analysis
- 🔍 Identify factors affecting student performance
- 📈 Create meaningful visualizations
- 🤖 Build a machine learning model to predict student success
- 💡 Derive actionable insights for educational improvement

---

## 📊 Dataset Information

### Source
**Students Performance in Exams Dataset** from Kaggle

### Dataset Overview
The dataset contains student performance data across three subjects with various demographic and educational factors.

### Features Description

| Feature | Description | Type |
|---------|-------------|------|
| **gender** | Student's gender (Male/Female) | Categorical |
| **race/ethnicity** | Student's racial/ethnic group (Group A-E) | Categorical |
| **parental level of education** | Highest education level of parents | Categorical |
| **lunch** | Type of lunch (standard/free or reduced) | Categorical |
| **test preparation course** | Completion status (completed/none) | Categorical |
| **math score** | Score in mathematics (0-100) | Numerical |
| **reading score** | Score in reading (0-100) | Numerical |
| **writing score** | Score in writing (0-100) | Numerical |

### Parental Education Levels
- Some high school
- High school
- Some college
- Associate's degree
- Bachelor's degree
- Master's degree

### Target Variables (Engineered)
- **average score**: Mean of math, reading, and writing scores
- **result**: Binary classification (1 = Pass ≥ 40, 0 = Fail < 40)

---

## ✨ Features

### Data Analysis
- ✅ **Comprehensive EDA**: Detailed exploration of student performance data
- ✅ **Statistical Analysis**: Distribution analysis and correlations
- ✅ **Missing Value Handling**: Data quality assessment
- ✅ **Feature Engineering**: Created average score and pass/fail indicators

### Visualizations
- ✅ **Gender-based Performance**: Bar charts comparing scores by gender
- ✅ **Parental Education Impact**: Line plots showing education influence
- ✅ **Test Preparation Analysis**: Comparison of students with/without prep courses
- ✅ **Multi-dimensional Analysis**: Hue-based visualizations for deeper insights

### Machine Learning
- ✅ **Binary Classification**: Predict student pass/fail status
- ✅ **Logistic Regression Model**: Statistical classification approach
- ✅ **Model Evaluation**: Accuracy score and confusion matrix
- ✅ **Train-Test Split**: Proper data splitting for validation

---

## 🚀 Installation

### Prerequisites
- Python 3.7 or higher
- Jupyter Notebook
- pip package manager

### Step 1: Clone the Repository

```bash
git clone https://github.com/CODERGURU26/Students-Performance-Analysis.git
cd Students-Performance-Analysis
```

### Step 2: Install Required Libraries

```bash
# Install core libraries
pip install pandas numpy matplotlib seaborn scikit-learn jupyter

# Or install all at once
pip install pandas numpy matplotlib seaborn scikit-learn jupyter openpyxl
```

### Step 3: Download the Dataset

Download the `StudentsPerformance.csv` file from Kaggle:
- [Students Performance in Exams Dataset](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)

Place the dataset in your project directory.

---

## 💻 Usage

### Running the Jupyter Notebook

1. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

2. **Open the Analysis Notebook**
   - Navigate to `Students_Performance_In_Exams_-_Kaggle.ipynb`
   - Update the file path in the notebook to your dataset location

3. **Run the Analysis**
   - Execute cells sequentially
   - Explore visualizations and insights
   - Train the machine learning model
   - Evaluate results

### Quick Start Example

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Load dataset
df = pd.read_csv('StudentsPerformance.csv')

# Display basic info
print(df.head())
print(df.info())
print(df.describe())
```

---

## 🔄 Project Workflow

### 1. **Data Loading**
```python
df = pd.read_csv('StudentsPerformance.csv')
```

### 2. **Data Cleaning**
- Check for missing values
- Verify data types
- Handle duplicates
- Validate data ranges

### 3. **Feature Engineering**

**Average Score Calculation:**
```python
df["average score"] = (df["math score"] + df["reading score"] + df["writing score"]) / 3
```

**Binary Classification Target:**
```python
df["result"] = df["average score"].apply(lambda x: 1 if x >= 40 else 0)
```

### 4. **Exploratory Data Analysis**
- Statistical summaries
- Distribution analysis
- Correlation exploration
- Group-based comparisons

### 5. **Data Visualization**
- Gender performance comparison
- Parental education impact
- Test preparation effectiveness
- Score distributions

### 6. **Model Training**
```python
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression

# Prepare features
X = df.drop(["math score", "reading score", "writing score", "result"], axis=1)
y = df["result"]

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Train model
model = LogisticRegression()
model.fit(X_train, y_train)
```

### 7. **Model Evaluation**
```python
from sklearn.metrics import accuracy_score, confusion_matrix

y_pred = model.predict(X_test)
accuracy = accuracy_score(y_test, y_pred)
print(f"Accuracy: {accuracy}")
```

---

## 📈 Data Analysis

### Key Statistics

**Score Distributions:**
- Math scores range: 0-100
- Reading scores range: 0-100
- Writing scores range: 0-100

**Categorical Distributions:**
- Gender: Male vs Female
- Race/Ethnicity: 5 groups (A-E)
- Parental Education: 6 levels
- Lunch Type: Standard vs Free/Reduced
- Test Prep: Completed vs None

### Analysis Questions Answered

1. **Do males or females perform better on average?**
   - Analyzed through gender-based bar plots
   - Compare average scores by gender

2. **How does parental education level affect student performance?**
   - Line plots showing trends across education levels
   - Separate analysis for male and female students

3. **Does test preparation course improve performance?**
   - Bar chart comparison of students with/without prep
   - Breakdown by gender

4. **What is the relationship between lunch type and performance?**
   - Statistical analysis of standard vs free/reduced lunch

5. **Which ethnic group performs best?**
   - Comparative analysis across groups A-E

---

## 📊 Visualizations

### 1. Gender Performance Comparison
```python
sns.barplot(x="gender", y="average score", data=df)
plt.title("Average Score by Gender")
plt.show()
```

**Insights:**
- Compare overall performance between male and female students
- Identify gender-based performance gaps

---

### 2. Parental Education Impact
```python
sns.lineplot(
    x="parental level of education",
    y="average score",
    hue="gender",
    marker="o",
    data=df
)
plt.xticks(rotation=45)
plt.title("Impact of Parental Education on Student Performance")
plt.show()
```

**Insights:**
- Higher parental education correlates with better student performance
- Gender differences across education levels
- Visual trend analysis

---

### 3. Test Preparation Course Effectiveness
```python
sns.barplot(
    x="test preparation course",
    y="average score",
    hue="gender",
    data=df
)
plt.title("Average Score by Test Preparation Course and Gender")
plt.show()
```

**Insights:**
- Students who completed prep courses tend to score higher
- Gender-based differences in prep course effectiveness

---

### 4. Score Distribution Analysis
```python
# Math score distribution
plt.hist(df["math score"], bins=20, edgecolor='black')
plt.title("Math Score Distribution")
plt.xlabel("Score")
plt.ylabel("Frequency")
plt.show()
```

---

### 5. Correlation Heatmap
```python
# Correlation between scores
score_cols = ["math score", "reading score", "writing score"]
sns.heatmap(df[score_cols].corr(), annot=True, cmap='coolwarm')
plt.title("Score Correlation Matrix")
plt.show()
```

**Insights:**
- Strong positive correlation between all three subjects
- Students good in one subject tend to be good in others

---

## 🤖 Machine Learning Model

### Model Type
**Logistic Regression** - Binary Classification

### Objective
Predict whether a student will pass (average score ≥ 40) or fail (average score < 40)

### Features Used
- Gender
- Race/Ethnicity
- Parental level of education
- Lunch type
- Test preparation course completion

### Target Variable
- **result**: 1 (Pass) or 0 (Fail)

### Model Pipeline

```python
# 1. Data Preparation
df_ml = df.drop(["math score", "reading score", "writing score"], axis=1)

# 2. Encode categorical variables
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
for col in df_ml.select_dtypes(include='object').columns:
    if col != 'result':
        df_ml[col] = le.fit_transform(df_ml[col])

# 3. Split features and target
X = df_ml.drop("result", axis=1)
y = df_ml["result"]

# 4. Train-test split
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

# 5. Train model
model = LogisticRegression()
model.fit(X_train, y_train)

# 6. Make predictions
y_pred = model.predict(X_test)

# 7. Evaluate
accuracy = accuracy_score(y_test, y_pred)
conf_matrix = confusion_matrix(y_test, y_pred)
```

### Model Evaluation Metrics

**Accuracy Score:**
- Percentage of correct predictions
- Measures overall model performance

**Confusion Matrix:**
```
                Predicted
                0    1
Actual    0   TN   FP
          1   FN   TP
```

- **True Positives (TP)**: Correctly predicted passes
- **True Negatives (TN)**: Correctly predicted fails
- **False Positives (FP)**: Incorrectly predicted passes
- **False Negatives (FN)**: Incorrectly predicted fails

### Additional Metrics (Optional)
```python
from sklearn.metrics import classification_report

print(classification_report(y_test, y_pred))
```

Provides:
- Precision: Accuracy of positive predictions
- Recall: Coverage of actual positives
- F1-Score: Harmonic mean of precision and recall

---

## 💡 Key Findings

### Performance Insights

1. **Gender Differences**
   - Analysis reveals performance variations between male and female students
   - Subject-specific strengths may vary by gender

2. **Parental Education Impact**
   - Strong positive correlation between parental education and student performance
   - Higher educated parents → better student outcomes

3. **Test Preparation Effectiveness**
   - Students completing test prep courses show improved performance
   - Significant boost in average scores

4. **Lunch Type Correlation**
   - Standard lunch students may outperform free/reduced lunch students
   - Indicates socioeconomic factors in education

5. **Subject Correlations**
   - High correlation between math, reading, and writing scores
   - Students excel or struggle across multiple subjects

### Recommendations

**For Educators:**
- Implement comprehensive test preparation programs
- Focus on students from lower education backgrounds
- Provide additional support for struggling subjects

**For Policymakers:**
- Address socioeconomic disparities (lunch programs)
- Invest in parental education initiatives
- Ensure equal access to test preparation resources

**For Students:**
- Complete test preparation courses
- Seek help across all subjects (correlated performance)
- Leverage available educational resources

---

## 🛠️ Technologies Used

### Core Libraries

| Technology | Purpose | Version |
|------------|---------|---------|
| **Python** | Programming language | 3.7+ |
| **Pandas** | Data manipulation | Latest |
| **NumPy** | Numerical computing | Latest |
| **Matplotlib** | Data visualization | Latest |
| **Seaborn** | Statistical visualization | Latest |
| **Scikit-learn** | Machine learning | Latest |
| **Jupyter Notebook** | Interactive development | Latest |

### Analysis Tools
- **Pandas**: Data loading, cleaning, manipulation
- **NumPy**: Numerical operations, array handling
- **Matplotlib**: Basic plotting and customization
- **Seaborn**: Advanced statistical visualizations

### Machine Learning
- **Scikit-learn**: Model training and evaluation
- **LogisticRegression**: Binary classification
- **train_test_split**: Data splitting
- **Metrics**: Accuracy, confusion matrix, classification report

---

## 📂 Project Structure

```
Students-Performance-Analysis/
│
├── Students_Performance_In_Exams_-_Kaggle.ipynb
│   └── Main Jupyter Notebook with complete analysis
│
├── StudentsPerformance.csv
│   └── Dataset (download from Kaggle)
│
├── visualizations/
│   ├── gender_performance.png
│   ├── parental_education_impact.png
│   ├── test_prep_effectiveness.png
│   └── score_distributions.png
│
├── requirements.txt
│   └── Python package dependencies
│
└── README.md
    └── Project documentation (this file)
```

---

## 🔮 Future Enhancements

### Analysis Improvements
- [ ] Add more advanced statistical tests (t-tests, ANOVA)
- [ ] Perform multivariate analysis
- [ ] Create interactive visualizations (Plotly, Dash)
- [ ] Add time series analysis (if temporal data available)
- [ ] Implement clustering analysis for student segmentation

### Machine Learning Enhancements
- [ ] Try multiple algorithms (Random Forest, SVM, XGBoost)
- [ ] Perform hyperparameter tuning
- [ ] Implement cross-validation
- [ ] Add feature importance analysis
- [ ] Create regression models for score prediction
- [ ] Build ensemble models

### Visualization Improvements
- [ ] Create interactive dashboards
- [ ] Add more chart types (violin plots, pair plots)
- [ ] Generate automated reports
- [ ] Build Power BI/Tableau dashboards
- [ ] Add animation for trends

### Deployment
- [ ] Create web application for predictions
- [ ] Build API for model serving
- [ ] Deploy dashboard online
- [ ] Create mobile app interface
- [ ] Implement real-time predictions

### Documentation
- [ ] Add detailed comments
- [ ] Create video tutorials
- [ ] Write blog post about findings
- [ ] Add case studies
- [ ] Create presentation slides

---

## 📊 Sample Analysis Code

### Basic Statistics
```python
# Summary statistics
print(df.describe())

# Group by gender
print(df.groupby('gender')[['math score', 'reading score', 'writing score']].mean())

# Test prep impact
print(df.groupby('test preparation course')['average score'].mean())
```

### Advanced Visualization
```python
# Create subplots for all three subjects
fig, axes = plt.subplots(1, 3, figsize=(15, 5))

sns.histplot(df['math score'], bins=20, kde=True, ax=axes[0])
axes[0].set_title('Math Score Distribution')

sns.histplot(df['reading score'], bins=20, kde=True, ax=axes[1])
axes[1].set_title('Reading Score Distribution')

sns.histplot(df['writing score'], bins=20, kde=True, ax=axes[2])
axes[2].set_title('Writing Score Distribution')

plt.tight_layout()
plt.show()
```

### Performance Analysis
```python
# Average scores by parental education
education_performance = df.groupby('parental level of education')['average score'].mean().sort_values(ascending=False)
print(education_performance)

# Performance by race/ethnicity
ethnicity_performance = df.groupby('race/ethnicity')[['math score', 'reading score', 'writing score']].mean()
print(ethnicity_performance)
```

---

## 🐛 Troubleshooting

### Common Issues

#### Issue 1: File Path Error
**Error:** `FileNotFoundError: StudentsPerformance.csv`

**Solution:**
```python
# Use raw string for Windows paths
df = pd.read_csv(r"C:\path\to\StudentsPerformance.csv")

# Or use forward slashes
df = pd.read_csv("C:/path/to/StudentsPerformance.csv")

# Or place file in same directory
df = pd.read_csv("StudentsPerformance.csv")
```

#### Issue 2: Encoding Categorical Variables
**Error:** Cannot fit string data to model

**Solution:**
```python
from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()
for col in df.select_dtypes(include='object').columns:
    df[col] = le.fit_transform(df[col])
```

#### Issue 3: Average Score Calculation
**Error:** Incorrect average calculation

**Solution:**
```python
# Correct formula
df["average score"] = (df["math score"] + df["reading score"] + df["writing score"]) / 3

# Not this
df["average score"] = df["math score"] + df["reading score"] + df["writing score"] / 3
```

---

## 🎓 Learning Outcomes

This project demonstrates proficiency in:

- ✅ **Data Analysis**: Comprehensive EDA techniques
- ✅ **Data Visualization**: Creating meaningful plots and charts
- ✅ **Feature Engineering**: Creating new features from existing data
- ✅ **Statistical Analysis**: Understanding distributions and correlations
- ✅ **Machine Learning**: Binary classification with Logistic Regression
- ✅ **Model Evaluation**: Using accuracy and confusion matrix
- ✅ **Python Programming**: Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn
- ✅ **Data Storytelling**: Deriving insights from data

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/NewAnalysis
   ```
3. **Make your changes**
   - Add new visualizations
   - Try different ML models
   - Improve documentation
4. **Commit your changes**
   ```bash
   git commit -m 'Add new analysis: Feature Name'
   ```
5. **Push and create Pull Request**

### Contribution Ideas
- Add regression analysis for score prediction
- Implement advanced ML algorithms
- Create interactive dashboards
- Add statistical hypothesis testing
- Improve visualizations
- Write detailed interpretations

---

## 📧 Contact & Connect

### Author

**Gururaj Krishna Sharma**

- 📧 Email: [guruuu2468@gmail.com](mailto:guruuu2468@gmail.com)
- 💼 LinkedIn: [Gururaj Krishna Sharma](https://www.linkedin.com/in/gururaj-krishna-sharma)
- 💻 GitHub: [@CODERGURU26](https://github.com/CODERGURU26)

---

## 🌟 Acknowledgments

- **Kaggle** for hosting the dataset
- **Scikit-learn** developers for ML tools
- **Seaborn & Matplotlib** teams for visualization libraries
- **Educational research community** for data collection
- **Python community** for extensive documentation

---

## 📚 Additional Resources

### Learn More
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Seaborn Gallery](https://seaborn.pydata.org/examples/index.html)
- [Scikit-learn User Guide](https://scikit-learn.org/stable/user_guide.html)
- [Kaggle Datasets](https://www.kaggle.com/datasets)

### Related Projects
- Student dropout prediction
- Grade prediction systems
- Educational analytics dashboards
- Performance improvement recommendations

### Recommended Reading
- "Python for Data Analysis" by Wes McKinney
- "Hands-On Machine Learning" by Aurélien Géron
- "Storytelling with Data" by Cole Nussbaumer Knaflic

---

## 🎯 Project Impact

This project can help:

**Educators:**
- Identify at-risk students early
- Tailor intervention programs
- Allocate resources effectively

**Administrators:**
- Make data-driven policy decisions
- Evaluate program effectiveness
- Track performance trends

**Students:**
- Understand factors affecting performance
- Seek appropriate support
- Set realistic goals

**Researchers:**
- Build upon analysis methods
- Develop new educational models
- Contribute to educational literature

---

**⭐ If you find this project helpful, please give it a star!**

**🔔 Watch this repository for updates and improvements!**

---

*Last Updated: February 2026*

**Happy Learning! 📚🎓**

# Employee Attrition Prediction System

A comprehensive machine learning system that predicts employee attrition risk using advanced classification techniques. This project analyzes various factors such as job satisfaction, salary, work environment, experience, and demographics to identify employees at risk of leaving the organization.

![Python](https://img.shields.io/badge/Python-3.12-blue.svg)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.8.0-orange.svg)
![Pandas](https://img.shields.io/badge/Pandas-3.0.1-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Model Performance](#model-performance)
- [Key Findings](#key-findings)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Visualizations](#visualizations)
- [Business Recommendations](#business-recommendations)
- [Future Improvements](#future-improvements)
- [Contributing](#contributing)
- [License](#license)

## Overview

Employee attrition is a critical concern for organizations, impacting productivity, morale, and costs. This project leverages machine learning to:
- Predict which employees are likely to leave
- Identify key factors contributing to attrition
- Provide actionable insights for HR teams
- Enable proactive retention strategies

## Features

- **Comprehensive Data Analysis**: Exploratory data analysis with 35+ employee features
- **Multiple ML Models**: Implementation of Logistic Regression, Decision Trees, and Random Forest
- **Feature Importance Analysis**: Identification of key attrition drivers
- **Interactive Visualizations**: Rich charts and graphs for data insights
- **Risk Scoring**: Individual employee attrition risk calculation
- **Business Insights**: Strategic recommendations for HR teams
- **Model Comparison**: Detailed performance metrics across all models

## Dataset

The system uses the **HR Employee Attrition Dataset** containing:
- **Records**: 1,470 employees
- **Features**: 35 attributes including:
  - **Demographics**: Age, Gender, Marital Status
  - **Job Details**: Job Role, Department, Job Level
  - **Compensation**: Monthly Income, Salary Hike, Stock Options
  - **Satisfaction**: Job Satisfaction, Environment Satisfaction, Work-Life Balance
  - **Experience**: Years at Company, Total Working Years, Years in Current Role
  - **Performance**: Performance Rating, Job Involvement
  - **Work Patterns**: Business Travel, Overtime, Distance from Home

- **Target Variable**: Attrition (Yes/No)
- **Attrition Rate**: 16.12% (237 out of 1,470 employees)

## Installation

### Prerequisites
- Python 3.12+
- pip package manager

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/HimalRana2610/Algonive_Employee_Attrition_Prediction_System.git
   cd Algonive_Employee_Attrition_Prediction_System
   ```

2. **Create a virtual environment** (recommended)
   ```bash
   python -m venv env
   ```

3. **Activate the virtual environment**
   - Windows:
     ```bash
     .\env\Scripts\activate
     ```
   - Linux/Mac:
     ```bash
     source env/bin/activate
     ```

4. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

5. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook app.ipynb
   ```

## Usage

### Running the Analysis

1. Open `app.ipynb` in Jupyter Notebook
2. Run cells sequentially to:
   - Load and explore the dataset
   - Perform exploratory data analysis
   - Train machine learning models
   - Visualize results and insights
   - Generate predictions

### Making Predictions

```python
# Load the trained model
best_model = results['Random Forest']['model']

# Create employee profile
employee_data = pd.DataFrame({
    'Age': [30],
    'MonthlyIncome': [3500],
    'YearsAtCompany': [2],
    # ... other features
})

# Predict attrition risk
prediction = best_model.predict(employee_data)
risk_probability = best_model.predict_proba(employee_data)[:, 1]

print(f"Attrition Risk: {risk_probability[0]*100:.2f}%")
```

## Model Performance

| Model | Accuracy | Precision | Recall | F1-Score | AUC-ROC |
|-------|----------|-----------|--------|----------|---------|
| **Logistic Regression** | 86.73% | 75.00% | 25.53% | 38.10% | 0.7766 |
| **Decision Tree** | 80.27% | 35.90% | 29.79% | 32.56% | 0.5708 |
| **Random Forest** | **84.01%** | **50.00%** | **12.77%** | **20.34%** | **0.7934** |

### Recommended Model: Random Forest
The Random Forest model is recommended for production deployment due to:
- Highest AUC-ROC score (0.7934)
- Best overall accuracy
- Robust performance across different metrics
- Lower overfitting compared to Decision Tree

## Key Findings

### Top Attrition Risk Factors

1. **Monthly Income** (7.24% importance)
   - Employees who left: $4,787 average
   - Employees who stayed: $6,832 average
   - **Impact**: Lower salary = Higher attrition risk

2. **Age** (6.95% importance)
   - Employees who left: 33.6 years average
   - Employees who stayed: 37.6 years average
   - **Impact**: Younger employees more likely to leave

3. **Total Working Years** (6.46% importance)
   - Experience level correlates with retention

4. **Years at Company** (4.27% importance)
   - Employees who left: 5.1 years average
   - Employees who stayed: 7.4 years average
   - **Impact**: Early-tenure employees at highest risk

5. **Overtime** (3.78% importance)
   - Excessive overtime increases attrition

### Department-wise Attrition Rates
- **Sales**: 20.63% (highest)
- **Human Resources**: 19.05%
- **Research & Development**: 13.84% (lowest)

### Job Satisfaction Impact
- Lower job satisfaction (Level 1) shows higher attrition
- Work-life balance rating of 1 has 31.25% attrition rate

## Technologies Used

### Core Libraries
- **Python 3.12** - Programming language
- **Pandas 3.0.1** - Data manipulation and analysis
- **NumPy 2.4.2** - Numerical computations
- **Scikit-learn 1.8.0** - Machine learning models and metrics

### Visualization
- **Matplotlib 3.10.8** - Plotting and charts
- **Seaborn 0.13.2** - Statistical visualizations

### Development Environment
- **Jupyter Notebook** - Interactive development
- **IPython 9.10.0** - Enhanced Python shell

## Project Structure

```
Algonive_Employee_Attrition_Prediction_System/
│
├── app.ipynb                      # Main Jupyter notebook with analysis
├── requirements.txt               # Python dependencies
├── README.md                      # Project documentation
│
├── Data/
│   └── HR-Employee-Attrition.csv # HR dataset
│
└── env/                          # Virtual environment (not in repo)
```

## Visualizations

The project includes comprehensive visualizations:

### Data Distribution
- Attrition distribution (bar chart & pie chart)
- Feature distributions by attrition status
- Correlation heatmap

### Model Performance
- Confusion matrices for all models
- ROC curves comparison
- Model metrics comparison charts

### Feature Analysis
- Feature importance rankings
- Boxplots for numeric features vs. attrition
- Categorical feature analysis

### Business Insights
- Department-wise attrition rates
- Salary impact analysis
- Tenure and age distribution

## Business Recommendations

### 1. **Compensation Strategy**
- Review and adjust salaries, especially in Sales and HR departments
- Implement competitive compensation packages
- Regular market rate benchmarking

### 2. **Retention Programs**
- Focus on employees in their first 1-2 years
- Target age group 25-35 with career development
- Create mentorship programs

### 3. **Work-Life Balance**
- Monitor and manage overtime hours
- Implement flexible work arrangements
- Encourage time-off and wellness programs

### 4. **Job Satisfaction**
- Conduct regular employee satisfaction surveys
- Address concerns in low-satisfaction departments
- Improve role clarity and career progression paths

### 5. **Proactive Monitoring**
- Deploy the Random Forest model to identify at-risk employees
- Generate monthly risk reports for HR teams
- Implement early intervention programs

### 6. **Department-Specific Actions**
- **Sales**: Address high attrition (20.63%) with improved incentives
- **HR**: Review workload and satisfaction levels (19.05% attrition)
- **R&D**: Maintain current retention strategies (13.84% attrition)

## Future Improvements

### Model Enhancements
- [ ] Implement ensemble methods (XGBoost, LightGBM)
- [ ] Add hyperparameter optimization (GridSearchCV)
- [ ] Address class imbalance with SMOTE
- [ ] Feature engineering (interaction terms, polynomial features)

### System Features
- [ ] Real-time prediction API
- [ ] Interactive dashboard with Streamlit/Dash
- [ ] Automated model retraining pipeline
- [ ] Integration with HR management systems

### Analysis Extensions
- [ ] Time-series analysis of attrition trends
- [ ] Survival analysis for tenure prediction
- [ ] Cost-benefit analysis of retention programs
- [ ] Sentiment analysis from employee feedback

### Deployment
- [ ] Containerization with Docker
- [ ] Cloud deployment (AWS/Azure)
- [ ] CI/CD pipeline setup
- [ ] Model monitoring and drift detection
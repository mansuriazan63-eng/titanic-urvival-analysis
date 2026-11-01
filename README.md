# Titanic Survival Analysis

Exploratory Data Analysis (EDA) on the Titanic dataset to understand which
factors influenced passenger survival, using Python data analysis and
visualization libraries.

## Dataset
- **Source:** [Titanic - Machine Learning from Disaster (Kaggle)](https://www.kaggle.com/c/titanic)
- **File used:** `train.csv` (891 passengers, 12 columns)
- **Key columns:** Survived, Pclass, Sex, Age, SibSp, Parch, Fare, Embarked

## Tools & Libraries
- Python 3
- Pandas, NumPy: data manipulation
- Matplotlib, Seaborn: data visualization
- Jupyter Notebook

## Project Structure
```
titanic-survival-analysis/
├── analysis.ipynb
├── train.csv
├── images/
├── requirements.txt
└── README.md
```

## Steps Performed
1. Loaded the dataset and inspected its shape, data types, statistics and missing values.
2. Cleaned the data: handled missing values and removed duplicate rows.
3. Created new features: `FamilySize` and `AgeGroup`.
4. Visualized survival by gender, passenger class, age, fare, embarkation port and family size.
5. Plotted a correlation heatmap and summarized the findings.

## Assumptions
- Missing `Age` values were filled with the **median** to reduce the effect of outliers.
- Missing `Embarked` values (2 rows) were filled with the **most frequent port** (mode).
- The `Cabin` column was **dropped** because most of its values are missing.
- The dataset is assumed to be a representative sample of Titanic passengers.
- `FamilySize` was calculated as `SibSp + Parch + 1` (the passenger included).

## Visualizations
![Survival Count](images/survival_count.png)
![Survival by Gender](images/survival_gender.png)
![Survival by Class](images/survival_class.png)
![Age Distribution](images/age_distribution.png)
![Survival by Age Group](images/survival_agegroup.png)
![Class and Gender](images/class_gender.png)
![Fare, Port and Family Size](images/fare_port_family.png)
![Correlation Heatmap](images/correlation_heatmap.png)

## Key Findings
- The overall survival rate was **38.38%** (out of 891 passengers).
- **Gender** was the strongest factor: **74.20%** of women survived compared to only **18.89%** of men.
- **Passenger class** mattered a lot: survival was **62.96%** in 1st class, **47.28%** in 2nd class and **24.24%** in 3rd class.
- **Age:** children (up to 12 years) had the highest survival rate at **57.97%**, while seniors (60+) had the lowest at **22.73%**.
- **Fare:** survivors paid higher fares on average (median fare of survivors is clearly higher than non-survivors), and Fare has a positive correlation with survival (**0.26**).
- **Embarkation port:** passengers who boarded at Cherbourg (C) survived more often (about 55%) than those from Southampton (S, about 34%).
- **Family size:** passengers travelling with 1 to 3 family members (family size 2 to 4) survived more often than people travelling alone (about 30%) or in very large families (5 or more).
- In the correlation heatmap, `Pclass` has the strongest negative correlation with survival (**-0.34**), and `Pclass` and `Fare` are strongly negatively correlated (**-0.55**).

## How to Run
1. Clone the repository:
   ```
   git clone https://github.com/<your-username>/titanic-survival-analysis.git
   cd titanic-survival-analysis
   ```
2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Open the notebook:
   ```
   jupyter notebook analysis.ipynb
   ```
4. Run the cell. Charts are saved in the `images/` folder.

## Author
kaif

## Acknowledgements
Dataset provided by Kaggle.

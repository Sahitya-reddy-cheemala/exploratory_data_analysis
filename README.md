Titanic Dataset - Exploratory Data Analysis (EDA)
Dataset-Titanic dataset.csv
Loaded from: C:/Users/RGUKT/OneDrive/Desktop/internship_task5/titanic_dataset.csv
Key Libraries Used:
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
Analysis Performed
 1)Data Loading & Inspection
Loaded using pandas
Inspected with df.head(), df.info(), and df.describe()
df.head()
 Shows the first 5 rows of your dataset.
 df.info()
  Gives a summary of the dataset structure.
df.describe()
Provides statistical summaries for all numeric columns.
visualizations
sns.barplot(data=df, x='Sex', y='Survived')
Shows that females had a much higher survival rate than males.
2. Age Distribution
python
Copy
Edit
sns.histplot(data=df, x='Age', bins=30, kde=True)
Displays the spread of passenger ages with a smooth density curve.

3. Fare Distribution
python
Copy
Edit
sns.histplot(data=df, x='Fare', bins=30, kde=True)
Shows that most passengers paid low fares, with some paying very high (outliers).

4. Survival by Age
python
Copy
Edit
sns.boxplot(data=df, x='Survived', y='Age')
Compares age distributions between survivors and non-survivors.

5. Fare by Passenger Class
python
Copy
Edit
sns.boxplot(data=df, x='Pclass', y='Fare')
Reveals that 1st class passengers paid much higher fares.

6. Age vs. Fare Colored by Survival
python
Copy
Edit
sns.scatterplot(data=df, x='Age', y='Fare', hue='Survived')
Visualizes the relationship between age, fare, and survival.

7. Siblings/Spouses Aboard vs. Fare
python
Copy
Edit
sns.scatterplot(data=df, x='SibSp', y='Fare', hue='Survived')
Helps examine family connections and their link to fare and survival.

8. Survival Count by Family Size
df['FamilySize'] = df['SibSp'] + df['Parch'] + 1
sns.boxplot(data=df, x='FamilySize', y='Survived')
Explores how having family aboard affected survival.

9. Correlation Heatmap
python
Copy
Edit
corr = df[numeric_features].corr()
sns.heatmap(corr, annot=True, cmap='coolwarm', fmt=".2f")
Shows relationships between numeric features like Age, Fare, Pclass, etc.
Women and 1st class passengers had higher survival rates.
Younger passengers and those with small families were more likely to survive.
Fare and Pclass are strongly correlated.
Most passengers paid lower fares, and few paid very high fares (outliers).



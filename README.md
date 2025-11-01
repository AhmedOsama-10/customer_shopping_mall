# Customer Shopping Behavior Analysis (Python EDA)

This project is a comprehensive Exploratory Data Analysis (EDA) using **Python**, **Pandas**, and **Seaborn** to understand the patterns and behaviors within a customer shopping dataset containing nearly 100,000 transactions.

**Dataset Link:** [Customer Shopping Dataset on Kaggle](https://www.kaggle.com/datasets/mehmettahiraslan/customer-shopping-dataset)

---

## 🎯 Project Objective

The primary goal is to dive into the transactional data to uncover actionable insights. This includes:
* Cleaning and preparing the data for analysis.
* Understanding the customer demographics (e.g., age, gender).
* Identifying the most popular product categories, payment methods, and shopping malls.
* Analyzing sales trends over time.
* Discovering relationships between different variables (e.g., do certain age groups prefer specific categories?).

---

## 🛠️ Project Workflow

The entire analysis was conducted within a Jupyter Notebook (`Project.ipynb`). The process followed these key stages:

### 1. Data Cleaning & Preparation
* **Import Libraries:** Imported essential libraries (`Pandas`, `NumPy`, `Matplotlib`, `Seaborn`).
* **Load Data:** Loaded the `customer_shopping_data.csv` file into a Pandas DataFrame.
* **Inspect Data:**
    * Checked for null values using `data.info()` and `data.isnull().sum()`. **Result: No null values.**
    * Checked for duplicate rows using `data.duplicated().sum()`. **Result: No duplicate rows.**
* **Correct Data Types:** Converted the `invoice_date` column from an `object` type to `datetime` to enable time-series analysis.
* **Manage Columns:** Dropped non-analytical columns (`invoice_no`, `customer_id`) to streamline the dataset.

### 2. Feature Engineering
To gain deeper insights, new features were created from existing data:
* **Date Components:** Extracted new columns from `invoice_date`:
    * `day`
    * `month`
    * `year`
    * `month/year`
    * `week`
    * `quarter`
* **Age Grouping:** Created a categorical `age_group_labeled` column by binning the numerical `age` column into descriptive groups (e.g., 'Young Adult', 'Adult', 'Senior') using `pd.cut`.

### 3. Exploratory Data Analysis (EDA)
* **Univariate Analysis:**
    * Analyzed the distribution of key categorical variables (`gender`, `category`, `payment_method`, `shopping_mall`) using `value_counts()` and `seaborn.countplot` charts to understand frequencies.
* **Outlier Analysis:**
    * Used the IQR method and **Seaborn boxplots** to identify outliers in the `price` column, noting they were most prominent in the 'Technology' and 'Shoes' categories.
* **Bivariate & Multivariate Analysis:**
    * Used `pd.crosstab` and `groupby` extensively to uncover relationships.
    * Analyzed total sales by `age_group_labeled` to understand spending habits across demographics.
    * Analyzed purchasing preferences (categories, payment methods, preferred malls) broken down by `gender`.
    * Created pivot tables to analyze total `price` aggregated by `shopping_mall`, `gender`, `category`, and `year`.
* **Time-Series Analysis:**
    * Plotted the total monthly sales using a `seaborn.lineplot` to visualize sales trends over time.

---

## 💡 Key Insights
* **Customers:** The customer base is skewed towards **Females (approx. 60%)**.
* **Products:** **"Clothing"** is the highest-selling category by a significant margin.
* **Payments:** **"Cash"** is the most common payment method, followed by "Credit Card".
* **Location:** The **"Mall of Istanbul"** records the highest number of transactions.
* **Spending:** Different age groups exhibit distinct spending patterns and clear preferences for specific product categories.

---

## 🔧 Technologies Used
* **Python**
* **Pandas:** For all data manipulation, cleaning, and analysis.
* **Matplotlib & Seaborn:** For data visualization.
* **NumPy:** For numerical operations.
* **Jupyter Notebook:** As the development environment for the analysis.

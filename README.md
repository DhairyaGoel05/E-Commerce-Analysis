# E-Commerce-Analysis

This project performs an in-depth analysis of an e-commerce dataset to extract meaningful insights. The dataset includes details such as purchase prices, customer languages, job titles, email addresses, and credit card information.

## Project Features

The following operations are conducted in this analysis:

### Dataset Operations

1. **Importing Necessary Libraries**
   ```python
   import pandas as pd
   ```
2. **Loading the Dataset**
   ```python
   data = pd.read_csv("Ecommerce Purchases.txt")
   ```

### Exploratory Data Analysis

1. **Display Top 10 Rows of the Dataset**
   ```python
   data.head(10)
   ```

2. **Check Last 10 Rows of the Dataset**
   ```python
   data.tail()
   ```

3. **Check Datatypes of Each Column**
   ```python
   data.dtypes
   ```

4. **Check Null Values in the Dataset**
   ```python
   data.isnull().sum()
   ```

5. **Determine the Number of Rows and Columns**
   ```python
   len(data.columns)  # Number of columns
   len(data)          # Number of rows
   ```

6. **Get Dataset Information**
   ```python
   data.info()
   ```

### Key Insights

1. **Highest and Lowest Purchase Prices**
   ```python
   data['Purchase Price'].max()  # Maximum purchase price
   data['Purchase Price'].min()  # Minimum purchase price
   ```

2. **Average Purchase Price**
   ```python
   data['Purchase Price'].mean()
   ```

3. **Number of People with French ('fr') as Their Language**
   ```python
   (data['Language'] == 'fr').sum()
   ```

4. **Number of Job Titles Containing 'Engineer'**
   ```python
   len(data[data['Job'].str.contains('engineer', case=False)])
   ```

5. **Email of the Person with IP Address `132.207.160.22`**
   ```python
   data[data['IP Address'] == '132.207.160.22']['Email']
   ```

6. **Number of People Using Mastercard with Purchases Above $50**
   ```python
   len(data[(data['CC Provider'] == 'Mastercard') & (data['Purchase Price'] > 50)])
   ```

7. **Email of the Person with Credit Card Number `4664825258997302`**
   ```python
   data[data['Credit Card'] == '4664825258997302']['Email']
   ```

8. **Number of Purchases During AM vs PM**
   ```python
   data['AM or PM'].value_counts()
   ```

9. **Number of People with Credit Cards Expiring in 2020**
   ```python
   def fun():
       count = 0
       for date in data['CC Exp Date']:
           if date.split('/')[1] == '20':
               count += 1
       print(count)
   fun()
   ```

10. **Top 5 Most Popular Email Providers**
    ```python
    list1 = []
    for email in data['Email']:
        list1.append(email.split('@')[1])

    data['temp'] = list1
    data['temp'].value_counts().head()
    ```

## Prerequisites

- Python 3.x
- Pandas library

## How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/your_username/e-commerce-analysis.git
   ```

2. Navigate to the project directory:
   ```bash
   cd e-commerce-analysis
   ```

3. Install the necessary libraries:
   ```bash
   pip install pandas
   ```

4. Run the script in a Python environment:
   ```bash
   python analysis.py
   ```

## Dataset

The dataset used in this project is named `Ecommerce Purchases.txt` and contains the following columns:

- **Purchase Price**
- **Language**
- **Job**
- **IP Address**
- **CC Provider**
- **Credit Card**
- **AM or PM**
- **CC Exp Date**
- **Email**

## Results

This analysis provides insights into customer behavior, preferences, and patterns based on the dataset. For example:

- The highest and lowest purchase prices
- The average purchase price
- Popular email domains
- Trends in purchase timings (AM/PM)
- Credit card provider usage statistics

## License

This project is open-source and available under the [MIT License](LICENSE).

## Author

Dhairya Goel


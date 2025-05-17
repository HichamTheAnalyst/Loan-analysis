# 🧮 Loan Data Preprocessing with NumPy

This project demonstrates how to **clean, preprocess, and manipulate loan data** using only NumPy — without the use of pandas. It focuses on handling missing values, splitting data into numeric and categorical features, and preparing it for further analysis or modeling.

---

## 📁 Dataset

The project uses a dataset called `loan-data.csv`, which includes information about loan applications such as loan amount, interest rate, term, grade, verification status, issue date, and more.

---

## 🧰 Features of the Project

* ✅ Importing and viewing raw data using NumPy
* 🔍 Identifying and handling missing values
* 🧠 Computing summary statistics (min, mean, max)
* 🧩 Splitting dataset into:

  * **Numeric columns**
  * **String (categorical) columns**
* 🧼 Re-importing each subset using `usecols`
* 💾 Creating reusable checkpoint files for cleaned data
* 🛠 String manipulation:

  * Converting months to numeric format
  * Binarizing loan status (good vs bad loans)
  * Extracting and formatting loan terms
  * Mapping grades and subgrades

---

## 🧪 Example Code Snippets

```python
# Load the dataset
raw_data_np = np.genfromtxt("loan-data.csv", delimiter=';', skip_header=1, autostrip=True)

# Find missing values
np.isnan(raw_data_np).sum()

# Split into string and numeric columns
columns_strings = np.argwhere(np.isnan(temporary_mean)).squeeze()
columns_numeric = np.argwhere(np.isnan(temporary_mean) == False).squeeze()
```

```python
# Convert 'issue_date' to numeric
months = np.array(['', 'Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun',
                   'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'])

for i in range(13):
    loan_data_strings[:,0] = np.where(loan_data_strings[:,0] == months[i],
                                      i,
                                      loan_data_strings[:,0])
```

---

## 📊 Columns Overview

| Column Type | Columns                                                                                               |
| ----------- | ----------------------------------------------------------------------------------------------------- |
| Numeric     | `id`, `loan_amnt`, `funded_amnt`, `int_rate`, `installment`, `total_pymnt`                            |
| Categorical | `issue_date`, `loan_status`, `term`, `grade`, `sub_grade`, `verification_status`, `url`, `addr_state` |

---

## 💾 Checkpoint Function

To facilitate saving and reloading cleaned data:

```python
def checkpoint(file_name, checkpoint_header, checkpoint_data):
    np.savez(file_name, header=checkpoint_header, data=checkpoint_data)
    return np.load(file_name + ".npz")
```

---

## 📌 Requirements

* Python 3.x
* NumPy

---

## 📈 Status

✅ Completed basic data loading, cleaning, and preprocessing.
🔄 Further steps can include:

* Feature engineering
* Feeding the cleaned data into a machine learning pipeline

---

## 📚 Learning Objectives

* Practice **data preprocessing** using NumPy (instead of pandas)
* Understand how to **manipulate mixed-type datasets**
* Learn **basic feature cleaning techniques** used in real-world financial datasets

---

## 🧑‍💻 Author

**Hicham Nouhaidi**
Data Scientist | Accountant | Cloud & Analytics Enthusiast
📍 Casablanca, Morocco



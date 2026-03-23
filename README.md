\# Vendor Invoice Intelligence System

\*\*Freight Cost Prediction \& Invoice Risk Flagging\*\*



\---



\## 📌 Project Overview



This project implements an \*\*end-to-end machine learning system\*\* designed to support finance and procurement teams by:



1\. \*\*Predicting expected freight cost\*\* for vendor invoices using historical patterns

2\. \*\*Flagging high-risk invoices\*\* that require manual review due to abnormal cost, freight, or operational patterns



\---



\## 🎯 Business Objectives



\### 1. Freight Cost Prediction (Regression)

Predict the expected freight cost for a vendor invoice using quantity, invoice value, and historical behavior.

\- Freight is a key component of landed cost

\- Poor estimation impacts margin analysis and budgeting

\- Early prediction improves procurement planning and vendor negotiation



\### 2. Invoice Risk Flagging (Classification)

Predict whether a vendor invoice should be flagged for manual approval.

\- Manual invoice review does not scale

\- Financial leakage often occurs in large or complex invoices

\- Early risk detection improves audit efficiency and operational control



\---



\## 📂 Data Sources



Data is stored in a relational \*\*SQLite database\*\* with the following tables:

\- `vendor\_invoice` – Invoice-level financial and timing data

\- `purchases` – Item-level purchase details

\- `purchase\_prices` – Reference purchase prices

\- `begin\_inventory`, `end\_inventory` – Inventory snapshots



SQL aggregation is used to generate \*\*invoice-level features\*\*.



\---



\## 📊 Exploratory Data Analysis (EDA)



EDA focuses on business-driven questions such as:

\- Do flagged invoices have higher financial exposure?

\- Does freight scale linearly with quantity?

\- How does vendor behavior vary across invoice types?



\*\*Statistical tests (t-tests)\*\* are used to confirm that flagged invoices differ meaningfully from normal invoices.



\---



\## 🤖 Models Used



\### Regression — Freight Cost Prediction

| Model | Role |

|---|---|

| Linear Regression | Baseline |

| Decision Tree Regressor | Intermediate |

| Random Forest Regressor | ✅ Final Model |



\### Classification — Invoice Risk Flagging

| Model | Role |

|---|---|

| Logistic Regression | Baseline |

| Decision Tree Classifier | Intermediate |

| Random Forest + GridSearchCV | ✅ Final Model |



\---



\## 📈 Evaluation Metrics



\### Freight Prediction

\- MAE, RMSE, R² Score



\### Invoice Flagging

\- Accuracy, Precision, Recall, F1-Score

\- Classification Report

\- Feature Importance Analysis



\---



\## 🖥️ Streamlit Application



A \*\*Streamlit web app\*\* demonstrates the complete pipeline:

\- Input invoice details

\- Predict expected freight cost

\- Flag invoices in real time

\- Provide human-readable explanations

```bash

streamlit run app.py

```



\---



\## 📁 Project Structure

```

Vendor-Invoice-Intelligence-System/

│

├── freight\_cost\_prediction/

│   ├── data\_preprocessing.py

│   ├── modeling\_evaluation.py

│   └── train.py

│

├── invoice\_flagging/

│   ├── data\_preprocessing.py

│   ├── modeling\_evaluation.py

│   └── train.py

│

├── inference/

│   ├── predict\_freight.py

│   └── predict\_invoice\_flag.py

│

├── models/

│   ├── predict\_freight\_model.pkl

│   ├── scaler.pkl

│   └── predict\_flag\_invoice.pkl

│

├── notebooks/

│   ├── Invoice Flagging.ipynb

│   └── Predicting Freight Cost.ipynb

│

├── images/

├── app.py

├── README.md

└── .gitignore

```



\---



\## 🚀 How to Run



1\. Clone the repository:

```bash

git clone https://github.com/Abhijeet31-Singh/Vendor-Invoice-Intelligence-System.git

```



2\. Train the models:

```bash

python freight\_cost\_prediction/train.py

python invoice\_flagging/train.py

```



3\. Test inference:

```bash

python inference/predict\_freight.py

python inference/predict\_invoice\_flag.py

```



4\. Launch the app:

```bash

streamlit run app.py

```



\---



\## 👤 Author



\*\*Abhijeet Singh\*\*

🔗 \[LinkedIn](https://www.linkedin.com/in/abhijeet-singh-a23a0a339)


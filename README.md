# Financial-Fraud-Detection

**📌 Overview**

This project focuses on detecting fraudulent financial transactions using a deep learning approach combined with explainable AI techniques. The model leverages a 1D Convolutional Neural Network (CNN) with an Attention Mechanism to capture complex patterns in transaction data, and uses LIME to explain individual predictions.

**🚀 Key Features**

🔍 Detects fraudulent transactions with high recall  
🧠 Uses 1D CNN for pattern extraction  
🎯 Incorporates Attention Mechanism for feature importance
📊 Provides Explainable AI (XAI) using LIME
⚖️ Handles severely imbalanced dataset effectively

**📊 Dataset**

Source: PaySim Dataset
Type: Synthetic financial transaction dataset
Transactions: ~6.3 million

**🔑 Features**

step – Time step
type – Transaction type
amount – Transaction amount
oldbalanceOrg, newbalanceOrig – Sender balances
oldbalanceDest, newbalanceDest – Receiver balances
isFraud – Target variable

**⚙️ Methodology**

🔹 Data Preprocessing
Removed irrelevant columns (nameOrig, nameDest)
Log transformation on amount
Feature engineering:
balance_diff_orig
balance_diff_dest
One-hot encoding for transaction type
Standard scaling
🔹 Handling Data Imbalance
Applied class weighting
Adjusted prediction threshold
Focused on Recall & F1-score instead of accuracy

**🧠 Model Architecture**

Input Layer
   ↓
Conv1D (32 filters) + MaxPooling
   ↓
Conv1D (64 filters) + MaxPooling
   ↓
Attention Layer
   ↓
Dense Layer (64 neurons) + Dropout
   ↓
Output Layer (Sigmoid)

**📈 Results**

Metric	Value
Accuracy	0.998
Precision	0.39
Recall	0.73
F1-score	0.51
ROC-AUC	0.98

**🎯 Key Insight**

The model prioritizes high recall, ensuring most fraud cases are detected even at the cost of some false positives.

**🔍 Explainability (LIME)**

Provides local explanations for each prediction
Identifies which features contributed most to fraud detection
Improves model transparency and trust

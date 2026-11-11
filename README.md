# Ransomware Detection Using Machine Learning & Deep Learning

## Project Overview

This project explores the application of Machine Learning and Deep Learning techniques to detect ransomware activity using memory-based features.

Using the CIC-MalMem-2022 dataset, the project analyses memory-related characteristics to distinguish between benign processes and ransomware activity.

Two classification approaches are implemented and compared:

- **Gradient Boosting** – A traditional Machine Learning approach using Histogram-based Gradient Boosting for binary classification.
- **Long Short-Term Memory (LSTM)** – A Deep Learning approach designed to learn patterns from preprocessed memory features.

The objective is to evaluate both approaches and understand their effectiveness in identifying ransomware-related activity.

## Technologies Used

- Python
- Pandas & NumPy
- Scikit-learn
- TensorFlow / Keras
- Matplotlib & Seaborn
- Hugging Face Datasets
- Google Colab

## Dataset

The project uses the **CIC-MalMem-2022 dataset**, which contains memory analysis data representing benign and malicious software activities.

Dataset source: [CIC-MalMem-2022 – Hugging Face](https://huggingface.co/datasets/bvk/CIC-MalMem-2022)

The dataset includes different malware categories, including:

- Benign
- Ransomware
- Spyware
- Trojan

For this project, the dataset is filtered to retain only:

- Benign samples
- Ransomware samples

The different ransomware variants are grouped into a single ransomware classification category.

## Project Workflow

### 1. Data Collection
- Download the CIC-MalMem-2022 dataset from Hugging Face.
- Load the dataset into a Pandas DataFrame.
- Inspect dataset dimensions and available features.

### 2. Data Filtering & Preparation
- Identify the category column.
- Filter benign and ransomware records.
- Convert the original categories into binary labels:
  - `0` – Benign
  - `1` – Ransomware
- Analyse the distribution of both classes.

### 3. Feature Engineering & Preprocessing
- Remove categorical text columns from the feature matrix.
- Exclude the classification label.
- Identify and remove zero-variance features.
- Extract numerical memory-related features.
- Apply StandardScaler to standardise the feature values.
- Split the dataset into training and testing sets using an 80:20 ratio.
- Apply stratified sampling to maintain class distribution.

### 4. Gradient Boosting Classification
- Implement HistGradientBoostingClassifier from Scikit-learn.
- Configure the model with 200 iterations.
- Train the classifier using the training dataset.
- Predict benign and ransomware activities.
- Evaluate classification performance.
- Generate a confusion matrix.

### 5. Feature Importance Analysis
- Attempt to extract the top 15 feature importance values.
- Check whether the selected Gradient Boosting implementation exposes feature importance directly.
- Provide an alternative using permutation importance if required.

### 6. Deep Learning – LSTM Model
- Reshape the numerical feature vectors into a sequence-like input format.
- Build an LSTM neural network using TensorFlow/Keras.
- Implement two LSTM layers with 64 and 32 units.
- Apply dropout for regularisation.
- Use a sigmoid activation function for binary classification.
- Compile the model using Adam optimiser and binary cross-entropy loss.

### 7. Model Training & Evaluation
- Train the LSTM model for up to 20 epochs.
- Use a validation split of 10%.
- Implement Early Stopping with a patience of 3 epochs.
- Restore the best model weights.
- Evaluate the model using a held-out test dataset.
- Visualise training and validation loss and accuracy.

### 8. Model Performance Comparison

Both approaches are evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix
- Classification Report
- ROC Curve
- Area Under the Curve (AUC)

A final comparison table and visualisation are generated to evaluate the performance of Gradient Boosting and LSTM models.

## How to Run

The notebook is designed to run in **Google Colab**.

1. Open the notebook in Google Colab.
2. Select Runtime → Change runtime type.
3. Select GPU (optional, recommended for LSTM training).
4. Run all cells from top to bottom.

The notebook automatically downloads the dataset from Hugging Face. No manual dataset upload is required.

## Repository Structure

```text
Ransomware-Detection-Using-Machine-Learning/
│
├── 4_Ransomware_Detection.ipynb
└── README.md
```

## Learning Outcomes

This project demonstrates practical implementation of:

- Ransomware detection concepts.
- Memory-based malware analysis.
- Binary classification for cybersecurity.
- Data preprocessing and feature engineering.
- Gradient Boosting classification.
- Deep Learning using LSTM.
- Model training and validation.
- Classification performance evaluation.
- Comparative analysis of Machine Learning and Deep Learning approaches.

## Disclaimer

This project is developed for educational and research purposes as part of cybersecurity studies. The models demonstrate ransomware classification using a publicly available memory analysis dataset. They are experimental and are not intended to replace production-grade Endpoint Detection and Response (EDR) or antivirus solutions.

---

**Project Area:** Cybersecurity | Malware Analysis | Ransomware Detection | Machine Learning | Deep Learning

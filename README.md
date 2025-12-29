# Gen AI E2 Fraud Detection Capstone Project

A comprehensive machine learning and generative AI solution for detecting fraudulent banking transactions. This project combines traditional machine learning models with Azure OpenAI integration to provide intelligent fraud detection and analysis.

## Project Overview

This capstone project demonstrates end-to-end fraud detection capabilities using:
- **Machine Learning Models**: Decision Trees, Random Forests, Gradient Boosting, and Logistic Regression
- **Embedding-based Detection**: Sentence transformers for semantic transaction analysis
- **Generative AI Integration**: Azure OpenAI for intelligent fraud investigation and reporting
- **Real-time Analysis**: Transaction classification with confidence scores and explanations

## Features

✨ **Dataset Generation**: Realistic banking transaction data generation with fraud patterns
- Multiple merchant categories (retail, utilities, restaurants, ATM, checks, P2P transfers)
- Realistic fraud probabilities based on merchant type and transaction amount
- Temporal patterns and customer behavior simulation

🤖 **Multiple ML Models**:
- Random Forest Classifier
- Decision Tree Classifier
- Gradient Boosting Classifier
- Logistic Regression
- Embedding-based Detection using Sentence Transformers

🔐 **Security & Authentication**:
- Azure OAuth2 integration for secure API access
- Environment variable configuration for sensitive credentials

🧠 **Generative AI Integration**:
- Azure OpenAI API integration for transaction analysis
- Intelligent fraud explanations and recommendations
- Natural language processing for investigation reports

📊 **Data Processing**:
- Advanced feature engineering (temporal, statistical, behavioral)
- Data normalization and scaling
- Feature importance analysis
- Model performance evaluation with multiple metrics

## Project Structure

```
├── banking_fraud_detection.ipynb    # Main analysis and model training notebook
├── generate_dataset.py              # Dataset generation script
├── azure_openai.py                  # Azure OpenAI integration utilities
├── requirements.txt                 # Project dependencies
├── data/
│   └── banking_transactions.json    # Generated transaction dataset
└── README.md                        # This file
```

## Installation

### Prerequisites
- Python 3.8 or higher
- pip package manager
- Azure OpenAI API credentials (optional, for Generative AI features)

### Setup

1. **Clone the repository**:
```bash
git clone https://github.com/manyu235/Gen-AI-E2-Fraud-Detection-Capstone-Project.git
cd "Gen AI E2-Fraud Detection System"
```

2. **Create a virtual environment**:
```bash
python -m venv venv
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

3. **Install dependencies**:
```bash
pip install -r requirements.txt
```

4. **Configure environment variables** (for Azure OpenAI integration):
Create a `.env` file in the project root:
```
AZURE_OPENAI_ENDPOINT=your_azure_endpoint
ACCESS_TOKEN_URL=your_token_url
CLIENT_ID=your_client_id
CLIENT_SECRET=your_client_secret
SCOPE=your_scope
GRANT_TYPE=client_credentials
```

## Usage

### 1. Generate Dataset
Generate realistic banking transaction data:
```bash
python generate_dataset.py
```
This creates `data/banking_transactions.json` with 1000+ transactions including fraud patterns.

### 2. Run Fraud Detection Analysis
Launch the Jupyter notebook for model training and evaluation:
```bash
jupyter notebook banking_fraud_detection.ipynb
```

The notebook includes:
- Data loading and preprocessing
- Exploratory Data Analysis (EDA)
- Feature engineering
- Model training with multiple algorithms
- Model evaluation and comparison
- Fraud case investigation using Generative AI
- Performance visualization

### 3. Azure OpenAI Integration
Use the Azure OpenAI utilities for transaction analysis:
```python
from azure_openai import azure_chat
result = await azure_chat("Analyze this suspicious transaction...")
```

## Key Technologies

- **Python 3.8+**: Core programming language
- **pandas**: Data manipulation and analysis
- **scikit-learn**: Machine learning algorithms and metrics
- **numpy**: Numerical computing
- **scipy**: Scientific computing
- **sentence-transformers**: Semantic embeddings for transactions
- **Azure OpenAI**: Generative AI integration
- **MSAL**: Microsoft authentication
- **Jupyter**: Interactive notebook environment

## Model Performance

The project evaluates multiple models:
- **Accuracy**: Overall correctness of predictions
- **Precision & Recall**: Balance between false positives and false negatives
- **F1-Score**: Harmonic mean of precision and recall
- **ROC-AUC**: Trade-off between true positive and false positive rates
- **Confusion Matrix**: Detailed performance breakdown

## Dataset Details

The synthetic dataset includes:
- **Transaction Amount**: Realistic ranges per merchant type
- **Merchant Category**: Retail, utilities, restaurants, ATM, checks, P2P transfers
- **Temporal Features**: Date, time, day of week
- **Fraud Labels**: Binary classification (fraud/legitimate)
- **Customer Behavior**: Consistent spending patterns with anomalies

Sample transaction structure:
```json
{
  "transaction_id": "TXN001",
  "merchant": "Walmart",
  "amount": 125.50,
  "category": "retail",
  "timestamp": "2024-01-15T14:30:00",
  "is_fraud": false,
  "customer_id": "CUST001"
}
```

## Feature Engineering

The notebook implements advanced features:
- **Temporal**: Hour of day, day of week, time since last transaction
- **Statistical**: Transaction amount percentiles, standard deviation
- **Behavioral**: Average spending by category, frequency anomalies
- **Categorical**: Merchant type encoding, location patterns
- **Distance-based**: Similarity embeddings using Sentence Transformers

## Investigation & Reporting

The project leverages Azure OpenAI for:
- Detailed fraud case investigation
- Natural language explanations of suspicious transactions
- Recommended actions for fraud prevention
- Pattern analysis and trend identification

## Evaluation Metrics

- **Accuracy**: Overall correctness
- **Precision**: True positives / (True positives + False positives)
- **Recall**: True positives / (True positives + False negatives)
- **F1-Score**: 2 × (Precision × Recall) / (Precision + Recall)
- **ROC-AUC**: Area under the receiver operating characteristic curve

## Future Enhancements

- Real-time fraud detection API
- Deep learning models (Neural Networks)
- Time series anomaly detection
- Graph neural networks for transaction networks
- Automated fraud alert system
- Model retraining pipeline

## Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs and feature requests.

## License

This project is provided as-is for educational and capstone purposes.

## Contact & Support

For questions or support regarding this project, please reach out to the project maintainer or open an issue on GitHub.

---

**Repository**: [Gen-AI-E2-Fraud-Detection-Capstone-Project](https://github.com/manyu235/Gen-AI-E2-Fraud-Detection-Capstone-Project)

**Last Updated**: December 2025

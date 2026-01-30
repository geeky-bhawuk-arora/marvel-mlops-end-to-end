# Marvelous MLOps: End-to-End MLOps with Databricks

A complete end-to-end Machine Learning Operations (MLOps) pipeline for Marvel character data, demonstrating best practices in ML model development, deployment, and monitoring using Databricks.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Setup & Installation](#setup--installation)
- [Scripts Overview](#scripts-overview)
- [Technologies Used](#technologies-used)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This project showcases a production-ready MLOps workflow using the Marvel Characters dataset. It demonstrates the complete machine learning lifecycle from data preprocessing to model deployment and monitoring on the Databricks platform. This repository serves as both a learning resource and a template for implementing MLOps best practices in real-world scenarios.

**Key Learning Areas:**
- Data preprocessing and feature engineering
- Model training and registration
- Automated deployment pipelines
- Model monitoring and performance tracking
- CI/CD integration with GitHub Actions
- Databricks serverless computing

## ✨ Features

- **Complete MLOps Pipeline**: End-to-end workflow from data ingestion to model serving
- **Databricks Integration**: Leverages Databricks serverless capabilities (version 3)
- **Automated Testing**: Integration tests with GitHub status updates
- **Model Monitoring**: Real-time monitoring dashboards and refresh mechanisms
- **Feature Engineering**: Advanced feature engineering pipeline for Marvel character attributes
- **Scalable Architecture**: Built on modern MLOps tools and best practices
- **Version Control**: Comprehensive versioning for data, models, and code
- **Production-Ready**: Deployment to Databricks model serving endpoints

## 📊 Dataset

### Marvel Characters Dataset

This project uses the **[Marvel Characters Dataset](https://www.kaggle.com/datasets/mohitbansal31s/marvel-characters?resource=download)** from Kaggle.

**Dataset Details:**
- **Source**: Kaggle
- **Content**: Detailed information about Marvel comic book characters
- **Features Include**:
  - Character names
  - Superpowers and abilities
  - Physical attributes (height, weight, etc.)
  - Alignment (hero, villain, neutral)
  - Origin stories
  - Marital status
  - Gender and identity
  - Appearance counts

**Use Cases:**
- Character attribute prediction
- Classification models (hero vs. villain)
- Feature engineering for character status prediction
- Mutant detection based on origin stories
- Character clustering and similarity analysis

## 📁 Project Structure

```
marvel-characters/
├── .github/
│   └── workflows/          # GitHub Actions CI/CD workflows
├── data/                   # Dataset storage
├── demo_artifacts/         # Demo outputs and artifacts
├── notebooks/              # Jupyter notebooks for exploration
├── resources/              # Additional project resources
├── scripts/                # Main MLOps pipeline scripts
│   ├── 01.process_data.py
│   ├── 02.train_register_fe_model.py
│   ├── 03.deploy_model.py
│   ├── 04.post_commit_status.py
│   └── 05.refresh_monitor.py
├── src/
│   └── marvel_characters/  # Source code modules
│       ├── data_processor.py
│       └── [other modules]
├── tests/                  # Unit and integration tests
├── .gitignore
├── .pre-commit-config.yaml # Pre-commit hooks configuration
├── databricks.yml          # Databricks configuration
├── project_config_marvel.yml # Project-specific configuration
├── pyproject.toml          # Python project dependencies
├── uv.lock                 # UV lock file
├── version.txt             # Version tracking
└── README.md
```

## 🚀 Setup & Installation

### Prerequisites

- Python 3.8+
- Databricks account with serverless capabilities
- UV package manager ([installation guide](https://docs.astral.sh/uv/getting-started/installation/))
- Git for version control
- Kaggle account (for dataset access)

### Environment Setup

This project uses **UV** for fast, reliable Python package management.

1. **Install UV** (if not already installed):
   ```bash
   # macOS/Linux
   curl -LsSf https://astral.sh/uv/install.sh | sh
   
   # Windows
   powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
   ```

2. **Clone the repository**:
   ```bash
   git clone https://github.com/marvelousmlops/marvel-characters.git
   cd marvel-characters
   ```

3. **Create and activate the environment**:
   ```bash
   uv sync --extra dev
   ```
   
   This command will:
   - Create a new virtual environment
   - Install all dependencies from `pyproject.toml`
   - Install development dependencies
   - Generate a lockfile (`uv.lock`)

4. **Download the dataset**:
   - Visit [Kaggle Marvel Characters Dataset](https://www.kaggle.com/datasets/mohitbansal31s/marvel-characters?resource=download)
   - Download and place in the `data/` directory

5. **Configure Databricks**:
   - Update `databricks.yml` with your workspace details
   - Configure `project_config_marvel.yml` with your specific settings

## 📝 Scripts Overview

### 1. **Data Processing** (`01.process_data.py`)

**Purpose**: Initial data preprocessing and preparation

**Key Functions**:
- Loads the Marvel characters dataset
- Performs data cleaning and validation
- Handles missing values and outliers
- Creates train/test splits (80/20)
- Saves processed data to Databricks catalog

**Data Transformations**:
- Gender normalization (Male, Female, Other)
- Marital status filtering
- Mutant feature extraction from origin stories
- Physical attribute validation

### 2. **Model Training & Registration** (`02.train_register_fe_model.py`)

**Purpose**: Feature engineering and model training pipeline

**Key Functions**:
- Advanced feature engineering on Marvel character data
- Model training with hyperparameter optimization
- Model evaluation and validation
- Model registration to MLflow registry
- Feature importance analysis

**Features Created**:
- Encoded categorical variables
- Scaled numerical features
- Derived mutant indicator
- Interaction features

### 3. **Model Deployment** (`03.deploy_model.py`)

**Purpose**: Automated model deployment to production

**Key Functions**:
- Deploys trained model to Databricks model serving endpoint
- Configures serving infrastructure
- Sets up model versioning
- Validates deployment health
- Enables real-time inference API

**Deployment Modes**:
- Serverless endpoints
- Auto-scaling configuration
- Traffic splitting for A/B testing

### 4. **GitHub Integration** (`04.post_commit_status.py`)

**Purpose**: CI/CD pipeline integration

**Key Functions**:
- Posts integration test results to GitHub
- Updates commit status checks
- Provides deployment feedback
- Enables automated workflows

**Status Updates**:
- Success/failure notifications
- Test coverage reports
- Deployment confirmations

### 5. **Monitoring & Refresh** (`05.refresh_monitor.py`)

**Purpose**: Model performance monitoring and dashboard updates

**Key Functions**:
- Refreshes monitoring tables
- Updates performance dashboards
- Tracks model drift
- Monitors data quality
- Generates alerts for anomalies

**Monitoring Metrics**:
- Prediction accuracy
- Latency measurements
- Input data distribution
- Feature drift detection

## 🛠️ Technologies Used

### Core Technologies
- **Python 3.8+**: Primary programming language
- **Databricks**: Unified analytics platform
- **MLflow**: Experiment tracking and model registry
- **UV**: Fast Python package manager

### ML/Data Science
- **pandas**: Data manipulation and analysis
- **scikit-learn**: Machine learning algorithms
- **NumPy**: Numerical computing
- **PySpark**: Distributed data processing

### MLOps Tools
- **Databricks Feature Store**: Feature management
- **Databricks Model Serving**: Real-time inference
- **GitHub Actions**: CI/CD automation
- **pre-commit**: Code quality hooks

### Monitoring & Visualization
- **Databricks Dashboards**: Monitoring visualization
- **MLflow UI**: Experiment tracking interface

## 📈 Usage Examples

### Running the Complete Pipeline

```bash
# 1. Process and prepare data
python scripts/01.process_data.py

# 2. Train and register model
python scripts/02.train_register_fe_model.py

# 3. Deploy to production
python scripts/03.deploy_model.py

# 4. Update GitHub status
python scripts/04.post_commit_status.py

# 5. Refresh monitoring
python scripts/05.refresh_monitor.py
```

### Configuration

Edit `project_config_marvel.yml` to customize:
- Data paths
- Model parameters
- Deployment settings
- Monitoring thresholds

## 🧪 Testing

The project includes comprehensive testing:

```bash
# Run all tests
pytest tests/

# Run with coverage
pytest tests/ --cov=src/marvel_characters
```

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Pre-commit Hooks

This project uses pre-commit hooks for code quality:

```bash
# Install pre-commit hooks
pre-commit install

# Run manually
pre-commit run --all-files
```

## 📄 License

This project is part of the Marvelous MLOps educational initiative. Please refer to the repository for specific license information.

## 🌟 Acknowledgments

- **Dataset**: Marvel Characters Dataset from Kaggle
- **Platform**: Databricks for serverless ML infrastructure
- **Community**: Open-source MLOps community for best practices

## 📞 Contact & Resources

- **Repository**: [marvelousmlops/marvel-characters](https://github.com/marvelousmlops/marvel-characters)
- **Organization**: [Marvelous MLOps](https://github.com/marvelousmlops)
- **Databricks Documentation**: [Serverless Documentation](https://docs.databricks.com/aws/en/release-notes/serverless/environment-version/three)
- **UV Documentation**: [UV Getting Started](https://docs.astral.sh/uv/getting-started/installation/)

## 🎓 Learning Resources

This project is designed as a learning resource for:
- Data Scientists transitioning to MLOps
- ML Engineers building production pipelines
- Students learning end-to-end ML workflows
- Teams implementing Databricks best practices

---

**Built with ❤️ by the Marvelous MLOps community**

*Data provided by Marvel. © Marvel*

# Valencia Airbnb Price Prediction

## ML Course Project

### Project Overview

This project implements a comprehensive machine learning pipeline to predict Airbnb apartment prices in Valencia, Spain. The project demonstrates multiple ML techniques covered in class, with a focus on comparing model performance and training times, leveraging GPU acceleration where applicable.

### Objective

Predict the nightly price of Airbnb listings in Valencia using property characteristics, location, amenities, and host information.

### Methods Implemented

1. **Regularized Generalized Linear Models**
   - Ridge Regression (L2 regularization)
   - Lasso Regression (L1 regularization with feature selection)
   - ElasticNet (Combined L1 + L2)

2. **Regression and Classification Trees**
   - Decision Tree Regressor with hyperparameter tuning

3. **Ensemble Methods: Bagging and Random Forests**
   - Bagging Regressor
   - Random Forest (multiple complexity levels)

4. **Ensemble Methods: Boosting**
   - XGBoost (with GPU acceleration)
   - LightGBM (with GPU acceleration)

5. **Deep Learning**
   - Neural Networks with PyTorch (CUDA-enabled)
   - Multiple architectures (small, medium, large)

### Key Features

- **GPU Acceleration**: Leverages CUDA for XGBoost, LightGBM, and PyTorch models
- **Training Time Analysis**: Compares training times across different model complexities
- **Comprehensive EDA**: Interactive visualizations using Plotly and Seaborn
- **Hyperparameter Tuning**: Grid search for optimal model parameters
- **Performance Metrics**: R², RMSE, MAE for all models
- **Reproducible Environment**: Docker + devcontainer setup with CUDA support

### Dataset

- **Source**: Inside Airbnb (http://insideairbnb.com/)
- **Location**: Valencia, Spain
- **Date**: September 2024
- **Size**: ~6,000 listings with 75+ features

### Results

The project provides:
- Detailed comparison of 14+ different models
- Performance vs. training time trade-off analysis
- Feature importance analysis
- Interactive visualizations
- Model recommendations for different use cases

### Repository Structure

```
.
├── .devcontainer/                  # VS Code devcontainer configuration
├── data/                           # Data directory (auto-downloaded)
│   └── README.md
├── installation/
│   └── docker-amd64-cuda/          # Docker setup with CUDA support
│       └── requirements.txt        # Python dependencies (updated)
├── notebooks/
│   └── valencia_airbnb_price_prediction.ipynb  # Main analysis notebook
├── outputs/                        # Results and saved models
└── src/                            # Source code (template structure)
```

### Getting Started

#### Prerequisites

- Docker with NVIDIA Container Toolkit (for GPU support)
- CUDA-capable GPU (recommended, but not required)
- VS Code with Remote-Containers extension (optional)

#### Quick Start

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd python-ml-research-template
   ```

2. **Open in devcontainer** (VS Code):
   - Open the repository in VS Code
   - Click "Reopen in Container" when prompted
   - Wait for the container to build (first time only)

3. **Run the notebook**:
   - Open `notebooks/valencia_airbnb_price_prediction.ipynb`
   - Run all cells to execute the complete analysis

#### Alternative: Docker Compose

```bash
cd installation/docker-amd64-cuda
./template.sh build_generic
./template.sh dev -e JUPYTER_SERVER=1 -e JUPYTER_PORT=8888
# Access Jupyter at http://localhost:8888
```

### Environment Details

- **Base Image**: NVIDIA PyTorch 24.07 (PyTorch 2.4, CUDA 12.5, Python 3.10)
- **Key Libraries**:
  - Data: pandas, numpy, scipy
  - Visualization: matplotlib, seaborn, plotly
  - ML: scikit-learn, xgboost, lightgbm
  - Deep Learning: PyTorch (with CUDA)
  - Hyperparameter Optimization: optuna
  - Interpretability: shap

### Performance Highlights

The project demonstrates:
- **GPU Speedup**: 5-10x faster training for boosting methods with CUDA
- **Best Accuracy**: Ensemble methods (R² > 0.70)
- **Fastest Training**: Linear models (< 1 second)
- **Best Trade-off**: XGBoost or LightGBM with GPU

### Future Enhancements

1. **Advanced Feature Engineering**:
   - NLP on listing descriptions
   - Temporal features (seasonality)
   - Neighborhood statistics

2. **Model Improvements**:
   - Automated hyperparameter optimization with Optuna
   - Model stacking and blending
   - Time-series forecasting

3. **Deployment**:
   - REST API for predictions
   - Interactive web dashboard
   - Model monitoring pipeline

### License

This project is licensed under the MIT License - see the LICENSE file for details.

### Acknowledgments

- Inside Airbnb for providing public dataset
- NVIDIA for PyTorch NGC container
- Python ML Research Template for repository structure

### Author

ML Course Student
Date: November 2025

### Citation

If you use this project or dataset, please cite:
```bibtex
@misc{valencia_airbnb_ml,
  title={Valencia Airbnb Price Prediction: A Comparative ML Study},
  author={ML Course Student},
  year={2025},
  url={<repository-url>}
}
```

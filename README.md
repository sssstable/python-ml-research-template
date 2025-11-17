# Valencia Airbnb Price Prediction

## ML Course Project - Simple Setup

Predicting Airbnb apartment prices in Valencia using multiple ML techniques with comprehensive performance comparison.

---

## 🚀 Quick Start (5 Minutes)

### Prerequisites

- [Anaconda](https://www.anaconda.com/download) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html)
- Git

### Setup

```bash
# 1. Clone the repository
git clone https://github.com/sssstable/python-ml-research-template.git
cd python-ml-research-template
git checkout claude/airbnb-price-prediction-01NRkeHLF3zbYMHDMj2YVs2x

# 2. Create conda environment (takes ~5 minutes)
conda env create -f environment.yml

# 3. Activate environment
conda activate airbnb-ml

# 4. Install the project
pip install -e .

# 5. Start Jupyter
jupyter lab

# 6. Open and run the notebook
# Navigate to: notebooks/valencia_airbnb_price_prediction.ipynb
# Click "Run All" or run cells individually
```

That's it! 🎉

---

## 📦 What's Installed

The environment includes:
- **Python 3.10**
- **Data Science**: pandas, numpy, scipy
- **Visualization**: matplotlib, seaborn, plotly
- **ML Core**: scikit-learn
- **Ensemble Methods**: XGBoost, LightGBM
- **Deep Learning**: PyTorch (CPU version)
- **Jupyter**: Full JupyterLab setup
- **Utilities**: Hydra, W&B, SHAP, Optuna

---

## 🎯 GPU Support (Optional)

If you have an NVIDIA GPU and want faster training:

### For CUDA 11.8:
```bash
conda activate airbnb-ml
pip install torch torchvision --index-url https://download.pytorch.org/whl/cu118
```

### For CUDA 12.1:
```bash
conda activate airbnb-ml
pip install torch torchvision --index-url https://download.pytorch.org/whl/cu121
```

### Verify GPU:
```bash
python -c "import torch; print(f'CUDA available: {torch.cuda.is_available()}')"
```

GPU will speed up:
- XGBoost: ~5-10x faster
- LightGBM: ~5-10x faster
- Neural Networks: ~5-10x faster

**But CPU works fine** - total notebook runtime is ~15-20 mins on CPU.

---

## 📊 Running the Notebook

### Option 1: JupyterLab (Recommended)
```bash
conda activate airbnb-ml
jupyter lab
# Open: notebooks/valencia_airbnb_price_prediction.ipynb
```

### Option 2: Jupyter Notebook
```bash
conda activate airbnb-ml
jupyter notebook notebooks/valencia_airbnb_price_prediction.ipynb
```

### Option 3: In Cursor/VS Code
```bash
# Open the project folder in Cursor
cursor .

# Select the conda environment:
# 1. Open the notebook
# 2. Click kernel selector (top right)
# 3. Choose "airbnb-ml" environment
# 4. Run cells!
```

---

## 🔬 What the Notebook Does

1. **Downloads Data**: Valencia Airbnb listings (~6,000 properties)
2. **Explores Data**: Interactive maps, distributions, correlations
3. **Engineers Features**: 25+ features from property, location, reviews
4. **Trains 14+ Models**:
   - Linear Models (Ridge, Lasso, ElasticNet)
   - Decision Trees
   - Ensemble Methods (Bagging, Random Forest)
   - Gradient Boosting (XGBoost, LightGBM)
   - Neural Networks (PyTorch)
5. **Compares Performance**: R², RMSE, MAE, training times
6. **Visualizes Results**: Interactive plots and comparisons

**Total Runtime**:
- CPU: ~15-20 minutes
- GPU: ~8-10 minutes

---

## 📁 Project Structure

```
.
├── environment.yml              # Conda environment specification
├── notebooks/
│   └── valencia_airbnb_price_prediction.ipynb  # Main analysis
├── data/                        # Auto-downloaded on first run
├── outputs/                     # Results and metrics
├── src/                         # Source code (template structure)
└── installation/                # Docker setup (optional, ignore)
```

---

## 🛠️ Troubleshooting

### Environment creation fails?
```bash
# Try with mamba (faster)
conda install -c conda-forge mamba
mamba env create -f environment.yml
```

### Package conflicts?
```bash
# Remove and recreate
conda env remove -n airbnb-ml
conda env create -f environment.yml
```

### Kernel not showing in Jupyter?
```bash
conda activate airbnb-ml
python -m ipykernel install --user --name airbnb-ml --display-name "Python (airbnb-ml)"
```

### Out of memory?
- Reduce batch sizes in neural network sections
- Close other applications
- Or just run on CPU (models will work, just slower)

---

## 🔄 Updating the Environment

If you need to add packages later:

```bash
conda activate airbnb-ml

# Add conda package
conda install <package-name>

# Or pip package
pip install <package-name>

# Update environment.yml to keep it reproducible
conda env export > environment.yml
```

---

## 🎓 Course Requirements Fulfilled

✅ **Select a dataset**: Valencia Airbnb (Inside Airbnb)
✅ **Application context**: Documented in notebook
✅ **Exploratory analysis**: Interactive visualizations
✅ **Pre-processing**: Feature engineering + variable selection
✅ **3+ Methods**: 5 method categories, 14+ models total:
   - Regularized linear models (Ridge, Lasso, ElasticNet)
   - Regression trees (Decision Tree)
   - Ensemble - Bagging (Bagging, Random Forest)
   - Ensemble - Boosting (XGBoost, LightGBM)
   - Deep Learning (Neural Networks with PyTorch)
✅ **Hyperparameter tuning**: GridSearchCV for all applicable models
✅ **Visual feedback**: All results visualized with plots and tables

---

## 🆘 Need Help?

**Common Questions:**

- **Where's the data?** Auto-downloads on first run (10MB)
- **How long does it take?** 15-20 mins on CPU, 8-10 mins with GPU
- **Do I need GPU?** No, CPU works fine (just slower)
- **Can I modify the notebook?** Yes! Experiment freely
- **Cursor specific setup?** Just select the `airbnb-ml` kernel

---

## 📄 Additional Documentation

- **PROJECT_DESCRIPTION.md**: Detailed project overview
- **QUICKSTART.md**: Ultra-fast copy-paste setup
- **data/README.md**: Dataset documentation
- **outputs/README.md**: Results structure

---

## 📜 License

MIT License - See LICENSE file

---

## 🎯 Ready to Run?

```bash
conda activate airbnb-ml
jupyter lab
# Open: notebooks/valencia_airbnb_price_prediction.ipynb
# Click: "Run All"
# Watch the magic happen! ✨
```

Enjoy! 🚀

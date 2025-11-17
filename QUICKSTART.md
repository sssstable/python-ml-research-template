# Quick Setup Guide

## TL;DR

```bash
# 1. Clone
git clone https://github.com/sssstable/python-ml-research-template.git
cd python-ml-research-template
git checkout claude/airbnb-price-prediction-01NRkeHLF3zbYMHDMj2YVs2x

# 2. Setup environment
conda env create -f environment.yml
conda activate airbnb-ml
pip install -e .

# 3. Run
jupyter lab
# Open: notebooks/valencia_airbnb_price_prediction.ipynb
```

## Step-by-Step

### 1. Install Conda (if needed)

Download from: https://www.anaconda.com/download

Or use Miniconda (smaller): https://docs.conda.io/en/latest/miniconda.html

### 2. Clone Repository

```bash
cd ~/qfin-sml/  # Or wherever you want it
git clone https://github.com/sssstable/python-ml-research-template.git
cd python-ml-research-template
git checkout claude/airbnb-price-prediction-01NRkeHLF3zbYMHDMj2YVs2x
```

### 3. Create Environment

```bash
conda env create -f environment.yml
```

This takes ~5 minutes and installs everything you need.

### 4. Activate Environment

```bash
conda activate airbnb-ml
```

You should see `(airbnb-ml)` in your terminal prompt.

### 5. Install Project

```bash
pip install -e .
```

### 6. Launch Jupyter

```bash
jupyter lab
```

Your browser will open automatically.

### 7. Open Notebook

In JupyterLab:
- Navigate to `notebooks/`
- Click `valencia_airbnb_price_prediction.ipynb`
- Click "Run All" (or run cells one by one)

### 8. Wait for Results

- First cell downloads data (~10 MB)
- Total runtime: ~15-20 minutes on CPU
- All results appear inline with interactive visualizations

## Using with Cursor

```bash
# Open project in Cursor
cd ~/qfin-sml/python-ml-research-template
cursor .

# In Cursor:
# 1. Open the notebook
# 2. Click kernel selector (top right)
# 3. Choose "Python (airbnb-ml)" or "airbnb-ml"
# 4. Run cells!
```

## Verify Setup

Test everything works:

```bash
conda activate airbnb-ml
python -c "import torch, pandas, sklearn, xgboost, lightgbm; print('✅ All packages installed!')"
```

## GPU Support (Optional)

If you have NVIDIA GPU:

```bash
conda activate airbnb-ml
pip install torch torchvision --index-url https://download.pytorch.org/whl/cu121

# Test
python -c "import torch; print(f'CUDA: {torch.cuda.is_available()}')"
```

## Need Help?

See full README.md for troubleshooting and detailed information.

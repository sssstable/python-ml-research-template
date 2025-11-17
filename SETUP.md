# Setup Instructions

## Quick Setup (Choose One Method)

### Method 1: Conda (Recommended for ML)

```bash
# Install Miniconda (if not installed)
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh -b -p $HOME/miniconda3
echo 'export PATH="$HOME/miniconda3/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

# Setup project
conda env create -f environment.yml
conda activate airbnb-ml
pip install -e .

# Run
jupyter lab
```

### Method 2: Python venv (Simpler, No Conda)

```bash
# Create virtual environment
python3 -m venv venv
source venv/bin/activate  # Linux/Mac
# OR: venv\Scripts\activate  # Windows

# Install dependencies
pip install -r installation/docker-amd64-cuda/requirements.txt
pip install -e .

# Run
jupyter lab
```

## Opening the Notebook

1. Start Jupyter:
   ```bash
   jupyter lab
   # OR
   jupyter notebook
   ```

2. Navigate to: `notebooks/valencia_airbnb_price_prediction.ipynb`

3. Click "Run All" or run cells one by one

## In Cursor/VS Code

```bash
# Open project
cursor .

# Select Python interpreter:
# - Conda: Choose "airbnb-ml" environment
# - venv: Choose "venv/bin/python"

# Open notebook and run!
```

## GPU Support (Optional)

After setup, if you have NVIDIA GPU:

```bash
# Activate your environment first
conda activate airbnb-ml  # OR: source venv/bin/activate

# Install CUDA-enabled PyTorch
pip install torch torchvision --index-url https://download.pytorch.org/whl/cu121

# Verify
python -c "import torch; print(torch.cuda.is_available())"
```

## Troubleshooting

**Jupyter kernel not found?**
```bash
# Conda
conda activate airbnb-ml
python -m ipykernel install --user --name airbnb-ml

# venv
source venv/bin/activate
python -m ipykernel install --user --name venv
```

**Package conflicts?**
```bash
# Conda: recreate environment
conda env remove -n airbnb-ml
conda env create -f environment.yml

# venv: recreate environment
rm -rf venv
python3 -m venv venv
source venv/bin/activate
pip install -r installation/docker-amd64-cuda/requirements.txt
```

**Out of memory?**
- Close other applications
- Reduce batch sizes in neural network cells
- CPU is totally fine for this project!

## What You'll Get

- ✅ 6,000+ Airbnb listings from Valencia
- ✅ 14+ trained ML models
- ✅ Interactive visualizations
- ✅ Complete performance comparison
- ✅ Training time analysis
- ✅ All results in ~15-20 minutes (CPU)

Happy coding! 🚀

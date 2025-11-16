# How to Run the Valencia Airbnb Price Prediction Notebook

## Quick Start Guide

### Option 1: VS Code Devcontainer (Recommended)

This is the easiest way to get started with full GPU support.

1. **Prerequisites**:
   - Docker Desktop with NVIDIA Container Toolkit
   - VS Code with Remote-Containers extension
   - NVIDIA GPU with CUDA support (optional but recommended)

2. **Steps**:
   ```bash
   # Clone the repository
   git clone <your-repo-url>
   cd python-ml-research-template

   # Open in VS Code
   code .
   ```

3. **In VS Code**:
   - Click "Reopen in Container" when prompted
   - Wait for the container to build (first time: ~10-15 minutes)
   - Open `notebooks/valencia_airbnb_price_prediction.ipynb`
   - Click "Run All" or execute cells one by one

### Option 2: Docker Compose with Jupyter Lab

1. **Build the environment**:
   ```bash
   cd installation/docker-amd64-cuda
   ./template.sh build_generic
   ```

2. **Start Jupyter Lab**:
   ```bash
   ./template.sh dev -d -e JUPYTER_SERVER=1 -e JUPYTER_PORT=8888
   ```

3. **Get the Jupyter token**:
   ```bash
   docker logs <container-id>
   # Look for: http://hostname:8888/?token=<TOKEN>
   ```

4. **Open in browser**:
   - Navigate to `http://localhost:8888/?token=<TOKEN>`
   - Open `notebooks/valencia_airbnb_price_prediction.ipynb`
   - Run the notebook

### Option 3: Local Jupyter (if environment is already set up)

```bash
# Install dependencies
pip install -r installation/docker-amd64-cuda/requirements.txt

# Install the project
pip install -e .

# Start Jupyter
jupyter lab notebooks/valencia_airbnb_price_prediction.ipynb
```

## What to Expect

### Execution Time

Total execution time varies based on hardware:

- **With GPU**: ~10-15 minutes
- **Without GPU**: ~20-30 minutes

### Data Download

The notebook will automatically download:
- Valencia Airbnb listings (~10 MB compressed)
- This happens on first run only

### Outputs

The notebook generates:
- Interactive visualizations (inline)
- Model comparison tables
- Results CSV files in `outputs/`

## GPU Acceleration

The notebook automatically detects and uses GPU if available:

- **XGBoost**: Uses CUDA if available
- **LightGBM**: Uses CUDA if available
- **PyTorch Neural Networks**: Uses CUDA if available

Without GPU, all models run on CPU (slower but still functional).

### Check GPU Availability

The notebook includes cells to check CUDA:
```python
import torch
print(f"CUDA available: {torch.cuda.is_available()}")
print(f"GPU Device: {torch.cuda.get_device_name(0)}")
```

## Troubleshooting

### Container Build Fails

```bash
# Clean Docker cache
docker system prune -a

# Rebuild
cd installation/docker-amd64-cuda
./template.sh build_generic
```

### Jupyter Kernel Dies

Increase Docker memory allocation:
- Docker Desktop → Settings → Resources → Memory (set to 8GB+)

### CUDA Out of Memory

Reduce batch sizes in the notebook:
```python
# In neural network training cell
train_loader = DataLoader(train_dataset, batch_size=64, shuffle=True)  # Reduce from 128
```

### Package Installation Issues

```bash
# Inside the container
pip install --upgrade pip
pip install -r installation/docker-amd64-cuda/requirements.txt
```

## Running Specific Sections

You can run only parts of the notebook:

- **EDA Only**: Run sections 1-3
- **Quick Models**: Skip the large neural networks (sections 12-14)
- **GPU Models Only**: Run sections 9-14

## Next Steps

After running the notebook:

1. **Explore Results**: Check `outputs/model_comparison_results.csv`
2. **Modify Models**: Try different hyperparameters
3. **Add Features**: Extend the feature engineering section
4. **Deploy**: Use the best model for predictions

## Additional Resources

- [Docker Documentation](https://docs.docker.com/)
- [VS Code Remote Containers](https://code.visualstudio.com/docs/remote/containers)
- [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html)
- [Inside Airbnb Data](http://insideairbnb.com/)

## Support

For issues specific to this project, check:
- `PROJECT_DESCRIPTION.md` for project overview
- `installation/docker-amd64-cuda/README.md` for detailed Docker setup
- `.devcontainer/devcontainer.json` for devcontainer configuration

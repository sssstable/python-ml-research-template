# Devcontainer Configurations

This project includes two devcontainer configurations:

## 1. Default (CPU-only) - `devcontainer.json`
**Use this if you're having GPU/NVIDIA Docker issues or want to get started quickly.**

- Runs all models on CPU
- No GPU dependencies required
- Slower training times but fully functional
- Automatically selected by default

## 2. GPU-enabled - `devcontainer-gpu.json`
**Use this once you have NVIDIA Container Toolkit properly configured.**

- Enables CUDA acceleration for XGBoost, LightGBM, and PyTorch
- Requires NVIDIA GPU + drivers + NVIDIA Container Toolkit
- Significantly faster training times
- Must manually select this configuration

## How to Switch Between Configurations

### In Cursor/VS Code:

**To use CPU-only (default)**:
- Just open the folder - it will use `devcontainer.json` automatically

**To use GPU**:
1. Rename files:
   ```bash
   mv .devcontainer/devcontainer.json .devcontainer/devcontainer-cpu.json
   mv .devcontainer/devcontainer-gpu.json .devcontainer/devcontainer.json
   ```
2. Rebuild container: `Cmd/Ctrl+Shift+P` → "Dev Containers: Rebuild Container"

## Testing GPU Support

Before using the GPU configuration, verify your setup:

```bash
# Test 1: Check NVIDIA drivers
nvidia-smi

# Test 2: Check Docker can access GPU
docker run --rm --gpus all nvidia/cuda:11.8.0-base-ubuntu22.04 nvidia-smi

# Test 3: Check NVIDIA Container Toolkit
docker run --rm --gpus all nvcr.io/nvidia/pytorch:24.07-py3 python -c "import torch; print(torch.cuda.is_available())"
```

If all three pass, you can use the GPU configuration!

## Installing NVIDIA Container Toolkit

If GPU tests fail, install the toolkit:

```bash
# Ubuntu/Debian
distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list

sudo apt-get update
sudo apt-get install -y nvidia-container-toolkit
sudo systemctl restart docker

# Verify
docker run --rm --gpus all nvidia/cuda:11.8.0-base-ubuntu22.04 nvidia-smi
```

## Performance Comparison

| Configuration | XGBoost (500 trees) | Neural Network (100 epochs) |
|---------------|---------------------|------------------------------|
| CPU-only      | ~60-90 seconds      | ~120-180 seconds             |
| GPU-enabled   | ~8-15 seconds       | ~20-40 seconds               |

The notebook will run fine on CPU, just slower. GPU is optional but recommended for the full experience.

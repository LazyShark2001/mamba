# mamba
## Requirements

```python
conda create -n mamba python=3.11
conda activate mamba
conda install cuda-toolkit=12.1 -c nvidia # maybe
pip install torch==2.2.0 torchvision==0.17.0 torchaudio==2.2.0 --index-url https://download.pytorch.org/whl/cu121
conda install cuda-nvcc=12.1 -c nvidia  # maybe
pip install causal-conv1d
pip install mamba-ssm
```
- If there is no response when installing causal-conv1d and mamba-ssm, please download the local package and decompress it directly. If downloading the whl file fails, please download and install it manually.
- When installing these two packages, a dependency of about 100MB and 300MB is downloaded by default, but it's difficult to download this dependency. So, I manually downloaded the tar.gz files for installation. However, it then reported an error saying that the whl file was missing, so I manually downloaded the whl file for installation.

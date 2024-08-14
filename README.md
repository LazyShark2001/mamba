# mamba
## Requirements

```python
conda create -n mamba python=3.11
conda activate mamba
conda install cudatoolkit==12.1 -c nvidia
pip install torch==2.2.0 torchvision==0.17.0 torchaudio==2.2.0 --index-url https://download.pytorch.org/whl/cu121
conda install cuda-nvcc=11.8 -c nvidia  # maybe
pip install causal-conv1d
pip install mamba-ssm
```
- If there is no response when installing causal-conv1d and mamba-ssm, please download the local package and decompress it directly. If downloading the whl file fails, please download and install it manually.

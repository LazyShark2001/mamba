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


- causal_conv1d
- http://mirrors.aliyun.com/pypi/packages/3f/28/c21f5059837c6426c0e15eaf7ada62febe00ccc3f23a4f6b3b9029bbdf8a/causal_conv1d-1.4.0.tar.gz
- https://github.com/Dao-AILab/causal-conv1d/releases/download/v1.4.0/causal_conv1d-1.4.0+cu122torch2.3cxx11abiFALSE-cp311-cp311-linux_x86_64.whl
- mamba_ssm
- http://mirrors.aliyun.com/pypi/packages/f7/80/69bc14816fda4b30be3ac724e3efc713969dd545cd0bcb35abee6b8dfbf9/mamba_ssm-2.2.2.tar.gz
- https://github.com/state-spaces/mamba/releases/download/v2.2.2/mamba_ssm-2.2.2+cu122torch2.3cxx11abiFALSE-cp311-cp311-linux_x86_64.whl

When installing selective_scan, it is important to pay attention to the CUDA_HOME parameter. By default, this parameter is set to /usr/local/cuda in the code. If it is not, you can modify it through the following code:
```python
export CUDA_HOME=/usr/local/cuda      # (Maintain consistency with the address in nvcc -- version)

export PATH=$CUDA_HOME/bin:$PATH

export LD_LIBRARY_PATH=$CUDA_HOME/lib64:$LD_LIBRARY_PATH
```
You can use python setup.py clean to check the CUDA_HOME path. Also, check the outputs of nvcc --version and g++ --version, as well as print(torch.cuda.is_available()) and print(torch.version.cuda).
```python
python setup.py clean
nvcc --version
g++ --version
print(torch.cuda.is_available())
print(torch.version.cuda)
```

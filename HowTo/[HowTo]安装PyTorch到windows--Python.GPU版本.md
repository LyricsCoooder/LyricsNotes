# 安装PyTorch到windows--Python.GPU版本

- *PyTorch官网* https://pytorch.org/
- *CUDA官网（PyTorch.GPU版本必须的环境）*https://developer.nvidia.com/cuda-toolkit

根据电脑环境安装对应的版本：

```sh
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu117
```

验证安装，python：

```python
import torch

print(torch.__version__)
print('gpu',torch.cuda.is_available())
```

输出该结果，证明安装成功：

```
2.0.1+cu117
gpu True
```


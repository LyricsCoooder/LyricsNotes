# Tensors(张量)的属性

张量属性描述了它们的形状、数据类型以及存储它们的设备.

```py
tensor = torch.rand(3,4)

print(f"Shape of tensor: {tensor.shape}")# 形状
print(f"Datatype of tensor: {tensor.dtype}")# 类型
print(f"Device tensor is stored on: {tensor.device}")# 存储设备
```

Out:

```sh
Shape of tensor: torch.Size([3, 4])
Datatype of tensor: torch.float32
Device tensor is stored on: cpu
```


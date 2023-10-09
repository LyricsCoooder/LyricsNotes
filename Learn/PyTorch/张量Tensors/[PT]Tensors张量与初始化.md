# Tensors：张量

张量是一种特殊的数据结构，与数组和矩阵非常相似，在 PyTorch 中，我们使用张量对模型的输入和输出以及模型的参数进行编码，张量与 NumPy 的 ndarray 类似，不同之处在于张量可以在 GPU 或其他硬件加速器上运行.

导入`torch`库来使用Tensors

```py
import torch
```

#### Tensors(张量)的初始化

张量可以通过多种方式初始化，具体包括下面的例子.

##### 直接通过数据初始化

张量可以直接从数据创建，数据类型是自动推断的.

```py
tensor_data = torch.tensor([[1, 2], [3, 4]])
```

##### 通过NumPy array初始化

张量可以通过NumPy array初始化，反之NumPy array也可以通过tensors初始化.

```py
np_array = numpy.array(data)
tensor_np = torch.from_numpy(np_array)	
np_array_from_Tensor = tensor_np.numpy()
```

##### 通过其他tensors张量初始化

新张量保留参数张量的属性（形状、数据类型），除非显式覆盖.

```py
tensor_ones = torch.ones_like(tensor_data) # 保留张量tensor_data的属性
print(f"Ones Tensor: \n {tensor_ones} \n")

tensor_rand = torch.rand_like(tensor_data, dtype=torch.float) # 覆盖张量tensor_datade的属性
print(f"Random Tensor: \n {tensor_rand} \n")
```

Out:

```shell
Ones Tensor:
 tensor([[1, 1],
        [1, 1]])

Random Tensor:
 tensor([[0.0285, 0.9179],
        [0.6143, 0.9016]])
```

##### 通过随机值或常数初始化

shape 是张量维度的元组，在下面的函数中，它确定输出张量的维数.

```py
shape = (2,3,)
rand_tensor = torch.rand(shape)# 随机初始化
ones_tensor = torch.ones(shape)# 全都初始化为 1
zeros_tensor = torch.zeros(shape)# 全都初始化为 0
```

​	
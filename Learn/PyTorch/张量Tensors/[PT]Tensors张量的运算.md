# Tensors(张量)的运算

每一个Tensors运算都可以在GPU运行（速度通常高于 CPU），在开始Tensors运算之前，可以修改Tensor张量的存储位置.

```sh
tensor = torch.rand(3, 4)
if torch.cuda.is_available():
  tensor = tensor.to('cuda')# 修改存储位置为 'cuda'
```

#### 类似于NumPy的索引与切片

Tensors拥有类似于NumPy的索引与切片功能，可以完成类似下方的任务.

> `string[start:end]`：获取从 `start` 到 `end` - 1 的所有字符,
>
> `string[:end]`：获取从字符串开头到 `end` - 1 的所有字符
>
> `string[start:]`：获取从 `start` 到字符串末尾的所有字符
>
> `string[start:end:step]`：获取从 `start` 到 `end` - 1 的所有字符，不包括每一个 `step` 字符

```py
tensor = torch.ones(4, 4)
tensor[:,1] = 0
print(tensor)
```

Out:

```sh
tensor([[1., 0., 1., 1.],
        [1., 0., 1., 1.],
        [1., 0., 1., 1.],
        [1., 0., 1., 1.]])
```

#### 以下运算基于该前提：

> ```py
> npArray1 = np.array([[1,2], [3,4], [5,6]])
> npArray2 = np.array([[7,8], [9,0]])
> npArray3 = np.array([[11,12], [13,14], [15,16]])
> 
> tensor1 = torch.tensor(npArray1)
> tensor2 = torch.tensor(npArray2)
> tensor3 = torch.tensor(npArray3)
> ```

#### 张量相乘

张量相乘要求两张量的属性相同.

```py
ansTensor = tensor1 * tensor3
print(ansTensor)
```

##### 张量的矩阵相乘

```py
ansTensor = tensor1 @ tensor2
print(ansTensor)
```

Out

----

#### 使用torch.cat或torch.stack进行堆叠

torch.cat与torch.stack的定义，：

> torch.cat(*tensors*, *dim=0*, *, *out=None*) → Tensor
>
> torch.stack(*tensors*, *dim=0*, *, *out=None*) → Tensor
>
> torch.stack与torch.cat对应的第0维，都指的是堆叠后的0维

#####  根据`dim`与tensors列表进行堆叠:

使用torch.cat堆叠两tensor，不会提升当前tensor的维度，而是堆叠在当前的tensor之中.

```py
tensorsCatDim0 = torch.cat([tensor1, tensor2], dim=0)
tensorsCatDim1 = torch.cat([tensor1, tensor3], dim=1)
print('tensorsCatDim0:\n',tensorsCatDim0)
print('tensorsCatDim1:\n',tensorsCatDim1)
```

Out:

```
tensorsCatDim0:
 tensor([[1, 2],
        [3, 4],
        [5, 6],
        [7, 8],
        [9, 0]], dtype=torch.int32)
tensorsCatDim1:
 tensor([[ 1,  2, 11, 12],
        [ 3,  4, 13, 14],
        [ 5,  6, 15, 16]], dtype=torch.int32)
```

##### torch.stack 根据`dim`与tensors列表进行堆叠:

torch.stack会提升当前tensor的维度，以保证当前的tensor直接堆叠，torch.stack要求堆叠的tensors具有相同的大小，而torch.cat不要求.

```py
tensorStackDim0 = torch.stack([tensor1, tensor3], dim=0)  # 保证所有tensors大小相同
tensorStackDim1 = torch.stack([tensor1, tensor3], dim=1)  # 保证所有tensors大小相同
tensorStackDim2 = torch.stack([tensor1, tensor3], dim=2)  # 保证所有tensors大小相同
print('tensorStackDim0:\n',tensorStackDim0)
print('tensorStackDim1:\n',tensorStackDim1)
print('tensorStackDim2:\n',tensorStackDim2)
```

Out:

```
tensorStackDim0:
 tensor([[[ 1,  2],
         [ 3,  4],
         [ 5,  6]],

        [[11, 12],
         [13, 14],
         [15, 16]]], dtype=torch.int32)
tensorStackDim1:
 tensor([[[ 1,  2],
         [11, 12]],

        [[ 3,  4],
         [13, 14]],

        [[ 5,  6],
         [15, 16]]], dtype=torch.int32)
tensorStackDim2:
 tensor([[[ 1, 11],
         [ 2, 12]],

        [[ 3, 13],
         [ 4, 14]],

        [[ 5, 15],
         [ 6, 16]]], dtype=torch.int32)
```


# Transform类.父子关系
#U3D

Transform类提供大量变量和方法来控制父子关系.

#### 父子关系相关的变量

当前对象的子对象数量.

```cs
public int childCount ;
```

当前对象的父级，更改父级将修改相对于父级的位置、缩放和旋转，但保持世界空间位置、旋转和缩放不变.

```cs
public Transform parent ;
```

#### Transform.SetParent

设置当前对象的父级为`parent`，`worldPositionStays`的值决定了是否修改相对于父级的位置、缩放和旋转，使对象保持与之前相同的世界空间位置、旋转和缩放.

```cs
public void SetParent (Transform p);
public void SetParent (Transform parent, bool worldPositionStays);
```

#### 查找当前对象的子对象

可以通过名字来进行查找，也可以通过索引直接获取子对象.

##### Transform.Find

根据当前游戏对象的子对象的名字查找对象，遍历算法，即使失活也能找到，并且对更深层的子对象屏蔽.

```cs
public Transform Find (string n);
```

##### Transform.GetChild

通过索引获取当前对象的子对象.

```cs
public Transform GetChild (int index);
```

##### Transform.GetSiblingIndex

获取当前对象作为子对象的索引.

```cs
public int GetSiblingIndex ();
```

##### Transform.SetSiblingIndex

Transform也提供了API用于操作子对象的索引，尽量不要越界，如果越界会将`SiblingIndex`设置为最大索引.

```cs
public void SetSiblingIndex (int index);
```

#### 解除当前对象与子对象的关联

清除所有子项的父级，并且不删除任何对象.

##### Transform.DetachChildren

```cs
public void DetachChildren ();
```
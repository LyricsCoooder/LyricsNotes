# Transform类.角度与旋转
#U3D

再Transform中角度有两种表示方式`transform.rotation`与`transform.eulerAngles`.

#### EulerAngles

`transform.eulerAngles`为一个Vector3向量，用于获取当前对象的世界坐标角度，对应的也存在本地角度`localEulerAngles`，并且和位置一样，角度只能整体赋值.

```cs
this.transform.eulerAngles;
this.transform.localEulerAngles;
```

##### 角度变换

与位移类似，也就是说根据角度变化量进行角度更新，transform提供`Rotate`方法进行控制

> ##### Rotate
>
> ```cs
> public void Rotate (Vector3 eulers, Space relativeTo= Space.Self);
> public void Rotate (Vector3 axis, float angle, Space relativeTo= Space.Self);
> ```
>
> 使用 Transform.Rotate 以各种方式旋转 GameObjects，eulers为旋转的角度，`Space`为枚举类型，包含`Self`与`world`，第二个方法为重载方法，指围绕着axis这条轴进行旋转，旋转角度为angle.

相对于某一个点的某一个轴进行旋转.

> ##### RotateAround
>
> ```cs
> public void RotateAround (Vector3 point, Vector3 axis, float angle);
> ```
>
> 将变换围绕穿过世界坐标中的point的 axis轴旋转angle度.


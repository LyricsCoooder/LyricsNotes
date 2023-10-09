# Transform类.位置与位移
#U3D 

Tansform会依附于每一个Unity游戏对象，是每个对象不可缺少的类，用来管理对象的位置，旋转，缩放，父子关系，坐标转换等相关信息管理.

#### 位置

使用`position`可以获取到该Unity对象的全局位置，也就是绝对坐标点，不受父对象的而改变.

```cs
this.transform.position;
```

使用`localPosition`可以获取到该Unity对象相对于父对象的相对位置.

```cs
this.transform.localPosition;
```

> 在很多时候`position`与`localPosition`是相等的，在Inspector面板上显示的的是`localPosition`.

`position`与`localPosition`的赋值必须整体赋值，不可以单独赋值.

```cs
this.transform.position = Vector3(1, 1, 1);
//this.transform.position.X = 1; 为错误写法，不被允许
```

所以可以将当前的`position`存为临时变量，再单独修改该临时变量，再更新修改.

```cs
Vector3 tempPos = this.transform.position;
tempPos.X = 1;
this.transform.position = tempPos;
```

#### 对象当前的各朝向

Transform中定义了实时变化的各个方向的单位向量，包括前右上，当该物体转向，所有方向也会变化.

```cs
this.transform.forward;
this.transform.up;
this.transform.right;
```

#### 位移

$$
位移 = (方向)*(时间)*(速度)
$$

不使用API控制游戏对象产生位移的示例.

```cs
speed = 1;
time = Time.deltaTime;
this.transform.position += this.tansform.forward * speed * time;
```

使用`Translate`方法对游戏对象操作.

> ##### Translate
>
> `translation`为位移，`Space`为枚举类型，包含`Self`与`world`.
>
> ```cs
> public void Translate (Vector3 translation, Space relativeTo= Space.Self);
> ```

沿世界坐标系的`forward`方向进行移动.

```cs
this.transform.Translate (Vector3.forward * speed * time, Space.World); 
```

沿自己的坐标系的`forward`方向进行移动.

```cs
this.transform.Translate (this.transform.forward * speed * time, Space.Self); 
```

尽量将该函数的两个参数配套使用，否则增加逻辑负担.


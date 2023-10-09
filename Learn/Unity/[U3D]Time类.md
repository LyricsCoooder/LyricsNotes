# Time类
#U3D

Time提供了大量的静态方法去获取Unity提供的时间信息，并且用于控制和修改.

#### 时间缩放比例

Time类提供静态变量`timeScale`来控制时间N倍速.

```cs
Time.timeScale = 0; //暂停游戏
Time.timeScale = 2; //2倍速
Time.timeScale = 1; //正常速度
```

#### 帧间隔时间

Time类提供两种帧间隔时间，一种是受`timeScale`影响的帧间隔时间`deltaTime`，另一种是不受影响的`unscaledDeltaTime`，两者帧间隔时间在编辑模式下都会尽可能快的去运行，可以根据需求选择不同的帧间隔时间.

> deltaTime = timeScale * unscaledDeltaTime；

```cs
Time.deltaTime; //受timeScale影响
Time.unscaledDeltaTime; //不受timeScale影响
```

#### 物理帧间隔时间

类似于帧间隔时间，物理帧间隔时间用`fixedDeltaTime`和`fixedUnscaledDeltaTime`来获取.

```cs
Time.fixedDeltaTime;
Time.fixedUnscaledDeltaTime;
```

#### 游戏运行开始到现在的时间

Time类提供两种游戏运行开始到现在的时间的变量，一种是受`timeScale`影响的，一种不受影响.

```cs
Time.time;
Time.unscaledDeltaTime;
```

#### 游戏从运行开始到现在的帧数

获取游戏从运行开始到现在跑了多少帧.

```cs
Time.frameCount;
```

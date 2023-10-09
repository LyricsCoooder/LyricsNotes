# 常见生命周期函数
#U3D

当Unity脚本挂载在游戏对象上时，在该对象的整个生命周期中，通过反射会自动调用的一些固定名称的函数.

> 当一个游戏对象初始为未激活状态，不会创建该对象并且不会执行以下函数，并在首次激活该游戏对象时执行.

##### Awake

Awake类似于类的构造函数，该函数在该类对象被Unity实例化时运行，可以将其用作构造函数.

```CS
private void Awake() {
}
```

##### OnEnable

OnEnable在该脚本挂载的游戏对象每次被激活时运行，默认激活情况下，会在Awake执行后执行.

```cs
 private void OnEnable() {	
 }
```

##### Start

Start在该脚本挂载的游戏对象被创建的第一次帧更新时执行，经常用于初始化参数与行为.

```cs
private void Start() {
}
```

##### FixedUpdate

在该脚本挂载的游戏对象被激活时，FixedUpdate在每一个物理帧进行运行，经常用于物理碰撞检测，更新的步长时间可以在设置*Project Setting->Time* 中设置.

```cs
private void FixedUpdate() {
}
```

##### Update

在该脚本挂载的游戏对象被激活时，Update在每一个逻辑帧运行，经常用于编写核心控制逻辑.

```cs
private void Update() {
}
```

##### LateUpdate

在该脚本挂载的游戏对象被激活时，LateUpdate是晚于Update运行的函数，Unity的动画操作位于Update于LateUpdate之间运行，所以LateUpdate经常用于更新摄像机信息.

```cs
private void LateUpdate() {
}
```

##### OnDisable

OnEnable在该脚本挂载的游戏对象每次被失活时运行.

```cs
 private void OnDisable() {	
 }
```

##### OnDestroy

OnDestroy类似于析构函数，该函数在该脚本挂载的游戏对象被删除时运行，并且在运行该函数之前该游戏对象将失活并删除.

```cs
private void OnDestroy() {
}
```
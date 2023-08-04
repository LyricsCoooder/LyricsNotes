# Transform类.缩放与看向
#U3D

与position类似，缩放也拥有相对世界缩放`Transform.lossyScale`和本地缩放`Transform.localScale`.

```cs
public Vector3 lossyScale ;
public Vector3 localScale ;
```

并且`lossyScale`为只读变量，只能修改`Transform.localScale`，并且不提供API.

#### LookAt

Unity提供`LookAt`方法使游戏对象的本地面朝向一直面向某个点或者某个对象，旋转变换以将其向上方向矢量指向 `worldUp` 矢量暗示的方向，如果省略`worldUp` 参数，则该函数会使用世界空间 y 轴。如果向前方向垂直于`worldUp`.

```cs
public void LookAt (Vector3 worldPosition);
public void LookAt (Vector3 worldPosition, Vector3 worldUp= Vector3.up);
public void LookAt (Transform target);
public void LookAt (Transform target, Vector3 worldUp= Vector3.up);
```


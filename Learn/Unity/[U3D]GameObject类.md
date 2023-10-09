# GameObject类
#U3D

GameObject是Unity中所有脚本依附的游戏对象的类，是Unity最重要的API之一.

Unity API 文档：https://docs.unity3d.com/cn/2021.2/ScriptReference/GameObject.html

#### GameObject类的构造函数

Unity提高构造函数用来创建空游戏对象.

```cs
public GameObject ();
public GameObject (string name);
public GameObject (string name, params Type[] components);
```

创建一个名为`name`的新游戏对象，`components`指新对象所包含的组件数组.

#### GameObject类的成员变量

所有MonoBehavior类都会依附于GameObject，并且通过`this.gameObject`可以获得该对象，也就可以可以获得该类的相关信息，这里介绍一些重要的成员变量.

- `this.gameObject.name`：游戏对象的名字.
- `this.gameObject.activeself`：游戏对象是否被激活.
- `this.gemObject.isStatic`：游戏对象是否为静态.
- `this.gemeObject.layer`：游戏对象当前所在的层.
- `this.gemeObject.tag`：游戏对象当前所在的标签.
- `this.gemeObject.tansform`：游戏对象的tansform类信息.
  - `this.tansform`与`this.gemeObject.tansform`含义相同.

#### GameObject类的静态方法

GameObject提供了静态方法，通过`GameObject`获取静态方法，都是一些增加对象和查找对象的方法.

##### GameObject.CreatePrimitive

```cs
public static GameObject CreatePrimitive (PrimitiveType type);
```

根据传入的`type`，来创建Unity中自带的预制体，`type`是一种枚举类型，具体看[PrimitiveType](https://docs.unity3d.com/cn/2021.2/ScriptReference/PrimitiveType.html).

##### GameObject.Find

```cs
public static GameObject Find (string name);
```

根据传入的`name`，查找GameObject并返回它，此函数仅返回活动 GameObject，如果未找到具有`name`的GameObject，则返回null.

> 出于性能原因，建议不要每帧都使用此函数，而是在启动时将结果缓存到成员变量中.

##### GameObject.FindGameObjectsWithTag

```cs
public static GameObject[] FindGameObjectsWithTag (string tag);
```

返回标签为`tag`的活动GameObjects的数组，如果未找到任何GameObject，则返回空数组.

> 标签在使用前必须在标签管理器中加以声明。如果此标签不存在，或者传递了空字符串或null作为标签，则将抛出UnityException.

##### GameObject.FindWithTag

~~~cs
public static GameObject FindWithTag (string tag);
~~~

返回一个标记为`tag`的活动GameObject，如果未找到GameObject，则返回null.

> 此方法返回它找到的具有指定标签的第一个GameObject，如果一个场景包含多个具有指定标签的活动GameObjects，则无法保证此方法返回特定GameObject.

##### Object.Instantiate

~~~cs
public static Object Instantiate (Object original);
~~~

克隆`original`对象并返回克隆对象，Instantiate函数有很多重载，详情可以看[Object.Instantiate](https://docs.unity3d.com/cn/2021.2/ScriptReference/Object.Instantiate.html).

##### Object.Destroy

```cs
public static void Destroy (Object obj, float t= 0.0F);
```

在当前更新循环之后立即销毁或从现在开始`t`秒后销毁对象obj，如果obj是Component，则此方法会从GameObject移除该组件并将它销毁，如果obj是GameObject，则会销毁该GameObject，其所有组件以及该GameObject的所有变换子项，实际的对象销毁操作始终延迟到当前更新循环结束，但始终在渲染前完成.

> 销毁 MonoBehaviour 脚本时，在删除脚本之前会调用 OnDisable 和 OnDestroy.

##### Object.DontDestroyOnLoad

```cs
public static void DontDestroyOnLoad (Object target);
```

在加载新的Scene时，请勿销毁Object，默认情况会销毁.

#### GameObject类的公有方法

GameObject提供了公有方法，用来对当前对象进行操作.

##### GameObject.AddComponent

```cs
public T AddComponent ();
```

向当前对象添加类型为`T`的新组件.

##### GameObject.GetComponent

在GameObject中拥有和Mono类中一样的`AddComponent`一系列方法，详细可查[官方API](https://docs.unity3d.com/cn/2021.2/ScriptReference/GameObject.html).

##### GameObject.SetActive

```cs
public void SetActive (bool value);
```

根据给定的值`true`或`false`，激活/停用GameObject.




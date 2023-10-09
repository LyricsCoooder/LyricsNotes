# 在Inspector中显示可编辑参数
#U3D

在Inspector中可以显示与其关联的脚本的成员变量，通过特性和反射对其进行操作.

> 大部分的变量类型都可以显示在Inspector面板中，特殊的字典Dictionary不能显示在Inspector面板中

##### 显示公有成员变量

默认情况下，只有类的共有成员可以显示在Inspector面板上，当声明一个共有成员变量时，Inspector面板中自动产生可编辑选项.

- 如果不希望将公有成员变量显示在Inspector面板上，可以使用 `[HideInspector]` 特性.

  ```cs
  [HideInspector]
  public int num;
  ```

##### 显示私有成员变量和保护成员变量

默认情况下不可显示，但可以通过`[SerializeField]`特性，在Inspector面板上显示目标成员.

```cs
[SerializeField]
private int num;

[SerializeField]
protected string str;
```

> Inspector默认显示：所有成员变量可以使用类似以下语句，进行默认设置，并在Inspector面板显示.
>
> ```cs
> public int num = 1+
>     
> ```


##### 显示自定义类型

默认情况下，`class`与`struct`类型不能被显示在Inspector面板上，通过`[System.Serializable]`,`[SerializeField]`特性可以显示.

```cs
//在继承自mono...类的外部，定义的结构类
[System.Serializable]
class MyClass{
    int hp;
    int age;
}

//在继承自mono...类的内部，定义的MyClass类型的成员变量
[SerializeField]
public MyClass data;
```
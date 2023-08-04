# 在控制台中打印
#U3D

#### 没继承自MonoBehavior的类

如果想在没继承自MonoBehavior的类中编写打印脚本，可以使用unity提供的`Debug`类.

```CS
Debug.Log("This is a log.");
Debug.LogError("This is a error.");
Debug.LogWarning("This is a warning.");
```

#### 继承自MonoBehavior的类

如果想在继承自MonoBehavior的类中编写打印脚本，可以更方便的使用`print`方法.

```CS
print("This is a test log.")
```


# MonoBehavior 基类
#U3D

MonoBehaviour 类是一个基类，所有 Unity 脚本都默认派生自该类。当您从 Unity 的项目窗口创建一个 C# 脚本时，它会自动继承 MonoBehaviour，并提供模板脚本.
#### 继承MonoBehaviour的类

在Unity中，使用反射机制判断一个C#脚本类是否继承于MonoBehavior，如果想将C#脚本挂载在一个对象之上，那么这个脚本类必须继承于MonoBehavior基类，如果不需要挂载在对象之上，就不需要继承于MonoBehavior.

> 当一个脚本需要被挂载在一个对象上时，unity通过文件名来定位该类，所以要求类名与文件名一致，否则会发出警告.

```cs
public class TestScript : MonoBehaviour
```

当一个类继承于MonoBehaviour，那么该类不能通过`new`来进行实例化，只能通过挂载的方式进行使用，因此继承自MonoBehaviour的类不需要实现该类的构造函数. 

#### 不继承MonoBehaviour的类

如果一个类不继承MonoBehaviour基类，那么该类可以使用 `new` 进行实例化，用于数据结构类或者管理类.

# Input类.鼠标键盘的输入

Input类：https://docs.unity3d.com/cn/2021.2/ScriptReference/Input.html

Input类提供了硬件输入的API，用于鼠标，键盘，手柄等设备的输入，所有的Input方法一般都使用在Update函数中.

#### 鼠标信息

一些定义在Input类中的，用于获取鼠标信息的静态变量.

- mousePosition：`public static Vector3 mousePosition ;`
  - 用于获取鼠标当前的位置信息，只读，返回值是一个Vector3类型，但只有X，Y有意义，会随着鼠标移动而变化，屏幕或窗口的左下角坐标为 (0, 0).
- mousePresent：`public static bool mousePresent ;`
  - 指是否检测到鼠标设备.
- mouseScrollDelta：`public static Vector2 mouseScrollDelta ;`
  - 当前的鼠标滚动增量，只读，Input.mouseScrollDelta 存储在 Vector2.y 属性中，Vector2.x 值将被忽略，检测鼠标滚轮向上滚动为Vector2.y 为1，反之则为-1，用于检测滚轮输入.

#### 鼠标输入

用来检测鼠标上的中键，左右键的按下，抬起，长按的方法，这些函数中`int button`用于代表鼠标按键，0 为 左键，1 为 右键，2 为中键.

- GetMouseButton：`public static bool GetMouseButton (int button);`
  - 当鼠标某个键被长按时返回true，否则返回false.
- GetMouseButtonDown：`public static bool GetMouseButtonDown (int button);`
  - 当鼠标某个键被按下的瞬间返回true.
- GetMouseButtonUp：`public static bool GetMouseButtonUp (int button);`
  - 当鼠标某个键被抬起的瞬间返回true.

#### 键盘输入

与鼠标输入类似，键盘的输入使用枚举`KeyCode`来传入键盘的按键，其中包含了大部分的键盘按键.

- GetKey：`public static bool GetKey (KeyCode key);`
  - 当键盘某个键被长按时返回true，否则返回false.
- GetKeyDown：`public static bool GetKeyDown (KeyCode key);`
  - 当键盘某个键被按下的瞬间返回true，否则返回false.
- GetKeyUp：`public static bool GetKeyUp (string name);`
  - 当键盘某个键被抬起的瞬间返回true，否则返回false.

#### 虚拟轴

Unity提供了大量的默认虚拟轴用来实现更丝滑的控制，使用`GetAxis`来获取默认轴的值.

- Input manager设置位置：Edit > Project Settings > Input Manager，在这里可以自定义轴.

- GetAxis：`public static float GetAxis (string axisName);`
  - 返回值平滑变化.
  - axisName为默认轴的名称.
- GetAxisRaw：`public static float GetAxisRaw (string axisName);`
  - 返回值直接变化.

官方示例：

```cs
float moveSpeed = 10;
//定义对象移动的速度

float horizontalInput = Input.GetAxis("Horizontal");
//获取水平输入轴的数值

float verticalInput = Input.GetAxis("Vertical");
//获取垂直输入轴的数值

transform.Translate(new Vector3(horizontalInput, verticalInput, 0) * moveSpeed * Time.deltaTime);
//将对象移动到 XYZ 坐标，分别定义为 horizontalInput、0 以及 verticalInput
```


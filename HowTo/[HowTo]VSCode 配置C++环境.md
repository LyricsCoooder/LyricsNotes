# VSCode 配置C++环境

索栏搜索`c++`并安装扩展.

#### 安装C++编译器

C++ 是一种编译语言，这意味着程序的源代码必须经过翻译（编译）才能在计算机上运行VS Code 首先是一个编辑器，并依赖命令行工具来完成大部分开发工作流程，C/C++ 扩展不包括 C++ 编译器或调试器。您将需要安装这些工具或使用计算机上已安装的工具.

##### 下载MSYS2

- https://www.msys2.org/ 

- MSYS2 是工具和库的集合，为您提供了一个易于使用的环境来构建、安装和运行本机 Windows 软件.

通过该命令安装Mingw-w64.

```
pacman -S --needed base-devel mingw-w64-x86_64-toolchain
```

##### 配置环境变量

使用以下步骤将 Mingw-w64 bin 文件夹的路径添加到 Windows PATH 环境变量：

1. `win + R`打开`systempropertiesadvanced`.

2. 选择用户变量中的路径变量，然后选择编辑.

3. 确切的路径取决于安装的 Mingw-w64 版本以及安装位置，默认为``C:\msys64\mingw64\bin`` .

##### 检查的MinGW安装

要检查Mingw-w64工具是否已正确安装且可用，打开一个新的命令提示符并键入：

```
gcc --version
g++ --version
gdb --version
```

#### Hello World

根据教程[Hello World](https://code.visualstudio.com/docs/languages/cpp#_hello-world)来判断是否可以运行C++.

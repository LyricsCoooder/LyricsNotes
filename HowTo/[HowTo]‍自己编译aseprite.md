# Aseprite的编译

#### 获取源代码

通过git使用以下命令克隆存储库及其所有子模块:

```sh
git clone --recursive https://github.com/aseprite/aseprite.git
```

更新现有克隆，您可以使用以下命令:

```sh
cd aseprite
git pull
git submodule update --init --recursive
```

```
call "D:\VisualStudio\VisualStudioIDE\Common7\Tools\VsDevCmd.bat" -arch=x64
```

#### 依赖关系

- 最新版本的[CMake](https://cmake.org/)（3.16 或更高版本）
- [ninja](https://ninja-build.org/)构建系统
- [以及Skia 库](https://github.com/aseprite/skia#readme)`aseprite-m102`分支的编译版本。有[可用的预构建包](https://github.com/aseprite/skia/releases)。[*您可以在laf*](https://github.com/aseprite/laf#dependencies)[依赖项](https://github.com/aseprite/laf#dependencies)页面中获取一些额外信息

```sh
cmake -DCMAKE_BUILD_TYPE=RelWithDebInfo -DLAF_BACKEND=skia -DSKIA_DIR=C:\Users\10189\Desktop\As\Skia-Win -DSKIA_LIBRARY_DIR=C:\Users\10189\Desktop\As\Skia-Win\out\Release-x64 -DSKIA_LIBRARY=C:\Users\10189\Desktop\As\Skia-Win\out\Release-x64\skia.lib -G Ninja ..
```

```sh
C:\Users\10189\Desktop\As\ninja\ninja.exe aseprite
```


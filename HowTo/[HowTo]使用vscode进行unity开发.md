# 使用vscode进行unity开发

- *官方教程：[Unity Development with VS Code](https://code.visualstudio.com/docs/other/unity#_install-build-tools-for-visual-studio-windows-only)*

使用vscode进行unity开发：

- 安装 [.NET SDK](https://dotnet.microsoft.com/download).
- 在vscode中安装 [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) 插件.
- 使用快捷键 `Ctrl + ,` 然后搜索 `Omnisharp: Use Modern Net setting`"， 修改`omnisharp.useModernNet": false`.
- 打开`Unity Preferences -> External Tools`,然后选择 `Visual Studio Code` 为 `External Script Editor`.
  - 如果这里没有，可以去安装目录寻找 `code.exe`，并添加.
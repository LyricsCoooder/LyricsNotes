# 解决在使用git status命令时中文文件名显示错误

设置git的 *core.quotepath* 选项为false：

```sh
git config --global core.quotepath false
```

**修改原因**
*core.quotepath* 选项为 true 时，会对中文字符进行转义再显示，看起来就像是乱码，设置该选项为false，就会正常显示中文


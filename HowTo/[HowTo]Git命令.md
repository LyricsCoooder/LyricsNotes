# Git命令

包含git大部分常用命令，相当于是一个命令表

#### 帮助手册:git help

显示常用帮助

```
git help
```

显示全部帮助

```
git help -a
```

显示帮助手册

```
git help -g
```

显示特定的帮助手册

```
git help [手册名称]
git help add //打开add手册
```

#### 配置信息:git config

显示配置列表

```
git config --list
```

配置全局特定配置

```
git config --global [配置名] '[名字]'
git config --global user.name 'lyrics'
git config --global user.email 'lyrics528169@gmail.com'
```

重置特定配置

```
git config --unset --global [配置名]
git config --unset --global user.name
```

全局设置会保存在 ```~/.gitconfig```，使用```cat```查看

```
cat ~/.gitconfig
```

#### 初始化:git init

使用`git init`在当前目录下初始化git，并跟踪该文件夹，当使用该命令后，git会跟踪该文件夹中的版本变化，并记录

```
git init
```

#### 当前状态查看:git status

```
git status
```

#### 添加发生变化的文件到暂存区:git add

添加当前所有变化的文件/目标文件到暂存区

```
git add .
git add [目标文件]
```

#### 交付当前所有的变化:git commit

交付当前所有变化，并给出描述

```
git commit -m'[描述]'
```

#### 查看当前文件夹的所有日志

```
git log
git log --oneline
```

#### 查看文件变化，查看不同:git diff

查看所有被修改文件的变化，或者目标文件的变化

```
git diff
git diff [目标文件]
```

`git diff`默认对比工作区和暂存区的区别，使用`git diff --staged`查看暂存区和提交库的区别

#### 查看git日志:git log

显示所有的提交记录

```
git log
```

#### 移除文件:git rm

如果该文件已经在暂存区中不可使用`git rm`进行删除

```
git rm [文件名]
```

当被git追踪的文件名发生变化时，git默认为原文件被删除，使用`git rm`对被原文件进行删除，重新添加新的文件，使git可以重新追踪该文件

```
git rm [原文件名]
git add [被修改的新文件名]
```

#### 重命名，移动文件或目录:git mv

对文件进行重命名

```
git mv [原文件名] [新文件名]
```

移动文件的路径，相当于修改文件名

```
git mv [原路径] [新路径名]
```

移动目录及目录下所有文件到新的目录下

```
git mv [目录名] [目录地址]
git mv files1 filesRoot/
```

#### 从分支中恢复:git checkout head

从主分支中，将目标文件恢复，`head`指t最近的上次分支，依次类推`head^ `，`head^^`表示最近上两次分支和上三次分支，`--`表示主分支

```
git checkout head^ -- [文件名]
git checkout head^^ -- [文件名]
```

#### 按logID恢复:git revert

使用`git log --oneline`显示所有提交日志，并查看logID，然后使用`git revert`撤回目标提交

```
git revert [ID]
```

#### 创建分支:git branch

在使用给git 时创建分支可以帮助我们增添新功能，而不影响旧的分支，等新功能测试完毕再合并到旧分支上，就可以完成新功能的开发

查看当前分支：

```
git branch
```

新建分支：

```
git branch [分支名]
git branch [new-branch]
```

切换当前分支:

```
git checkout [目标分支名]
```

对比两个分支的区别：

```
git diff [分支名1]..[分支名2] [具体文件]
```

#### 合并分支:git merge

将一个分支合并在现有分支之上，首先查看当前分支：

```
git branch
```

将目标分支合并在当前分支之中：

```
git merge [目标分支]
```

当合并时产生冲突，先解决冲突再进行提交

#### 重命名，删除分支

重命名分支：

```
git branch -m [目标分支名] [新分支名]
```

#### 与远程仓库链接:git remote

```
git remote add origin [目标仓库的URL]
```

#### 提交本地分支到远程仓库:git push

```
git push -u origin [分支名]
```

push到特定的分支：

```
git push -u origin [本地分支名] [目标分支名]
//git push -u origin Base-CPU origin/Base-CPU
```

#### 克隆目标项目仓库，包含版本库:git clone

```
git clone [目标仓库的URL] [新的名字]
```

#### 更新远程代码库的更新，到本地的origin分支

该命令会将远程更新的代码加在本地的origin分支之中

```
git fetch
```


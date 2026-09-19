# Git 和 Linux 常用命令

这份笔记整理自“Git 和 Linux 常用命令我应该记住哪些”对话，覆盖日常开发中最常见的操作。

> 原对话中的 “liux” 应为 **Linux**。

## 一、Git 常用命令

### 1. 查看状态与历史

```bash
git status                  # 查看工作区状态
git log --oneline --graph   # 查看简洁提交历史
git diff                    # 查看未暂存修改
git diff --staged           # 查看已暂存修改
```

### 2. 提交代码

```bash
git add 文件名              # 暂存指定文件
git add .                   # 暂存当前目录所有修改
git commit -m "说明"        # 提交
git commit -am "说明"       # 暂存并提交已被 Git 跟踪的文件
```

### 3. 分支

```bash
git branch                  # 查看本地分支
git switch 分支名           # 切换分支
git switch -c 分支名        # 创建并切换到新分支
git merge 分支名            # 合并分支
git branch -d 分支名        # 删除已合并分支
```

### 4. 远程仓库

```bash
git remote -v               # 查看远程仓库
git pull                    # 拉取并合并远程更新
git fetch                   # 只拉取，不自动合并
git push                    # 推送当前分支
git push -u origin 分支名   # 首次推送并建立关联
```

### 5. 撤销与恢复

```bash
git restore 文件名          # 丢弃工作区修改
git restore --staged 文件名 # 取消暂存
git reset HEAD~1            # 撤销最近一次提交，但保留文件修改
git revert 提交ID           # 创建一个反向提交，较安全
```

⚠️ `git reset --hard` 会直接丢弃修改，使用前一定确认。

## 二、Linux 常用命令

### 1. 文件与目录

```bash
pwd                         # 当前目录
ls                          # 查看文件
ls -la                      # 查看包括隐藏文件的详细信息
cd 目录                     # 进入目录
cd ..                       # 返回上一级
cd ~                        # 回到用户主目录
mkdir 目录                  # 创建目录
touch 文件                  # 创建空文件
cp 源 目标                  # 复制
mv 源 目标                  # 移动或重命名
rm 文件                     # 删除文件
rm -r 目录                  # 删除目录
```

### 2. 查看文件内容

```bash
cat 文件                    # 一次性查看
less 文件                   # 分页查看
head 文件                   # 查看开头
tail 文件                   # 查看结尾
tail -f 日志文件            # 实时查看日志
```

### 3. 查找与过滤

```bash
find . -name "*.js"         # 查找文件
grep "关键词" 文件           # 搜索文本
grep -r "关键词" 目录        # 递归搜索
rg "关键词"                 # 更快的文本搜索工具
```

### 4. 权限与进程

```bash
chmod +x 文件               # 添加可执行权限
sudo 命令                   # 以管理员权限执行
ps aux                      # 查看进程
top                         # 查看系统进程和资源
kill 进程ID                 # 结束进程
```

### 5. 磁盘与网络

```bash
df -h                       # 查看磁盘空间
du -sh 目录                 # 查看目录大小
free -h                     # 查看内存
curl URL                    # 请求网页或 API
ping 域名                   # 测试网络
ssh 用户@服务器             # 远程登录
scp 文件 用户@服务器:路径   # 远程复制文件
```

### 6. 压缩与解压

```bash
tar -czf archive.tar.gz 目录/   # 压缩
tar -xzf archive.tar.gz         # 解压
```

## 三、终端常用快捷键

```text
Tab       自动补全文件名、文件夹名或命令
Tab Tab   显示所有匹配项
↑         重复上一条命令
Ctrl + R  搜索历史命令
Ctrl + A  跳到命令开头
Ctrl + E  跳到命令结尾
Ctrl + U  删除整行
Ctrl + C  取消当前输入或停止命令
```

## 四、建议优先熟练的命令

```text
pwd       ls -la    cd        mkdir     cp        mv        rm
grep      find      git status
git add   git commit git pull  git push   git switch
```

记忆方式：**Linux 负责操作文件和系统，Git 负责记录代码版本。**

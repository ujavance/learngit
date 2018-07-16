Github 学习笔记

1. 初始化一个Git仓库，使用 `git init`命令。
2. 添加文件到Git仓库，分两步：
    - 使用命令 `git add <file>`，注意，可反复多次使用，添加多个文件；
    - 使用命令 `git commit -m <message>` ，完成。
3. 一定要放到learngit目录下（子目录也行），因为这是一个Git仓库，放到其他地方Git找不到这个文件。
4. 掌握仓库当前的状态
    - 要随时掌握工作区的状态，使用`git status`命令。
    - 如果git status告诉你有文件被修改过，用 `git diff`可以查看修改内容。
5. 历史之间穿梭
    1. `HEAD` 指当前版本,上一版本是 `HEAD^`，上上版本是 `HEAD^^`,往上100个版本 `100个^`
    2. `git reset --hard commit_id` 恢复到指定版本
    3. `git log` 查看**提交历史**，确定要回退的版本
    4. `git reflog` 查看命令历史,确定要回到未来的哪个版本
6. `ssh-keygen -t rsa -C "youremail@qq.com"` 获得一个秘钥，只有指定秘钥的客户端才可以提交
7. `git remote add origin git@github.com:ujavance/learngit.git` 关联远端的仓库
8. Github 创建一个Response后，给的提示
    1. 关联本地的一个仓库.[代码](#relativelocalcode)
    2. 从这个仓库克隆出新的仓库 [代码](#createnewcode)
    3. 从另一个存储库导入代码
9.  从远程库克隆
    1.  先创建远程库，然后从远程库克隆
    2.  创建一个新的仓库, 同时初始化勾选 `Initialize this repository with a README`初始化一个 **md**文件
    3.  `git clone git@github.com:ujavance/gitskills.git` 克隆一个本地库
    4.  [检查克隆是否成功](#checkcloneok)
10. 分支管理
    1.  特点：创建、切换和删除分支可以快速完成
    2.  **创建与合并**分支
        1.  创建并切换可一条语句执行，也可两条语句执行
        2.  查看当前分支
        3.  [代码](#createbranchandcheckoutbrand)
        4.  修改当前文件
        5.  
11. end


<a id="relativelocalcode"></a>
或从命令行推送现有存储库
```cmd
git remote add origin git@github.com:ujavance/learngit.git
git push -u origin master
```

<a id="createnewcode"></a>
在命令行上创建一个新的存储库
```cmd
echo "# learngit" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:ujavance/learngit.git
git push -u origin master
```

<a id="checkcloneok"></a>
```cmd
$ cd gitskills
$ ls
README.md
```
<a id="createbranchandcheckoutbrand"></a>
```
// 创建并切换
$ git checkout -b dev
Switched to a new branch 'dev'

// 创建并切换相当于以下两条命令
$ git branch dev
$ git checkout dev
Switched to branch 'dev'

// git branch命令查看当前分支
// git branch命令会列出所有分支，当前分支前面会标一个*号。
$ git branch
* dev
  master

// 当前分支位于 Dev 上，修改Dev分支，并提交，然后切回master分支检查

$ git merge dev

查看分支：git branch
创建分支：git branch <name>
切换分支：git checkout <name>
创建+切换分支：git checkout -b <name>
合并某分支到当前分支：git merge <name>
删除分支：git branch -d <name>
```



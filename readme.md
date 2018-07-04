Github 学习笔记

1. 初始化一个Git仓库，使用git init命令。
2. 添加文件到Git仓库，分两步：
    - 使用命令git add <file>，注意，可反复多次使用，添加多个文件；
    - 使用命令git commit -m <message>，完成。
3. 一定要放到learngit目录下（子目录也行），因为这是一个Git仓库，放到其他地方Git找不到这个文件。
4. 掌握仓库当前的状态
    - 要随时掌握工作区的状态，使用git status命令。
    - 如果git status告诉你有文件被修改过，用git diff可以查看修改内容。
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
    4. #

9.  end


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
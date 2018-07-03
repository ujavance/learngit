Github 学习笔记

1. 初始化一个Git仓库，使用git init命令。
2. 添加文件到Git仓库，分两步：
    - 使用命令git add <file>，注意，可反复多次使用，添加多个文件；
    - 使用命令git commit -m <message>，完成。
3. 一定要放到learngit目录下（子目录也行），因为这是一个Git仓库，放到其他地方Git找不到这个文件。
4. 掌握仓库当前的状态
    - 要随时掌握工作区的状态，使用git status命令。
    - 如果git status告诉你有文件被修改过，用git diff可以查看修改内容。
5. end
# Git 常用操作总结

### 1 查看Git命令帮助
在每个命令后面加上 "--help"即可，但是都是英文的.
#### Example:  
git clone --help  
git add --help  

### 2 把远程仓库复制到本地来
[git clone](http://git-scm.com/docs/git-clone)
#### Example:  
git clone https://github.com/borishuai/git-basic-usage.git

### 3 跟踪新文件或暂存已修改文件(staged area)
[git add](http://git-scm.com/docs/git-add)
#### Example: 
git add hello.txt, 将hello.txt文件添加到暂存区  
git add ., 将所有文件添加到暂存区，"."表示所有文件，它会递归处理所有目录中的文件  
详细用法请参考：[Git 基础 - 记录每次更新到仓库](http://git-scm.com/book/zh/v1/Git-%E5%9F%BA%E7%A1%80-%E8%AE%B0%E5%BD%95%E6%AF%8F%E6%AC%A1%E6%9B%B4%E6%96%B0%E5%88%B0%E4%BB%93%E5%BA%93)

### 4 提交更新
[git commit](http://git-scm.com/docs/git-commit)
#### Example:
git commit,  如果不带"-m"参数，会进入编辑器提示你输入commit message，推荐每次使用带上“-m”参数。  
git commit -m "Refine the login page", 提交并且加上commit message  
git commit -m "Refine the login page" -a, “-a”这个参数同时具备了git add的功能。

### 5 更新分枝(合并远程和本地的分枝)
[git pull](http://git-scm.com/docs/git-pull)
### Example:
git pull origin master，将远程和master分枝和本地的master分枝合并，其实可以理解为更新了远程分枝的代码到本地来。

### 6 提交分枝到远程服务器
[git push](http://git-scm.com/docs/git-push)
#### Example:
git push origin master，将本地的master分枝提交到远程服务器，如果远程该分枝不存在则新建分枝，否则进行合并。

### 7 查看你的文件在工作目录与缓存的状态
[git status](http://git-scm.com/docs/git-status)
### Example:
git status, 默认是带了"-l"参数的，就是完整显示当前的状态，内容比较多，同时列出下一步可以执行的命令.  
git status -s,以简短的形式显示当前的状态，基本上只显示了所有修改过以及未跟踪的文件。

### 8 删除文件或文件夹
对于Git中的文件或文件夹，如果我们要对它们进行删除，我们同样要通过Git命令来操作，而不能通过操作系统直接操作。
[git rm](http://git-scm.com/docs/git-rm)
#### Example:
git rm hello.txt, 删除hello.txt文件
git rm -rf abc,　删除文件夹abc及里面的所有内容

### 9 移动文件或文件夹
对于Git中的文件或文件夹，如果我们要对它们进行移动，我们同样要通过Git命令来操作，而不能通过操作系统直接操作。
[git mv](http://git-scm.com/docs/git-mv)
#### Example:
git mv hello.txt hello,　将hello.txt移动到hello文件夹下面  
git mv hello.txt hello/abcd.txt, 将hello.txt移动到hello文件夹下面，同时将名字修改为abcd.txt

### 10 用远程仓库文件覆盖本地文件
通常当我们对本地文件作了一些修改后打算放弃这些修改，使它回到修改前的状态时使用。
[git checkout](http://git-scm.com/docs/git-checkout)
#### Example:
git checkout hello.txt,　用远程的hello.txt覆盖本地的hello.txt文件

### 11 切换分枝
[git checkout](http://git-scm.com/docs/git-checkout)
#### Example:
git checkout branch1,　切换到branch1分枝  
git checkout -b branch1,　先创建branch1分枝，然后切换到branch1分枝，适合需要创建新分枝并且切换的情形

### 12 分枝处理常见操作
[git branch](http://git-scm.com/docs/git-branch)
#### Example:
git branch, 不带参数时列出本地已经存在的分支，并且在当前分支的前面加“*”号标记，和git branch --list等价  
git branch hello,　创建一个新的分枝hello，但并没有切换到新分枝，如果要创建后自动切换到新分枝，请使用git chekcout -b  
git branch -r, 列出所有的远程分枝  
git branch -a, 列出所有的本地分枝和远程分枝  
git branch -d hello，删除本地hello分枝，如果hello分枝的所有commits没有全部合并回它fork出来的分枝，则删除失败  
git branch -D hello, 强行删除本地hello分枝，不管hello分枝的所有commits有没有全部合并回它fork出来的分枝，  
git branch -d　-r origin/remote-branch, 删除远程分枝remote-branch  
git branch -m branch1 branch2, 将分枝branch1的名字改成branch2  


 
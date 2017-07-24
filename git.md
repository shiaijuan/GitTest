### Git学习笔记
#### 一、Git的安装
1. 在window系统上安装：从https://git-for-windows.github.io下载，然后按默认选项安装即可；
2. 安装完成后，在“桌面”上右击，在弹出的菜单中选择“Git Bash”；
3. 在蹦出一个类似命令行窗口的东西里面输入git命令：
    ```
    $ git --version   //查看git安装版本

    ```
4. 安装完成后，还需要最后一步设置，在命令行输入:
    ```
    $ git config --global user.name "Your Name"
    $ git config --global user.email "email@example.com"
    
    //因为Git是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和Email地址。
    ```
    注意git config命令的--global参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。
    

#### 二、创建版本库
##### 什么是版本库
版本库又名仓库，英文名repository，你可以简单理解成一个目录，这个目录里面的所有文件都可以被Git管理起来，每个文件的修改、删除，Git都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻可以“还原”。

##### 创建版本库的步骤：
1.  选择一个合适的地方，新建一个目录
    ```
    $ mkdir learnGit      //创建目录
    $ cd learnGit     //进入该目录
    $ pwd     //命令用于显示当前目录
    ```
2. 通过git init命令把这个目录变成Git可以管理的仓库 
    ```
    $ git init
    Initialized empty Git repository in /Users/michael/learngit/.git/
    //初始化一个空的git仓库在...目录下
    
    ```
    此时，learngit目录下有隐藏的.git目录，可以通过 **ls -ah** 命令，来查看learngit目录下所有文件（隐藏和未隐藏的）
    
##### 三、把文件放到版本库

- 把文件放到版本库的操作情境如下：

    在learngit目录里面新建一个文件，文件名为readme.txt，txt文件的内容如下：
    ```
    Git is a version control system.
    Git is free software.
    ```

1. 第一步，用命令git add告诉Git，把文件添加到仓库
    ```
    $ git add readme.txt
    ```
2. 用命令git commit告诉Git，把文件提交到仓库
    ```
    $ git commit -m "wrote a readme file"
    ```
    运行结果如下：
    ```
    [master (root-commit) cb926e7] wrote a readme file
    1 file changed, 2 insertions(+)
    create mode 100644 readme.txt
    
    //git commit命令执行成功后会告诉你，1个文件被改动（我们新添加的readme.txt文件），插入了两行内容（readme.txt有两行内容）。
    ```

    - git commit命令，-m后面输入的是本次提交的说明，可以输入任意内容，当然最好是有意义的，这样你就能从历史记录里方便地找到改动记录
    
    - commit可以一次提交很多文件，所以你可以多次add不同的文件，比如：
    ```
    $ git add file1.txt
    $ git add file2.txt file3.txt
    $ git commit -m "add 3 files."

    ```
    

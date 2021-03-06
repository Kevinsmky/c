
# Table of Contents

1.  [安装cygwin](#org86d4e06)
    1.  [下载安装文件](#org2b4c069)
    2.  [安装cygwin](#org82681d3)
        1.  [next到选择站点的时候添加163的地址](#orgd842656)
        2.  [选择gcc和相关软件进行安装](#org83eee47)
        3.  [完成后的确认](#orgaf79547)
    3.  [添加cygwin到windows的PATH中](#org3e1f32a)
2.  [下载VS Code并安装](#org33df5a4)
3.  [安装VS Code C/C++插件](#orgbf15058)
4.  [配置VS Code的C语言编译选项](#org61e8a43)
    1.  [cygwin下新建一个目录用于存放C的项目：](#org352031e)
    2.  [将.vscode目录下载下来并放到这个目录下](#org0b1d6e0)
5.  [Hello, World](#org1ebc142)


<a id="org86d4e06"></a>

# 安装cygwin


<a id="org2b4c069"></a>

## 下载安装文件

下面两个地址任选一个

[官网下载](https://cygwin.com/setup-x86_64.exe)

[我的github下载](https://github.com/linc5403/c/blob/master/ide/win/setup-x86_64.exe)


<a id="org82681d3"></a>

## 安装cygwin


<a id="orgd842656"></a>

### next到选择站点的时候添加163的地址

到下面这个页面的时候在Url里面输入 `http://mirrors.163.com/cygwin/` ，点击“Add”按钮。否则下载速度会相当慢。

![img](./img/cygwin-add-163.png)


<a id="org83eee47"></a>

### 选择gcc和相关软件进行安装

在 `Select Packages` 页面选择3个软件：gcc-core, gdb, cmake。注意左上角View的下拉菜单选中 `Full` ，然后右边可以搜索；双击Skip那个地方选中该软件：

![img](./img/cygwin-select-gcc-full.png)

![img](./img/cygwin-select-gdb-full.png)

![img](./img/cygwin-select-make-full.png)


<a id="orgaf79547"></a>

### 完成后的确认

安装完成后桌面会出现cygwin的快捷方式，双击会进入终端界面，在里面输入 `cc --version` 出现如下所示结果表示安装成功：

![img](./img/start-gcc.png)


<a id="org3e1f32a"></a>

## 添加cygwin到windows的PATH中

1.  打开windows环境变量设置
    
    ![img](./img/path-config-1.png)

2.  添加cygwin的bin目录到环境变量
    
    ![img](./img/path-config-2.png)


<a id="org33df5a4"></a>

# 下载VS Code并安装

[下载链接](https://code.visualstudio.com/download)

选择User Installer -> 64bit下载并安装：

![img](./img/download-win-64-user.png)

安装的时候一路Next就可以了， **重点:安装完成后需要重启电脑** ，因为需要将VS Code添加到系统路径中。


<a id="orgbf15058"></a>

# 安装VS Code C/C++插件

打开visual Studio Code，安装c/c++插件:

![img](./img/vs-install-plugin.png)


<a id="org61e8a43"></a>

# 配置VS Code的C语言编译选项


<a id="org352031e"></a>

## cygwin下新建一个目录用于存放C的项目：

    mkdir c-projects


<a id="org0b1d6e0"></a>

## 将.vscode目录下载下来并放到这个目录下

[.vscode目录](https://github.com/linc5403/c/tree/master/ide/win/.vscode)

1.  在c项目目录（c-projects）下启动VS Code：
    
        cd c-projects
        code .
    
    此时应该可以出现VS的界面

2.  在VS Code中新建.vscode目录：
    
    ![img](./img/create-dir.png)

3.  选中.vscode目录, 新建文件（ `c_cpp_properties.json` `launch.json` `tasks.json` ），将github上的3个文件内容分别copy到新建的三个文件中
    
    ![img](./img/create-file-1.png)
    
    ![img](./img/create-file-2.png)
    
    ![img](./img/create-file-3.png)

4.  下载和拷贝完成后你的工作目录应该是这个样子的：
    
    ![img](./img/create-file-4.png)
    
        c-projects/
        └── .vscode
          ├── c_cpp_properties.json
          ├── launch.json
          └── tasks.json
    
    **注意** .vscode是隐藏目录，需要使用 `ls -la` 进行查看


<a id="org1ebc142"></a>

# Hello, World

创建你的第一个C程序并运行吧：

1.  新建文件保存为hello.c，并输入如下代码：
    
        #include <stdio.h>
        
        int main(int argc, char** argv) {
            printf("Hello, world!\n");
            return 0;
        }
    
    ![img](./img/hello-code.png)
    
    **注意** 记得保存文件

2.  使用Ctrl+Shift+B(同时按住Ctrl，Shift和B这三个键)进行编译,出现如下结果表示编译成功：
    
    ![img](./img/compile.png)

3.  cygwin下可以看到多出了编译出来的可执行文件：hello
    
        bash-3.2$ ls
        hello.exe           hello.c

4.  通过 `./hello.exe` 执行该文件
    
    ![img](./img/result.png)






# MkDocs+Github+ReadtheDocs

sphinx vs MkDocs 

sphinx 对mk的支持不是很好，所以选择MkDocs。

教程如下:



- [官方链接](https://docs.readthedocs.io/en/latest/intro/getting-started-with-mkdocs.html)

  

- [搭建过程](https://zj-sphinx-github-readthedocs.readthedocs.io/en/latest/)

  
## 搭建本地MkDocs环境，搭建MkDocs工程
MkDocs是一个简单、便捷的工程文档生成器。



* 安装MkDocs

  `sudo pip install mkdocs`

* 进入相应文件夹，设置MkDocs工程

  `mkdocs new .`

* 编译Markdown文件到HTML ,打开http://127.0.0.1.8000/

  `mkdocs serve`

## 上传到github
* 初始化工程

  `git init`

* 添加文件

  `git add .`

* commit 文件

  `git commit -m "update"`

* push到远程仓库

  `git push`

## ReadtheDocs部署
Read the Docs是一个在线文档浏览网站



* 上[readthedocs](https://readthedocs.org/)注册账号，
* 在[Importing Your Documentation](https://readthedocs.org/dashboard/import/)中导入github工程。
* 点击   1.  `管理`->`高级设置`->`save` 2. `集成`-> `添加集成`即可。
* 设置名称：xxx； 则文档访问地址为：xxx.readthedocs.org。

## 学习如何用MkDocs
备注： 运行`mkdocs serve`后，出现端口被占用。先用`lsof -i :8000`查看需要关闭的PID,例(PID为:6832)，查到后再用`kill -9 6832` 就可以关闭了。

教程如下：

[官方User Guide](https://www.mkdocs.org/#adding-pages)



下图为自动生成的目录，单独的配置文件：`mkdocs.yml`、文件夹`docs`、主页面`index.md`

![](https://gitee.com/kbytes/Photos_CSDN/raw/master/1584325678_20200316033247012_1670407676.png)

### 改变主题

 打开`mkdocs.yml`，更换掉`site_name`到你想要的名字即可。

 

### 添加新页面

首先在docs中加入一个md文档。

![](https://gitee.com/kbytes/Photos_CSDN/raw/master/1584325679_20200316035054718_2002839798.png)

再修改`mydocs.yml`文件。



```c
site_name: FOC 笔记
nav:
   - Home: index.md
   - About: about.md
```



### 修改到readthedocs主题



```c++
site_name: FOC 笔记
nav:
   - Home: index.md
   - About: about.md
theme: readthedocs
```
### 更换网站图标

通过官网上的教程，没能成功，把图标转化小也没用。



### 建站

通过`echo "site/" >> .gitignore`可以直接生成文件.gitignore ，并且写入site/
由于已经用了ReadtheDocs,能自动把源文件解析成网站，故目前不需要这一步。



### 后续添加md文件

每次在docs文件夹里加入md文件后，都需要在根目录下yml中加入排版。



### 其他设置

 自行看[yml示例](https://github.com/zimocode/mkdocs-docs-zh/blob/master/mkdocs.yml)，即可明白。




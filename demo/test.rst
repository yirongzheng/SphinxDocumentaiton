Windows系统

================================================
内容写作。采用轻量级的标记语言：reStructuredText
================================================

  安装
.. images:.. images/xxx.jpg

=====================
文档发布工具。Sphinx
=====================

---------
  安装
---------
  
  1. 安装python环境。安装地址：http://www.sphinx-doc.org/en/stable/install.html
     因为sphinx是用python写的，所以如果我们想要使用sphinx来开发技术文档，我们也需要安装python环境。
     安装途径1：可以直接进入上述网址内跳转安装python，如图：
     .. image:: /SphinxDocumentation/images/install_python1.jpg 
     安装途径2：进入python官网安装，网址：https://www.python.org/

  2. 安装sphinx。安装地址：http://www.sphinx-doc.org/en/stable/install.html
     打开网址之后直接翻到下方【Windows: Install Python and Sphinx】
     pip安装：pip是一个python命令，需要先安装pip才能安装sphinx。
       首先进入 https://bootstrap.pypa.io/get-pip.py 并下载这个py文件；
       然后打开cmd并输入命令 ``python get-pip.py`` 然后耐心等待即可。
     sphinx安装：完成了pip安装之后，只需在cmd内输入命令 ``pip install sphinx`` 然后耐心等待即可。


----------
  建立项目
----------
  1. 在桌面新建一个文件夹并命名为SphinxDocumentation

  2. 打开cmd并通过cd命令进入SphinxDocumentation文件夹
       一般来说应该是cd desktop/SphinxDocumentation就能进入

  3. 进入文件夹之后再cmd中输入并运行命令 ``sphinx-quickstart`` 

  4. 接下来会弹出一系列对话框式的选择，y代表yes，n代表no，分别为：
       Separate source and build derectories (y/n) [n]: 
       是否将source文件夹与build文件夹分离，此处一般建议分离，所以在后面填y然后回车即可
       Name prefix for templates and static dir [_]: 
       文件前缀名，此处填下划线_即可
       Project name: 
       给你的项目取个名字，此处填写SphinxDocumentaion作为示例
       Author name(s): 
       此处填写你的名字即可
       Project release []:
       项目发行版本，可填写版本号，此处填写1.0作为示例
       Project language [en]:
       项目语言，填写相关语言的代号，可在http://sphinx-doc.org/config.html#confval-language查询 此处填写en（英语）作为示例
       Source file suffix [.rst]:
       文件后缀名，一般填写.rst即可
       Name of your master document (without suffix) [index]:
       此处一般填写为index即可
       Do you want to use the epub builder (y/n) [n]:
       如果你事后希望能输出epub格式，则填写y
       autodoc: automatically insert docstrings from modules (y/n) [n]:
       doctest: automatically test code snippets in doctest blocks (y/n) [n]:
       intersphinx: link between Sphinx documentation of different projects (y/n) [n]:
       todo: write "todo" entries that can be shown or hidden on build (y/n) [n]:
       coverage: checks for documentation coverage (y/n) [n]:
       imgmath: include math, rendered as PNG or SVG images (y/n) [n]:
       mathjax: include math, rendered in the browser by MathJax (y/n) [n]:
       ifconfig: conditional inclusion of content based on config values (y/n) [n]:
       viewcode: include links to the source code of documented Python objects (y/n) [n]:
       githubpages: create .nojekyll file to publish the document on GitHub pages (y/n) [n]:
       以上全部填写y即可
       Create Makefile? (y/n) [y]:
       Create Windows command file? (y/n) [y]:
       以上两项填写y即可
      此时下方如果出现Finished: An initial directory structure has been created.
      打开桌面上你创建的SphinxDocumentation里你会发现里面多了两个文件夹，一个source，一个build。
      那么说明你的第一个sphinx项目已经创建好啦！


----------------
往项目中添加内容
----------------
  1. 浏览到SphinxDocumentaion/source文件夹，并在这个文件夹下建一个新文件夹，此处建立demo文件夹作为示例。

  2. 在demo文件夹中新建rst文件，此处建立test.rst作为示例。
       tips：可以先新建一个txt文件，然直接修改后缀名为rst即可
  
  3. 用visual studio code（编辑器，后文会有介绍）打开demo.rst，随意输入一段内容并保存。
       rst文件应使用rst语法进行书写，相关语法可参见：http://sphinx-doc-zh.readthedocs.io/en/latest/rest.html

  4. 打开source文件夹中的index.rst文件，并将demo.rst添加到目录树toctree中，如下图：
       .. image:: demo/toctree.jpg
       tips:一是要写对文件路径；二是注意对齐问题，不对齐会报错。
  
  5. 打开cmd并进入到SphinxDocumentaiton文件夹（参照前面的方法）中

  6. 输入并运行命令 ``sphinx-build -b html source build`` 

  7. 编译成功的话，打开SphinxDocumentation文件夹中的build文件夹，里面会有刚刚发布好的静态网页index.html。







  3. 往项目中添加内容
  
  1. 
  4. 修改主题
  
  
  5. 安装ReadtheDoc同款主题
  
  
  6. 由ReadtheDocs执行发布命令
 



当你终于历尽千辛万苦，完成了sphinx本地项目的创建与写作之后，
是不是迫不及待想把自己写的内容发布成一个静态网页了呢？
来跟和我一起做吧~

1. 首先你需要在 **source** 文件夹中创建一个新的文件夹，并把你写的所有的rst文件都放在这个文件夹里；
2. 打开 **source** 文件夹，找到 ``index.rst`` 文件并打开，然后在 ``toctree`` 部分，将自己写的每一个rst文件的完整路径都添加上去；
3. 打开cmd进入到 **sphinx** 项目文件夹，然后执行 ``sphinx-build -b html source build`` 命令，等待一分钟就完成啦~
4. 这时你可以打开 **build** 文件夹里面的 ``index.html`` 文件，你会发现你写的rst文档已经全部都发布好啦~


=========================
协同与版本控制。GitHub
=========================
  安装

=========================
文档托管。Read the Docs
=========================

  注册

如果用sphinx把自己的文档发布成静态网页或pdf当然都很好，但不方便的地方在于，如果我们需要对文档进行修改或是增减内容，
那么我们每做一次修改，都需要用cmd执行一次 ``-build`` 命令，这样显然非常麻烦，
所以我们在这里再介绍一款工具，可以轻松帮助我们对文档进行发布。

1. 进入 ``https://readthedocs.org/`` 并注册一个账号；
2. 在自己的Github上新建一个sphinx项目repo；
3. 将ReadTheDocs（以下简称RTD）账号与自己的Github账号相关联；
4. 在RTD上新建一个project并将其与Github上的sphinx repo相关联；
5. 下载Github Desktop桌面版，登陆，然后把sphinx repo  ``clone`` 到本地；
6. 打开 **sphinx repo本地仓库** 所在文件夹，把 **source** 文件夹中的 ``conf.py`` ``index.rst`` 以及自己建立的用于 ``写rst文档的文件夹`` 放到本地仓库然后再 ``push`` ；
7. 之后每次需要对内容进行增删改等操作时，直接在本地仓库中进行修改，然后把文件名和路径添加到 ``index.rst`` 里，然后再 ``push`` 上去就好啦~
8. 这时你再打开RTD网页，点击右上角的 **阅读文档** 就会发现，自己在本地做的修改已经自动发布啦~是不是很方便！

当在线repo中有任何变动时，RTD都能检测到并帮你发布，妈妈再也不用担心我每次发布都要 ``-build`` 一次啦~


===============================
写作工具。MS Visual Studio Code
===============================
  安装 

教程目标
1. 能够通过这一套流程完成一篇技术文档从开发到呈现。
2. 能够在学习教程的过程中对技术传播的概念有一个总体了解。

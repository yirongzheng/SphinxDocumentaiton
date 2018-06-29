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
..  image:: /SphinxDocumentation/images/install_python1.jpg 

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
..  image:: demo/toctree.jpg

       tips:一是要写对文件路径；二是注意对齐问题，不对齐会报错。
  
  5. 打开cmd并进入到SphinxDocumentaiton文件夹（参照前面的方法）中

  6. 输入并运行命令 ``sphinx-build -b html source build`` 

  7. 编译成功的话，打开SphinxDocumentation文件夹中的build文件夹，里面会有刚刚发布好的静态网页index.html。


-----------
  修改主题
-----------
  1. 用vs code打开source文件夹中的conf.py文件

  2. 找到主题配置行html_theme = 'alabaster' 

  3. 从内置主题中挑选需要的主题，如bizstyle，并将其修改为 html_theme = 'bizstyle',然后保存。
       官网给出了10种配置好的内置主题样式，分别是：alabaster, classic, sphinxdoc, scrolls, agogo, traditional, nature, haiku, pyramid, bizstyle。
       另外，也可以自行配置想要的主题。
       网址：http://www.sphinx-doc.org/en/master/theming.html#using-a-theme 

  4. 打开cmd并进入到SphinxDocumentation文件夹，重新运行-build命令，则可得到新主题的样式的文档。

  5. 如果喜欢readthedocs.org（也就是课程文档所使用的主题）的话，可以按照如下方式安装。
       打开cmd，输入并运行指令 ``pip install sphinx_rtd_theme`` 
       安装好了之后，按照上述步骤，讲conf.py中的主题配置行修改为html_theme = 'sphinx_rtd_theme'，
       然后再重新运行sphinx-build命令发布即可。

  如果到这一步你都能够顺利完成，那么恭喜你，你已经可以通过sphinx来开发属于你自己的技术文档，并通过cmd发布为本地的静态网页。
  那么如果我想把我写的文档发布到公网应该怎么办呢？
  我如何利用sphinx来创建自己的博客并实时更新内容呢？
  这就是这篇教程接下来要讨论的：GitHub协同与版本控制。


=========================
协同与版本控制。GitHub
=========================

--------
  安装
--------
  1. 官网注册：https://github.com/ 
       首先在官网注册好一个GitHub帐号
       第一次注册登陆，首页应该会弹出‘hello world guide’，这相当于一个快速新手指南，教你如何建立自己的repo，如何fork别人的repo等，
       建议新手第一次登陆之后不要直接跳过这个部分，最好跟着这个指南操作一次。

  2. GitHub Desktop下载：https://desktop.github.com/
       进入上面的网址，下载并安装GitHub Desktop桌面端
       下载好了之后打开并登陆自己的GitHub帐号

-----------
  创建repo
-----------
  1. 打开GitHub网页端，创建一个新repo，并命名为 SphinxDocumentation ，与本地的项目文件夹相对应；

  2. 打开GitHub Desktop本地客户端，点击左上角 File-Clone repository 如下图：
..  images:: /images/clonerepo.jpg

  3. 在弹出的新窗口中选择刚刚在GitHub网页端创建的新repo SphinxDocumentation，然后点击确定，如图：
     .. images:: /images/clonerepo2.jpg
  
  4. 这时，GitHub Desktop会把网页版GitHub里我们创建的新repo clone到本地，

--------
  同步
--------
  1. clone完成之后，点击中央的 open this repository 可以打开本地repo对应的文件夹，如图：
     .. images:: /images/openrepo.jpg

  2. 这时，再打开之前在本地创建好的SphinxDocumentation项目文件夹，然后把整个source文件夹拷贝或移动到GitHub本地仓库的文件夹中去。

  3. 此时GitHub Desktop界面会发生变化，这是因为本地仓库发生任何变化GitHub desktop都能检测到并显示在界面上，如下图：
     .. images:: /images/committomaster.jpg 

  4. 在左下角summary输入框中随意输入任意字符，此处输入1.0作为版本号来记录这次变化，然后点击 **commit to master**

  5. commit完之后，界面又恢复了原来的样子，此时你对本地仓库中的文件所作的修改已经被GitHub desktop记录好了。
      但现在只是在本地完成了修改，如何同步到GitHub网页端呢？
      这也是为什么我们要下载GitHub Desktop的原因之一：同步与版本控制;
      点击上方黑色栏中间的 **push origin**，将本地所作的修改push到GitHub网页端完成同步，如图：
      .. images:: /images/push.jpg 
  
  6. 打开GitHub网页端，点开刚刚创建的SphinxDocumentation repo就能看到从本地push上去的所有内容啦！
  
--------
  发布
--------
  1. 点击上方**setting**，在这个界面你还可以修改项目的名字
      .. images:: /images/setting1.jpg
      滚轮滚到中下方，找到**GitHub Pages**，点开下拉选项并选择**master branch**然后点击**save**保存。
      .. images:: /images/setting2.png 
      这时页面会自动刷新，你再下拉到**GitHub Pages**部分会发现里面多了一个url链接，这就是你生成的公网可访问的连接啦。
      .. images:: /images/setting3.jpg 
      点击这个链接，你就能在网页中打开你写好的技术文档。
  2. 把这个链接分享给别人，他们也一样能在他们的电脑上打开这个链接并看到你写的技术文档。


  截至到这一步，我们已经可以利用sphinx在本地创建技术文档并通过cmd生成本地静态网页，然后通过GitHub将我们创建的文档实现公网可访问。
  但我们仍然没有解决之前提到的更新维护问题，我们每对文档做一次增删改之类的更新或迭代，我们都需要在本地通过cmd的-build命令编译一次，然后再push到GitHub上去，这样操作显然非常麻烦。
  为了解决这个问题，极大提高文档的可维护性，轻松帮助我们对文档进行发布，我们就需要用到下面所说的文档托管：**Read the Docs**

     
=========================
文档托管。Read the Docs
=========================
---------
  注册
---------
  1. 注册：https://readthedocs.org/
     打开上面的网址并进行注册，填写好相关信息
  2. 与GitHub关联。
     注册并登陆之后，需要将readthedocs账户与GitHub账户进行关联，按照页面指示进行相关操作即可。

--------------
  创建关联项目
--------------
  1. 与GitHub账户关联好之后，readthedocs将能够读取到你在GitHub上的所有repo；
  2. 点击**import a project**
     .. images:: /images/importproject1.jpg
  3. 在出现的窗口中选择我们要与readthedocs进行关联的repo即可，此处选择SphinxDocumentation,然后点击右边的**+**
     .. images:: /images/importproject2.jpg
  4. 如果是选择手动导入代码库的话，可以到GitHub网页版，打开要关联的repo，点击右方的**clone or download**，
     然后把url复制下来，回到readthedocs网页，并把url粘贴到相对应的位置，再填好相应信息进行import即可。
     .. images:: /images/importproject3.jpg
  





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

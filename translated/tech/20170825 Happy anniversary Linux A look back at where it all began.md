周年快乐，Linux：回顾这一切的开始
============================================================

### 通过安装 SLS 1.05 展示了 Linux 内核在这 26 年间走过了多远。 

![Happy anniversary, Linux: A look back at where it all began](https://opensource.com/sites/default/files/styles/image-full-size/public/lead-images/happy_birthday_tux.png?itok=GoaC0Car "Happy anniversary, Linux: A look back at where it all began")

图片来源：[litlnemo][25]。由 Opnesource.com 修改。[CC BY-SA 2.0.][26]

我第一次安装 Linux 是在 1993年。那时我跑的是 MS-DOS，但我真的很喜欢学校机房电脑的 Unix 系统，就是在那里度过了我大学本科期间的大部分时间。 当我听说了 Linux，一个 Unix 的免费版本，可以在我家的 386 电脑上运行的时候，我立刻就想要尝试。我的第一个 Linux 发行版是 [Softlanding Linux System][27] (SLS) 1.03, 带有 补丁级别为 11 的 0.99 alpha 版本的 Linux 内核。高达 2 MB 的内存需求，如果你想要编译项目需要 4 MB，运行 X windows 则需要 8 MB。

更多 Linux 资源

*   [ Linux 是什么？][1]

*   [ Linux 容器是什么？][2]

*   [现在下载：Linux 命令速查表][3]

*   [高级 Linux 命令速查表][4]

*   [我们最新的 Linux 文章][5]

我认为 Linux 相较于 MS-DOS 的世界是一个巨大的进步。 尽管 Linux 缺乏广泛的应用以及运行在 MS-DOS 上的游戏，但我发现 Linux 带给我的是巨大的灵活性。不像 MS-DOS ，现在我可以进行真正的多任务，同时运行不止一个程序。并且 Linux 提供了丰富的工具，包括一个 C 语言编译器，让我可以构建自己的项目。

一年后，我升级到了 SLS 1.05，它支持全新的 Linux 内核 1.0。 更重要的，Linux 引入了内核模块。通过内核模块，你不再需要为支持新硬件而编译整个内核；取而代之，加载一个 包含在内的 Linux 内核模块之一。在 SLS 1.05 的发行自述文件中包含这些关于模块的注释:

> 内核模块化旨在正视减少并最终消除重新编译内核的要求，无论是变更、修改设备驱动或者为了动态访问不常用的驱动。更为重要的是，也许，个别工作小组的工作不再影响到内核的正确开发。事实上，这让现在官方内核的二进制版本成为了可能。

在 8 月 25 日，Linux 内核将迎来它的第 26 周年（译：已经过去了 =.= ）。为了庆祝，我重新安装了 SLS 1.05 来提醒自己 Linux 1.0 内核是什么样子，去认识 Linux 自二十世纪 90 年代以来走了多远。和我一起踏上 Linux 的怀旧之旅吧！

### 安装

SLS 是第一个真正的 “发行版”，因为它包含一个安装程序。 尽管安装过程并不像现代发行版一样顺畅。 不能从 CD-ROM 启动安装，我需要从软盘启动我的系统，然后从 **login** 提示中运行安装程序。

### [install1.png][6]

![Installing SLS 1.05 from the login prompt](https://opensource.com/sites/default/files/u128651/install1.png "Installing SLS 1.05 from the login prompt")

在 SLS 1.05 中支持彩色的文本模式安装器有一段简洁的功能介绍。当我选择彩色模式时，安装器切换到一个带有黑色文字的亮蓝色背景，不再是我们祖辈们使用的原始的普通黑白文本。

### [install2.png][7]

![Color-enabled text-mode installer in SLS 1.05](https://opensource.com/sites/default/files/u128651/install2.png "Color-enabled text-mode installer in SLS 1.05")

 SLS 安装器是一个简单的事件，从屏幕底部滚动文本，但这就是它的工作。通过响应一些简单的提示，我能够创建一个 Linux 分区，挂载上 ext2 文件系统，并安装 Linux 。 安装包含了 X windows 和开发工具的 SLS 1.05，需要大约 85 MB 的磁盘空间。依照今天的标准这听起来可能不是很多，但在 Linux 1.0 出来的时候，120 MB 的硬件设备仍然很常见。

### [install10.png][8]

![Creating a partition for Linux, putting an ext2 filesystem on it, and installing Linux](https://opensource.com/sites/default/files/u128651/install10.png "Creating a partition for Linux, putting an ext2 filesystem on it, and installing Linux")

### [firstboot1.png][9]

![First boot](https://opensource.com/sites/default/files/u128651/firstboot1.png "First boot")

### 系统级别

当我第一次启动到 Linux 时，我的内存引发了一些关于早期版本 Linux 的系统事件。首先，Linux 没有占据很多的空间。在启动系统之后运行一些程序来检查的时候，Linux 占用不到 4 MB 的内存。在一个拥有 16MB 内存的系统中，这就意味着节省了很多内存用来运行程序。

### [uname-df.png][10]

![Checking out the filesystem and available disk space](https://opensource.com/sites/default/files/u128651/uname-df.png "Checking out the filesystem and available disk space")

熟息的 **/proc** 元文件系统存在于 Linux 1.0，尽管对比我们今天看到的现代系统它并不能提供许多信息。在 Linux 1.0， **/proc** 包含一些界面来探测基本的系统状态像是 **meminfo** 和 **stat**。

### [proc.png][11]

![The familiar /proc meta filesystem](https://opensource.com/sites/default/files/u128651/proc.png "The familiar /proc meta filesystem")

在这个系统上的 **/etc** 文件目录非常简单。特别的是，SLS 1.05 带来了来自 [BSD Unix][28] 的 **rc** 脚本来控制系统启动。 初始化是通过 **rc** 脚本，由 **rc.local** 文件来定义调整本地系统。后来，许多 Linux 发行版采用了很相似的来自 [Unix System V][29] 的 **init** 脚本，然后是 [systemd][30] 初始化系统。

### [etc.png][12]

![The /etc directory](https://opensource.com/sites/default/files/u128651/etc.png "The /etc directory")

### 你能做些什么

 随着系统的启动运行，接下来就该工作了，那么，在这样的早期 Linux 系统上你能做些什么？

让我们从基本的文件管理开始。 每次在你登录的时候，SLS 会提醒你的是 Softlanding menu shell (MESH)，这是一个文件管理程序，现代用户们可能认出它和 [Midnight Commander][31] 很相似。 二十世纪 90 年代的用户们可能拿 MESH 与更为接近的 [Norton Commander][32] 相比，这个可以说是在 MS-DOS 上最流行的第三方文件管理程序。

### [mesh.png][13]

![The Softlanding menu shell (MESH)](https://opensource.com/sites/default/files/u128651/mesh.png "The Softlanding menu shell (MESH)")

在 SLS 1.05 中包含一些相对全屏的应用程序位于 MESH 的一侧。但你可以找到熟息的用户工具，包括 Elm 邮件阅读器，GNU Emacs 可编程编辑器，以及古老的 Vim 编辑器。

### [elm.png][14]

![Elm mail reader](https://opensource.com/sites/default/files/u128651/elm.png "Elm mail reader")

### [emacs19.png][15]

![GNU Emacs programmable editor](https://opensource.com/sites/default/files/u128651/emacs19.png "GNU Emacs programmable editor")

SLS 1.05 甚至包含了一个可以让你在终端玩的俄罗斯方块版本。

### [tetris.png][16]

![Tetris for terminals](https://opensource.com/sites/default/files/u128651/tetris.png "Tetris for terminals")

在二十世纪 90 年代，住宅网络的接入是通过拨号连接的，所以 SLS 1.05 包含 Minicom 调制解调器-拨号程序。Minicom 提供一个与调制解调器直接连接并允许用户控制 Hayes 调制解调器的 **AT** 命令进行一些像是拨号或挂电话这样的基础功能。Minicom 同样支持宏和其他简单功能来使连接你的本地调制解调器池更容易。

### [minicom.png][17]

![Minicom modem-dialer application](https://opensource.com/sites/default/files/u128651/minicom.png "Minicom modem-dialer application")

但如果你想要写一篇文档时怎么办？ SLS 1.05 的存在要比 LibreOffice 或者 OpenOffice 早很长时间。在二十世纪 90 年代，Linux 还没有这些应用。相反，如果你想要使用一个文字处理器，可能需要引导你的系统进入 MS-DOS，然后运行你喜欢的文字处理器程序，如 WordPerfect 或者共享软件 GalaxyWrite。

但是所有的 Unix 系统都包含一个简单的文本格式设置程序，叫做 nroff 和 troff。在 Linux 系统中，他们被合并成 GNU groff 包，并且 SLS 1.05 包含了 groff 的一个版本。我在 SLS 1.05 上的一项测试就是用 nroff 生成一个简单的文本文档。

### [paper-me-emacs.png][18]

![A simple nroff text document](https://opensource.com/sites/default/files/u128651/paper-me-emacs.png "A simple nroff text document")

### [paper-me-out.png][19]

![nroff text document output](https://opensource.com/sites/default/files/u128651/paper-me-out.png "nroff text document output")

### 运行 X windows

获取安装 X windows 并不容易，由于 SLS 安装文件承诺：

> 在你的 PC 上获取安装 X windows 可能会有一些发人深省的体验，主要是因为 PC 的显示卡类型太多。Linux X11 仅支持 VGA 类型的显示卡，但在许多类型的 VGA 中仅有个别的某些类型是完全支持的。SLS 存在两种 X windows 服务器。全彩的 XFree86，支持一些或所有 ET3000, ET400, PVGA1, GVGA, Trident, S3, 8514, Accelerated cards, ATI plus 等。
> 
> 另一个服务器 XF86_Mono，能够工作在几乎所有的 VGA 卡上，但只提供单色模式。因此，相比于彩色服务器，它会占用更少的内存并拥有更快的速度。当然就是看起来不怎么漂亮。
> 
> X windows 的批量配置信息存储在目录 "/usr/X386/lib/X11/"。需要注意的是，"Xconfig" 文件为监视器和显示卡定义了时序。默认情况下，X windows 设置使用彩色服务器，如果彩色服务器出现问题，你可以切换到单色服务器 x386mono，因为它已经支持各种标准的 VGA。本质上，就是创建链接到 /usr/X386/bin/X。
> 
> 只需要编辑 Xconfig 来设置鼠标驱动类型和时序，然后键入 "startx"。

这些听起来令人困惑，但它就是这样。手工配置 X windows 真的可以是一个发人深省的体验。幸好，SLS 1.05 包含了 syssetup 程序来帮你确定系统组件的种类，包括了 X windows 的显示设置。在一些提示过后，经过一些实验和调整，最终我成功启动了 X windows！

### [syssetup.png][20]

![The syssetup program](https://opensource.com/sites/default/files/u128651/syssetup.png "The syssetup program")

这就是 1994 年的 X windows，并不存在桌面的概念。我的选项是 FVWM （一个虚拟窗口管理器）或 TWM （选项卡式的窗口管理器）。TWM 直接建立并提供一个功能简单的图形环境。

### [twm_720.png][21]

![TWM](https://opensource.com/sites/default/files/u128651/twm_720.png "TWM")

### 关机

已经尽可能多的沉浸在我的 Linux 起源的探索中，最终是时候回到我的现代桌面上了。最初我跑 Linux 的是一台仅有 8MB 内存和 一个 120MB 硬盘驱动器的 32位 386 电脑，而我现在的系统已经足够强大了。拥有双核 64 位 Intel Core i5 处理器，4 GB 内存和一个 128 GB 的固态硬盘，我可以在我的运行着 Linux 内核 4.11.11 的系统上做更多事情。那么，在我的 SLS 1.05 的实验结束之后，是时候离开了。

### [shutdown-h.png][22]

![Shutting down](https://opensource.com/sites/default/files/u128651/shutdown-h.png "Shutting down")

再见，Linux 1.0。很高兴看到你的茁壮成长。

--------------------------------------------------------------------------------

via: https://opensource.com/article/17/8/linux-anniversary

作者：[Jim Hall  ][a]
译者：[softpaopao](https://github.com/softpaopao)
校对：[校对者ID](https://github.com/校对者ID)

本文由 [LCTT](https://github.com/LCTT/TranslateProject) 原创编译，[Linux中国](https://linux.cn/) 荣誉推出

[a]:https://opensource.com/users/jim-hall
[1]:https://opensource.com/resources/what-is-linux?intcmp=70160000000h1jYAAQ&utm_source=intcallout&utm_campaign=linuxcontent
[2]:https://opensource.com/resources/what-are-linux-containers?intcmp=70160000000h1jYAAQ&utm_source=intcallout&utm_campaign=linuxcontent
[3]:https://developers.redhat.com/promotions/linux-cheatsheet/?intcmp=70160000000h1jYAAQ&utm_source=intcallout&utm_campaign=linuxcontent
[4]:https://developers.redhat.com/cheat-sheet/advanced-linux-commands-cheatsheet?intcmp=70160000000h1jYAAQ&utm_source=intcallout&utm_campaign=linuxcontent
[5]:https://opensource.com/tags/linux?intcmp=70160000000h1jYAAQ&utm_source=intcallout&utm_campaign=linuxcontent
[6]:https://opensource.com/file/365166
[7]:https://opensource.com/file/365171
[8]:https://opensource.com/file/365176
[9]:https://opensource.com/file/365161
[10]:https://opensource.com/file/365221
[11]:https://opensource.com/file/365196
[12]:https://opensource.com/file/365156
[13]:https://opensource.com/file/365181
[14]:https://opensource.com/file/365146
[15]:https://opensource.com/file/365151
[16]:https://opensource.com/file/365211
[17]:https://opensource.com/file/365186
[18]:https://opensource.com/file/365191
[19]:https://opensource.com/file/365226
[20]:https://opensource.com/file/365206
[21]:https://opensource.com/file/365236
[22]:https://opensource.com/file/365201
[23]:https://opensource.com/article/17/8/linux-anniversary?rate=XujKSFS7GfDmxcV7Jf_HUK_MdrW15Po336fO3G8s1m0
[24]:https://opensource.com/user/126046/feed
[25]:https://www.flickr.com/photos/litlnemo/19777182/
[26]:https://creativecommons.org/licenses/by-sa/2.0/
[27]:https://en.wikipedia.org/wiki/Softlanding_Linux_System
[28]:https://en.wikipedia.org/wiki/Berkeley_Software_Distribution
[29]:https://en.wikipedia.org/wiki/UNIX_System_V
[30]:https://en.wikipedia.org/wiki/Systemd
[31]:https://midnight-commander.org/
[32]:https://en.wikipedia.org/wiki/Norton_Commander
[33]:https://opensource.com/users/jim-hall
[34]:https://opensource.com/users/jim-hall
[35]:https://opensource.com/article/17/8/linux-anniversary#comments
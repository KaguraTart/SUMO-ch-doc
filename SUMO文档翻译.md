SUMO使用手册

​    SUMO（Simulation of Urban MObility），是一个开放源码，高度便携，微观和连续交通仿真封装设计来处理大型网络。它允许包括行人在内的多式联运模拟，并带有用于场景创建的大量工具。它主要由员工开发的运输系统研究，所在德国航空航天中心。SUMO已获得EPL 2.0的许可。

目录

[第一章 介绍... 3](#_Toc73307450)

[1   1 特征... 3](#_Toc73307451)

[2   2 包含的运用... 3](#_Toc73307452)

[3   3 软件设计标准... 4](#_Toc73307453)

[第二章 基本用法... 4](#_Toc73307454)

[1   文档中符号... 4](#_Toc73307455)

[1.1     XML范例... 4](#_Toc73307456)

[1.2     引用的数据类型... 5](#_Toc73307457)

[1.3     引用的文件类型... 5](#_Toc73307458)

[2   所需电脑技能... 5](#_Toc73307459)

[2.1     使用文字编辑器... 5](#_Toc73307460)

[2.2     处理文件和文件夹.. 6](#_Toc73307461)

[2.3     从命令行运行程序.. 6](#_Toc73307462)

[2.4     SUMO 0.12.3和更高版本... 6](#_Toc73307463)

[2.5     配置环境变量... 6](#_Toc73307464)

[3   安装SUMO.. 6](#_Toc73307465)

[4   使用SUMO命令行语句... 7](#_Toc73307466)

[4.1     从命令行使用SUMO.. 7](#_Toc73307467)

[4.2     在命令行上设置选项... 7](#_Toc73307468)

[4.3     配置文件... 7](#_Toc73307469)

[4.4     配置文件的命名约定... 8](#_Toc73307470)

[4.5     配置文件与命令行参数.. 8](#_Toc73307471)

[4.6     生成配置文件，模板和方案.. 8](#_Toc73307472)

[4.7     配置文件中的环境变量.. 9](#_Toc73307473)

[4.8     常用选项... 9](#_Toc73307474)

[4.9     生成和读取文件... 10](#_Toc73307475)

[4.10    写文件... 10](#_Toc73307476)

[4.11    时间值... 11](#_Toc73307477)

[4.12    从命令行使用Python工具.. 11](#_Toc73307478)

[5   教程... 11](#_Toc73307479)

[5.1     初学者教程... 11](#_Toc73307480)

[6   验证应用程序XML的输入.. 30](#_Toc73307481)

[6.1     验证XML输入... 30](#_Toc73307482)

[6.2     添加架构声明... 31](#_Toc73307483)

[第三章 网络构建... 31](#_Toc73307484)

[1   SUMO道路网介绍... 31](#_Toc73307485)

[1.1     网络格式... 32](#_Toc73307486)

[2   抽象网络生成... 37](#_Toc73307487)

[2.1     网格状网络... 37](#_Toc73307488)

[2.2     类蜘蛛网络... 38](#_Toc73307489)

[2.3     随机网络... 39](#_Toc73307490)

[3   使用netconvert导入网络.. 39](#_Toc73307491)

[4   使用netedit创建和修改网络... 39](#_Toc73307492)

[4.1     输入... 39](#_Toc73307493)

[4.2     输出... 40](#_Toc73307494)

[4.3     热键... 40](#_Toc73307495)

[4.4     处理菜单... 42](#_Toc73307496)

[5   高程数据建立... 42](#_Toc73307497)

[6   坐标... 43](#_Toc73307498)

[6.1     检查地理坐标... 43](#_Toc73307499)

[6.2     坐标转换... 43](#_Toc73307500)

[6.3     坐标输出... 43](#_Toc73307501)

[第四章 需求模型... 43](#_Toc73307502)

[1   SUMO需求建模简介.. 43](#_Toc73307503)

[2   车辆定义车辆类型路线.. 44](#_Toc73307504)

[3   使用netedit定义流量需求.. 44](#_Toc73307505)

[3.1     路线... 44](#_Toc73307506)

[3.2     车辆... 45](#_Toc73307507)

[3.3     车辆类型... 48](#_Toc73307508)

[3.4     人数... 49](#_Toc73307509)

[4   模拟公共交通... 49](#_Toc73307510)

[5   模拟个人和旅行链.. 49](#_Toc73307511)

[6   物流模拟... 49](#_Toc73307512)

[7   最短或最佳路径路由... 49](#_Toc73307513)

[8   多式联运... 49](#_Toc73307514)

[9   仿真中的布线... 49](#_Toc73307515)

[10     计算动态用户分配.. 50](#_Toc73307516)

[10.1    迭代的任务（动态用户平衡）... 50](#_Toc73307517)

[10.2    路线选择算法... 50](#_Toc73307518)

[10.3    中止... 51](#_Toc73307519)

[10.4    使用范围... 51](#_Toc73307520)

[10.5    及时分配... 51](#_Toc73307521)

[11      产生行人交通需求.. 51](#_Toc73307522)

[12     生成车辆类型分布以对车队进行建模.. 51](#_Toc73307523)

[12.1    使用工具createVehTypeDistribution.py. 51](#_Toc73307524)

[12.2    extractTest.py. 52](#_Toc73307525)

[12.3    generateParkingLots.py. 52](#_Toc73307526)

[12.4    generateStationEdges.py. 53](#_Toc73307527)

 

 

# 第一章 介绍

SUMO是一个开源的，微观的，多模态交通仿真。它允许模拟由单个车辆组成的给定交通需求如何在给定道路网络中移动。该模拟允许解决大量交通管理主题。它纯粹是微观的：每辆车都经过明确建模，拥有自己的路线，并通过网络进行单独移动。默认情况下，模拟是确定性的，但是引入随机性有多种选择。

## 1    1 特征

-  包括准备和执行流量模拟所需的所有应用程序（网络和路由导入，DUA，模拟）

- 模拟

- - 空间连续且时间离散的车辆运动
  - 不同的车辆类型
  - 多车道街道，车道变更
  - 不同的通行权规则，交通信号灯
  - 快速的openGL图形用户界面
  - 管理具有多个10.000边缘（街道）的网络
  - 快速的执行速度（在一台1GHz的计算机上，每秒可更新100.000次车辆）
  - 在运行时与其他应用程序的互操作性
  - 全网，基于边缘，基于车辆和基于检测器的输出
  - 支持基于人的联程旅行

- 网络导入

- - 导入VISUM，Vissim，Shapefile，OSM，RoboCup，MATsim，OpenDRIVE和XML描述
  - 缺失值通过启发式方法确定

- 路由

- - 微观路线-每辆车都有自己的一辆
  - 不同的动态用户分配算法

- 高便携性

- - 仅使用标准C      ++和可移植库
  - 存在Windows主要Linux发行版的软件包

- 通过仅使用XML数据实现高互操作性

- 开源（EPL2.0）

 

## 2    2 包含的运用

| **应用名称**                                                 | **简短的介绍**                                               |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| sumo                                                         | 没有可视化的微观模拟；命令行应用                             |
| Suno-gui                                                     | 具有图形用户界面的微观模拟                                   |
| [netconvert](https://sumo.dlr.de/docs/netconvert.html)       | 网络导入器和生成器；读取不同格式的道路网络并将其转换为SUMO格式 |
| [netedit](https://sumo.dlr.de/docs/Netedit/index.html)       | 图形网络编辑器。                                             |
| [netgenerate](https://sumo.dlr.de/docs/netgenerate.html)     | 生成用于SUMO仿真的抽象网络                                   |
| duaraoter                                                    | 通过网络计算最快的路线，导入不同类型的需求描述。执行DUA      |
| [jtrrouter](https://sumo.dlr.de/docs/jtrrouter.html)         | 使用路口转弯百分比计算路线                                   |
| [dfrouter](https://sumo.dlr.de/docs/dfrouter.html)           | 根据感应环路测量结果计算路线                                 |
| [marouter](https://sumo.dlr.de/docs/marouter.html)           | 执行宏观分配                                                 |
| [od2trips](https://sumo.dlr.de/docs/od2trips.html)           | 将O / D矩阵分解为单个车辆行程                                |
| [polyconvert](https://sumo.dlr.de/docs/polyconvert.html)     | 从不同的格式导入兴趣点和多边形，并将其转换为可由[sumo-gui](https://sumo.dlr.de/docs/sumo-gui.html)可视化的描述 |
| [activitygen](https://sumo.dlr.de/docs/activitygen.html)     | 根据模型人口的流动意愿产生需求                               |
| [emissionsMap](https://sumo.dlr.de/docs/Tools/Emissions.html#emissionsmap) | 生成发射图                                                   |
| [missionsDrivingCycle](https://sumo.dlr.de/docs/Tools/Emissions.html#emissionsdrivingcycle) | 根据给定的驾驶周期计算排放值                                 |
| [Additional Tools](https://sumo.dlr.de/docs/Tools/index.html) | 有些任务不需要编写大型应用程序。这些工具可能涵盖针对不同问题的几种解决方案。 |

## 3    3 软件设计标准

达到了两个主要的设计目标：软件应快速且可移植。因此，最初的版本被开发为只能从命令行运行-最初没有提供图形界面，并且必须手动插入所有参数。这样可以避免缓慢的可视化，从而提高执行速度。同样，由于这些目标，该软件被分为几个部分。它们中的每一个都有特定的目的，必须单独运行。这使SUMO与其他仿真程序包有所不同，例如，动态用户分配是在仿真程序内部进行的，而不是通过此处的外部应用程序进行的。这种拆分使包中的每个应用程序都更容易扩展，因为每个应用程序都比执行所有操作的单片应用程序小。还，它允许使用更快的数据结构，每种数据结构都已针对当前目的进行了调整，而不是使用复杂的，镇流器加载的数据结构。尽管如此，与其他仿真程序包相比，这仍使SUMO的使用有点不舒服。由于还有其他事情要做，因此我们目前尚未考虑对集成方法进行重新设计。

# 第二章 基本用法

## 1    文档中符号

### 1.1  XML范例

显示了XML元素和属性like this。它们的值（如果可变） <LIKE THIS>。完整的XML文件示例如下所示：

<myType>

  <myElem myAttr1="0" myAttr2="0.0"/>

  <myElem myAttr1="1" myAttr2="-500.0"/>

</myType>

### 1.2  引用的数据类型

<BOOL>：一个布尔值，使用“ t”或“ true”以及“ f”或“ false”进行编码

<INT>：一个整数值，可以为负数

<UINT>：无符号整数值，必须> = 0

<FLOAT>：浮点数

<TIME>：时间，以秒为单位；允许使用小数，例如“ 12.1”

<STRING>：任何字符串，但仅使用ASCII字符

<ID>：不得包含以下字符的字符串：'＃'

<FILE>或<FILENAME>：文件的（相对或绝对）路径；另请参阅#Referenced文件类型

<PATH>：（相对或绝对）路径（通常到文件夹）

<COLOR>：以'，'分隔的四倍浮点数（<FLOAT>，<FLOAT>，<FLOAT>，<FLOAT>），它们描述了红色，绿色，蓝色和alpha分量，范围从0.0到1.0（ alpha组件是可选的），或者列表可能包含0-255范围内的整数。请注意，分隔符必须是逗号，并且不允许有空格。也可以使用带有HTML颜色代码的单个字符串或基本颜色（“红色”，“绿色”，“蓝色”，“黄色”，“青色”，“洋红色”，“黑色”， “白色”，“灰色”）。“ random”的值将分配随机颜色。

<2D-POSITION>：两个以'，'分隔的浮点数（<FLOAT>，<FLOAT>），分别描述x偏移和y偏移。z隐式为0

<3D-POSITION>：三个以'，'分隔的浮点数（<FLOAT>，<FLOAT>和<FLOAT>），分别描述x-，y-和z-offset。

<POSITION-VECTOR>：2D或3D位置的列表，以'分隔。即（<2D-POSITION> <2D-POSITION>，<3D-POSITION>）

<2D-BOUNDING_BOX>：四个以'，'分隔的浮点数（<FLOAT>，<FLOAT>，<FLOAT>，<FLOAT>），描述了x最小值，y最小值，x最大值和y最大值

<PROJ_DEFINITION>：一个字符串，其中包含proj.4使用的投影定义；请注意，您必须将定义字符串嵌入引号中。

### 1.3  引用的文件类型

<NETWORK_FILE>：由netgenerate或 netconvert构建 的SUMO网络文件

<ROUTES_FILE>： 由duarouter或 jtrrouter或手动构建的SUMO路由文件

<TYPE_FILE>：手动构建或下载的SUMO边缘类型文件

<OSM_FILE>： 从OpenStreetMap导出的OpenStreetMap文件

<SUMO_HOME>是您将SUMO程序包保存到的路径。

## 2    所需电脑技能

### 2.1  使用文字编辑器

SUMO需要配置文件和数据文件才能正确执行。可以使用文本编辑器创建和编辑这些文件。在Windows上，您可以通过以下方式打开基本的文本编辑器：按住win＋R并输入notepad。

  记事本是一个非常基本的文本编辑器。通过切换到具有更多功能的编辑器，可以提高舒适度和生产率。考虑使用 Notepad ++或 vim（译者也建议可以使用vscode），还可以看到文本编辑器的这种比较。

### 2.2  处理文件和文件夹

要使用SUMO所需的各种文件，您必须能够在文件系统上找到它们。对于初学者，请在此处或 此处了解有关使用Windows资源管理器的信息。

### 2.3  从命令行运行程序

SUMO由不同的模拟相关的任务，许多独立的程序（所有可以找到的单独程序的引用 在这里和其他工具的列表在这里）。只有sumo-gui（sumo-gui.exe）和netedit（netedit.exe）具有图形用户界面（GUI）。所有其他程序必须从命令行调用。

首先，您必须打开命令行。在Windows上，必须启动“ cmd.exe ”（开始-> Windows系统->命令提示符）。您也可以按Win+R键，然后在Windows的任务栏上的搜索框中输入cmd或搜索cmd。

应出现一个黑色的窗口。这是您的命令行。从0.12.3版开始，您还可以双击文件start-command-line.bat（另请参见 下文）以打开一个命令行，并设置了有用的环境变量（可以将其与所有其他sumo可执行文件放在同一文件夹中） 。使用Linux时，您必须启动一个终端（例如xterm）。

命令行允许您通过键入程序名称和程序选项来启动程序。由于这是自动化的，因此对于重复性任务而言，使用GUI可能会更舒适。命令看起来像这样：

netconvert --node-files=hello.nod.xml --edge-files=hello.edg.xml --output-file=hello.net.xml

这里netconvert是程序的名称，以及该程序的命令集的其余选项。

### 2.4  SUMO 0.12.3和更高版本

在您的SUMO版本中（您下载的所有SUMO文件和文件夹），都有一个bin目录。此目录包含一个名为的批处理文件 start-command-line.bat。该批处理文件将启动命令行，并确保您可以执行SUMO程序。

1. 通过双击执行start-command-line.bat
2. 使用命令[cd](https://ss64.com/nt/cd.html)导航到包含您的配置和网络文件的目录（更改目录）
3. 输入诸如

netconvert --node-files=hello.nod.xml --edge-files=hello.edg.xml --output-file=hello.net.xml

### 2.5  配置环境变量

\1. 右键点击我的电脑à属性à高级系统设置à环境变量à系统变量

\2. 应该会出现一个小窗口。在用户变量下（译者建议在系统变量下添加），选择PATH（或Path -Windows环境变量不区分大小写），然后单击编辑。如果不存在这样的变量，则必须使用New -Button创建它。

\3. 附加;C:\Program Files\sumo-1.9.0\bin到PATH值的末尾（注意：请勿删除现有值！）（注意C:\Program Files\sumo-1.9.0应该换为您使用的文件地址）

\4. 现在，在用户变量下选择SUMO_HOME并点击编辑。如果不存在这样的变量，则必须使用New -Button创建它

\5. 设置C:\Program Files\sumo-1.9.0为SUMO_HOME变量的值（注意C:\Program Files\sumo-1.9.0应该换为您使用的文件地址）

## 3    安装SUMO

Windows有四种不同的二进制程序包，具体取决于您拥有的平台（32位和64位）以及您想对SUMO进行的处理。如果要在本地安装它并在计算机上拥有管理员权限，则应下载并执行其中一个安装程序（最好是64位）。如果您需要“便携式”版本或没有管理员权限，请使用正确的zip，并使用7Zip， Winzip或类似工具将其解压缩到所需的文件夹中。每个软件包都包含二进制文件，所需的所有dll，示例，工具和HTML格式的文档。

在安装文件夹中，您将找到一个名为“ bin ”的文件夹。在这里，您可以找到可执行文件（程序）。您可以双击 sumo-gui并查看docs / examples中的示例。所有其他应用程序（duarouter，dfrouter等）都必须从命令行运行。为此，还有一个start-commandline.bat，它可以为您设置整个环境。如果您不确定命令行，请阅读 Basics / Basic_Computer_Skills＃Running_Programs_from_the_Command_Line。

如果您希望每天进行一次最新的构建或需要测试或源文件，则可以从“下载”页面下载它们。有关从源代码构建SUMO的信息，请参见在Windows下构建SUMO。

## 4    使用SUMO命令行语句

### 4.1  从命令行使用SUMO

SUMO应用程序是纯可执行文件。您只需通过在命令行中输入它们的名称来启动它们；例如 netgenerate由netgenerate.exe代码启动。

这只是启动应用程序（在这种情况下为netgenerate）。由于未提供任何参数，因此应用程序不知道该怎么办，而仅输出有关其自身的信息：

Eclipse SUMO netgenerate Version 1.9.0

 Build features: Linux-4.1.39-56-default Proj GDAL GUI

 Copyright (C) 2001-2020 German Aerospace Center (DLR) and others; https://sumo.dlr.de

 License EPL-2.0: Eclipse Public License Version 2 <https://eclipse.org/legal/epl-v20.html>

 Use --help to get the list of options.

### 4.2  在命令行上设置选项

选项有两种：布尔型选项，不需要参数，如果存在选项，则设置为true（但接受通常的布尔型值，例如“ true”和“ false”作为参数）；以及选项，需要参数。在命令行上使用参数设置选项包括两部分-选项名称和选项的值。例如，如果要模拟加载某个道路网络“ mynet.net.xml”，则必须编写以下内容：

 --net mynet.net.xml

在这种情况下，前面的'-'表示该选项的长名称紧随其后（“ net”）。在空格之后，必须给出选项的值。也可以使用'='代替空格：

一些常用的选项可以缩写。--net-option的缩写 是-n。以下与上面的两个示例具有相同的效果：

 -n mynet.net.xml

请注意，缩写用单个“-”表示。

### 4.3  配置文件

由于选项列表可能会很长，因此引入了配置文件。您可以设置一个配置文件，其中包含要用来启动应用程序的所有参数。此外，您仅需使用此配置文件来启动应用程序。

配置文件是一个XML文件，其根元素名为 configuration。选项被写为元素名称，所需值存储在属性 value（或v）中。命令行中提供的--net-file test.net.xml选项将成为 <net-file value="test.net.xml"/>配置文件内的内容。对于布尔选项，该值对于激活应为“ true”，“ on”，“ yes”，“ 1”或“ x”，对于其激活应为“ false”，“ off”，“ no”或“ 0”停用该选项（大小写在这里无关紧要）。

对于上面的示例，配置文件（让我们将其保存在“ test.sumocfg”下，如下所示）如下所示：

<configuration>

  <input>

​    <net-file value="test.net.xml"/>

​    <route-files value="test.rou.xml"/>

​    <additional-files value="test.add.xml"/>

  </input>

</configuration>

input上面给出的部分仅具有文档目的，而没有功能含义。不太冗长但等效的版本如下所示：

<configuration>

  <n v="test.net.xml"/>

  <r v="test.rou.xml"/>

    <a v="test.add.xml"/>

</configuration>

根据SUMO执行调用（同时使用两个配置版本）将是：

 sumo.exe -c test.sumocfg

这意味着我们仅使用选项--configuration-file <FILE>或-c <FILE>给出配置文件的名称，而不是参数。如果您不想在命令行上提供其他选项，则也可以省略“ -c”：

sumo.exe test.sumocfg

### 4.4  配置文件的命名约定

根据目标应用程序，配置文件具有不同的扩展名。强烈建议您遵循此约定。为了将仿真配置与 sumo-gui一起使用，这甚至是必需的 -sumo -gui只能读取名为“ * .sumocfg”的仿真配置。可在使用的文件扩展名的页面上找到配置扩展名的所有约定。

### 4.5  配置文件与命令行参数

除了配置文件外，还可以在命令行上提供其他命令行参数。如果在命名的配置文件中以及在命令行中给定的参数被设置，则使用命令行中给定的值（覆盖配置文件中的一个）。如果要禁用在配置文件中启用的布尔选项，则需要在命令行上显式提供“ false”值，例如--verbose false。

### 4.6  生成配置文件，模板和方案

SUMO软件包的应用程序允许您生成配置文件模板。可以保存一个空的配置-配置模板。这可以通过使用--save-template <FILE>来完成。在这种情况下，配置将仅包含填充有其默认值的参数。

也可以保存包含当前设置值的配置文件。使用选项--save-configuration <FILE>可以强制应用程序执行此操作。

最后但并非最不重要的一点是，可以生成XML模式（使用选项--save-schema <FILE>）来验证配置文件。对于SUMO应用程序，此架构应等效于https://sumo.dlr.de/xsd/sumoConfiguration.xsd上的架构 （分别适用于其他可执行文件）。请注意，该架构比SUMO选项解析器更为严格，因为它仅验证上面给出的详细版本。

无论哪种情况，如果都需要有关参数的更多信息，则还可以传递--save-commented选项。然后，生成有关每个参数的一些其他注释。

### 4.7  配置文件中的环境变量

可以在配置文件中引用环境变量。引用环境变量的语法为$ {VARNAME}。例如，您的配置文件可以引用一个名为NETFILENAME的变量，该变量包含具有以下配置设置的网络文件的名称。

<configuration>

  <input>

​    <net-file value="${NETFILENAME}.net.xml"/>

  </input>

</configuration>

### 4.8  常用选项

#### 4.8.1    报告选项：

| **t**                                                        | **描述**                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| **-v** [**](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types)   **--verbose** [**](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types) | 切换到详细输出；*默认值：false* **                           |
| **--print-options** [*<**书本>*](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types) | 在处理之前打印选项值；*默认值：false* **                     |
|                                                              |                                                              |
| **-****？** [**](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types)   **--help** [**](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types) | 打印此屏幕；*默认值：false* **                               |
| **-V** [**](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types)   **--version** [**](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types) | 打印当前版本；*默认值：false* **                             |
| **-X** [**](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types)   **--xml****验证** [**](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types) | 设置XML输入的模式验证方案（“从不”，“自动”或“始终”）；*默认值：自动*** |
| **--xml-validation.net** [**](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types) | 设置SUMO网络输入的模式验证方案（“从不”，“自动”或“始终”）；*默认值：从不*** |
| **-W** [**](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types)   **--no-warnings** [**](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types) | 禁用警告输出；*默认值：false* **                             |
| **-l** [*<**文件>*](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types)   **--log** [*<**文件>*](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types) | 将所有消息写入FILE（表示冗长）                               |
| **--message-log** [*<**文件>*](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types) | 将所有非错误消息写入FILE（表示冗长）                         |
| **--error-log** [*<**文件>*](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types) | 将所有警告和错误写入FILE                                     |

日志选项--log和--message-log也启用详细输出，但仅输出到给定的文件中（除非也提供了--verbose）。错误总是会打印到控制台（除了可能的日志文件）。

该XML验证选项使XML模式处理XML分析器。这将对输入内容进行基本验证，因此强烈建议特别为初学者使用，因为它很容易在输入内容中发现拼写错误，否则可能会被忽略。仅当在输入文件中声明了XML模式时，才执行验证。

#### 4.8.2    随机数选项

这些选项配置如何确定随机数生成器的种子。相同的种子导致相同的生成随机数序列。

默认情况下，种子是硬编码的固定值。因此，只要所有配置设置都保持相同，重复模拟运行的输出将相同。要更改此设置，请使用以下选项之一。

| **选项**         | **描述**                                                     |
| ---------------- | ------------------------------------------------------------ |
| **--seed <INT>** | 为随机数生成器设置一个特定的种子。通过使用不同的值，您可以进行不同但仍可重现的模拟运行。 |
| **--random**     | 让SUMO选择种子。如果可用，则种子将基于/ dev / urandom的输出，否则种子将从当前系统时间得出。此选项**优先**于**--seed** [**](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types)选项。 |

### 4.9  生成和读取文件

从SUMO包中读取或生成的工具中，几乎每个文件都是用XML编写的。在开始使用SUMO之前，您应该熟悉 XML。SUMO允许您从不同来源导入文件，但是“本机” SUMO文件-道路网络描述，路线和/或需求描述，基础结构描述等-是SUMO特定的，不遵循任何标准。可以使用简单的文本编辑器来读取和写入XML文件，我们通常这样做。但是，还有其他几种工具可以重复使用。

对于SUMO使用的某些文件类型，存在xsd（XML模式定义）。请查阅文件扩展名页面，以获取所描述文件格式的列表。

提示：

Windows上XML文件的默认查看器是Internet Explorer。它可以用于验证您的XML文件。如果Internet Explorer可以完全加载XML文件的语法，则该语法应有效。Eclipse允许遵循给定的xsd（XML模式定义）来编写XML文档。

### 4.10      写文件

有几个选项希望将文件名（<FILE>）作为参数写入。在命令行中给出时，假定给定路径是相对于当前工作目录的。当在配置文件中给出文件路径时，假定该文件路径相对于配置文件的路径。当然也可以使用绝对路径。

通常，具有相同名称的现有文件会被覆盖而不会发出警告。该目录必须存在，应在其中写入输出文件。

除了写入文件之外，其他特殊符号还允许：

1．写入空设备（根本没有输出）：使用“ NUL”或“ / dev / null”作为文件名（两种表示法均与平台无关）

2．写入套接字：使用“ <HOST>：<PORT>”作为文件名

3．写入标准输出（在命令行上打印）：使用“ stdout”或“-”作为文件名

4．写入stderr：使用“ stderr”作为文件名

文件名中的特殊字符串“ TIME”将替换为应用程序的开始时间

目前，无法从套接字或stdin读取输入。

作为修改输出文件名的简单方法，提供了--output-prefix <STRING>选项。给定的字符串将放在应用程序编写的所有文件之前。

### 4.11      时间值

默认情况下，SUMO写入的所有时间值均以秒为单位。所有应用程序和某些python工具都支持--human-read-time（short -H）选项，该选项导致输出中的时间写为“ HH：MM：SS”（小时，分钟，秒）。亚秒级的时间将写为“ HH：MM：SS.SS”。如果写入时间超过24小时，则将其写为“ DD：HH：MM：SS”，其中DD是天数。设置选项--human-read-time也将影响sumo-gui对话框中某些时间值的格式（即断点）。选项和xml输入中的所有时间值都可以始终以秒或“ HH：MM：SS”或“ DD：HH：MM：SS”格式给出。

### 4.12      从命令行使用Python工具

SUMO分发的许多工具（在 <SUMO_HOME> / tools文件夹中）都是用python 编程语言编写的。要使用它们，必须在计算机上安装python 2.7。

然后，您需要确保设置了环境变量SUMO_HOME。最简单的方法是使用start-command-line.bat打开命令行窗口 。

此外，您需要确保您的计算机知道在哪里可以找到python工具。最简单（但有点麻烦）的方法是使用完整路径运行该工具：

C:\Users\yourname>D:\path_to_sumo\tools\randomTrips.py ... arguments ...

或者，您可以将工具所在的目录添加到 PATH-Variable。

## 5    教程

### 5.1  初学者教程

#### 5.1.1    创建简单网络和需求

本教程适用于初次使用SUMO的用户。我们将构建最简单的网络，并让其上一辆汽车行驶。

为了在SUMO中执行非常基本的模拟，要求至少具有以下元素（文件）：

1网络

2路线

3SUMO配置文件

在SUMO中，街道网络由节点（路口）和边线（连接路口的街道）组成。在本教程中，我们将使用netedit创建我们的基本网络。

路线是通过连接边并分配经过它们的车辆来定义的。在本教程中，我们将使用netedit来创建它。

SUMO配置文件是列出某些选项和所有文件（网络，路由等）的位置，以便SUMO可以查找和使用它们。

l 在netedit创建网络

打开netedit并通过选择File-> New Network或使用快捷方式来创建一个新的网络Ctrl + N确保已选择“网络”。

![https://sumo.dlr.de/docs/images/neteditNetworkMode.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image002.jpg)

使用快捷方式或单击按钮，选择“*编辑”->“**边缘模式”*，以进入“**边缘模式”**。在“边缘模式”下，确保已选择“***链”\***（在较新的版本中，“*链”*是以下图标：）。这将有助于以更少的点击创建多个节点及其连接边缘。E![https://sumo.dlr.de/docs/images/ModeCreateEdge.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image003.gif)![https://sumo.dlr.de/docs/images/checkbox_chain.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image004.png)

![https://sumo.dlr.de/docs/images/neteditChainSelected.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image006.jpg)

通过单击空白区域（处于“边缘模式”时）来创建节点。通过在白色空白处单击三个不同的位置来插入3个节点（又名“结”）。插入最后一个节点后，按<ESC>取消选择最后一个节点。

![https://sumo.dlr.de/docs/images/HelloWorld_1.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image007.gif)

现在，我们想重命名最近插入的Junctions和Edges（在创建时会获得任意ID），并通过对齐所有节点来使我们的简单网络更漂亮。为此，通过使用快捷方式或单击按钮，选择“*编辑”->“**检查模式”*，以进入“**检查模式”**。I![https://sumo.dlr.de/docs/images/ModeInspect.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image008.gif)

在检查模式下，您可以选择不同类型的元素，例如节点和边。如果选择了元素，则其属性将显示在左侧。让我们将节点重命名（更改其id）为“ 1”，“ 2”和“ 3”（从左到右），将边缘重命名为“ 1to2”和“ out”（也从左到右）。将节点的位置（pos）替换为以下值：

| **ID** | **位置** |
| ------ | -------- |
| 1个    | -100,50  |
| 2个    | 0,50     |
| 3      | 100,50   |

![https://sumo.dlr.de/docs/images/HelloWorld_2.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image009.gif)

我们最基本的网络已经完成！我们只需要保存它![https://sumo.dlr.de/docs/images/Save.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image010.gif)。使用*文件**->**保存网络*（Ctrl + S）或*文件**->**将网络另存为*（Ctrl + Shift + S）并为其指定适当的名称（例如helloWorld.net.xml）。暂时不要关闭netedit，仍然需要生成需求。

l Netedit需求生成

现在，在netedit中选择“需求”超级模式。

![https://sumo.dlr.de/docs/images/neteditDemandMode.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image012.jpg)

**创建路线**

通过使用快捷方式或单击按钮，选择“*编辑”->“**路由模式”*，进入“**路由模式”**。R![https://sumo.dlr.de/docs/images/Route.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image013.gif)

创建一条路线就像单击将要构成其的边一样简单。选择边缘时，其颜色将改变。

- FOO选定的边缘
- FOO可能的可选边

选择将组成所需路线的所有边后，点击*创建路线*。

![https://sumo.dlr.de/docs/images/HelloWorld_3.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image014.gif)

**添加车辆**

最后，通过使用快捷方式或单击按钮，选择“*编辑”->“**车辆模式”*，进入“**车辆模式”**。要插入车辆，只需点击路线的起点即可。将会出现一辆汽车。在左侧栏上，您可以更改车辆的属性，例如id甚至颜色（只是为了好玩而将其更改为蓝色）。V![https://sumo.dlr.de/docs/images/Vehicle.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image015.gif)

![https://sumo.dlr.de/docs/images/HelloWorld_4.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image016.gif)

现在保存需求（路线+车辆）文件![https://sumo.dlr.de/docs/images/Save.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image010.gif)。使用*文件**->**需求元素->**保存需求元素*（Ctrl + Shift + D）或*文件**->**需求元素->**将需求元素另存为*并为其指定适当的名称（例如helloWorld.rou.xml）。请勿关闭netedit。

l 在SUMO中可视化

我们将从netedit打开sumo-gui。为此，请转到“编辑”->“以sumo-gui打开”（Ctrl + T）。这将打开sumo-gui并加载我们最近创建的网络和需求文件。

sumo-gui打开后，立即保存SUMO配置文件（该文件与网络和需求文件相关）。 文件->保存配置（Ctrl + Shift + S）。给它起一个适当的名称（例如helloWorld.sumocfg）。现在，您可以根据需要关闭netedit。

在开始模拟之前，请确保将Delay设置为至少80 ms，否则模拟将非常快速地进行，我们将无法在我们的小型网络中看到我们唯一的车辆。单击运行（Ctrl + A）开始仿真。

![https://sumo.dlr.de/docs/images/Delay.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image017.png)

![https://sumo.dlr.de/docs/images/HelloWorld_5.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image018.gif)

#### 5.1.2    OSMWeb向导

l 关于

OSM Web向导提供了从SUMO开始最简单的解决方案之一。基于对openstreetmap地图摘录的选择，您将能够配置随机流量需求，并在sumo-gui中运行和可视化场景。本教程将指导您从地图摘录的选择中逐步指导您，通过运行和可视化sumo-gui中的方案来定义交通需求。

l 要求

SUMO安装

Python（> = 2.7）安装

l 入门

OSM Web向导本质上是相扑安装根目录中位于目录工具下的python脚本的集合。通过在tools 目录中调用以下命令来启动OSM Web向导：

python osmWebWizard.py

Windows用户也可以通过单击所有程序-> SUMO-> OSM Web向导来调用命令。脚本运行后，将打开一个网络浏览器，显示柏林市中心的地图摘录。

![wz01.jpg](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image020.jpg)

您可以缩放和平移到您感兴趣的区域。注意：如果地图摘录覆盖的区域很大，则模拟可能会变慢甚至无法响应。我们建议选择与初始视图类似的缩放级别。

在下一步中，选择要为其生成模拟方案的实际区域。通过单击地图右侧蓝色区域选择面板上的“选择区域”复选框，可以激活区域选择。

![wz02.jpg](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image022.jpg)

您可以通过在灰色和非灰色区域之间的边界上单击并按住鼠标指针来更改此区域的大小和位置。对区域选择满意后，即可继续下一步。

l 网络生成

从OSM导入到SUMO仿真的基础结构受不同的向导选项的影响

默认情况下会生成道路交通模拟，但也会导入所有类型的道路和铁路（自行车道，人行道，铁路等）

如果启用了“左侧流量”复选框，则将使用左侧流量规则来构建网络。对于需要此功能的大多数地理区域，此功能将自动启用，但如果它不起作用，则可以将该选项用作补救措施。

如果启用了“仅汽车网络”复选框，则仅包括允许乘用车通行的道路。这可用于减小网络规模，也有助于降低路口复杂度

如果启用了“导入公共交通”复选框，则将导出busStops和trainStops。还将按照OSM中定义的公共运输路线生成公交车，电车和火车（但它们将遵循综合时间表）。

如果“需求”复选框“自行车”处于活动状态，则将在OSM包含此信息的道路上添加额外的自行车道

如果需求复选框“行人”处于活动状态，则将生成人行道和人行横道。

l 需求产生

需求由需求生成面板定义。您可以通过单击汽车象形图来激活此面板。

![wz03.jpg](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image024.jpg)

SUMO支持多种运输方式。在需求生成面板上，您可以通过单击相应的复选框来激活/停用各种运输方式。对于每种传输方式，OSM Web向导都会基于一定的概率分布生成随机需求，该概率分布受两个参数的影响：

每次生成新车辆时，OSM Web向导都会随机选择车辆的出发和到达边缘。在通过交通因子定义它是多少倍，可能为边界处的模拟区域的边缘被选择相比完全位于模拟区域内的边缘。“通过交通因数”的较大值表示有许多车辆驶离并到达模拟区域的边界，这对应于具有大量通过交通的情况。

该计数参数定义多少车辆每小时车道公里的产生。假设

网络包含3个边缘，总长度为5 km

每个都有2条车道，以允许当前的交通模式

并将计数值设置为90，

则每小时将产生5 * 2 * 90 = 900辆汽车。这转换为 p = 4的 randomTrips参数，这意味着每4秒就会在网络中的某处插入新的车辆。

下一步是生成并运行方案。

l 生成并且运行方案

单击控制面板中的“生成方案”后，将自动生成完整的方案。场景生成需要几秒钟或几分钟（尤其取决于场景的大小）。场景生成过程完成后，sumo-gui将启动，并且可以通过按“播放”按钮来启动模拟。

![wz04.jpg](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image026.jpg)

l 选择车流走向

OSM Web向导将整个模拟方案相扑配置和中间文件存储在本地目录中，名称的格式为 yyyy-mm-dd-hh-mm-ss。如果您的SUMO安装位置是可写的，则数据将存储在tools目录中。否则，将创建一个新目录〜/ SUMO / yyyy-mm-dd-hh-mm-ss来承载数据。目录的内容如下所示：

  ➜ 2016-10-17-14-54-30 ls

  build.bat         osm.net.xml        osm.rail.rou.alt.xml    osm.tram.rou.alt.xml

  osm.bicycle.rou.alt.xml  osm.netccfg        osm.rail.rou.xml      osm.tram.rou.xml

  osm.bicycle.rou.xml    osm.passenger.rou.alt.xml osm.rail.trips.xml     osm.tram.trips.xml

  osm.bicycle.trips.xml   osm.passenger.rou.xml   osm.rail_urban.rou.alt.xml osm.truck.rou.alt.xml

  osm.bus.rou.alt.xml    osm.passenger.trips.xml  osm.rail_urban.rou.xml   osm.truck.rou.xml

  osm.bus.rou.xml      osm.pedestrian.rou.alt.xml osm.rail_urban.trips.xml  osm.truck.trips.xml

  osm.bus.trips.xml     osm.pedestrian.rou.xml   osm.ship.rou.alt.xml    osm.view.xml

  osm.motorcycle.rou.alt.xml osm.pedestrian.trips.xml  osm.ship.rou.xml      osm_bbox.osm.xml

  osm.motorcycle.rou.xml   osm.poly.xml        osm.ship.trips.xml     run.bat

  osm.motorcycle.trips.xml  osm.polycfg        osm.sumocfg

#### 5.1.3    使用netedit入门

本教程介绍了使用示例网络进行流量分析的SUMO的基本应用程序和基本功能。

此处提到的所有文件也可以在 <SUMO_HOME> / docs / tutorial / quickstart目录中找到。可以在<SUMO_HOME> / tests / complex / tutorial / quickstart / data的资源库中找到最新版本。

l 范例说明

在此示例中，将使用SUMO的应用来分析交通状态。示例网络包括四个起点，四个目的地以及两个无信号交叉口。在调查的区域中，每条出站道路都有3条车道，并且每条车道上允许的交通流量受到限制。禁止在所有路口掉头。此外，对东行和西行的交通给予了更高的优先权。相应的网络布局如图所示。

![型号名称](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image028.png)

l 资料准备

在SUMO中进行流量分析之前，应首先使用表中列出的信息来构建图中的示例网络。

| **节点名称** | **X****坐标** | **y****坐标** |
| ------------ | ------------- | ------------- |
| 91           | -1000.0       | +1000.0       |
| 92           | -1000.0       | 0.0           |
| 93           | +3000.0       | 0.0           |
| 94           | +3000.0       | +1000.0       |
| 911          | -500.0        | +1000.0       |
| 912          | -500.0        | 0.0           |
| 913          | +2500.0       | 0.0           |
| 914          | +2500.0       | +1000.0       |
| 1个          | 0.0           | +1000.0       |
| 2个          | 0.0           | 0.0           |
| 3            | +1000.0       | 0.0           |
| 4            | +2000.0       | 0.0           |
| 5            | +2000.0       | +1000.0       |
| 6            | +1000.0       | +1000.0       |

l 使用netedit进行网络编辑

根据表1.2中的坐标数据和图1.1中基于节点链接的网络布局，通过分别给出x和，分别将交点，起点和终点编码为节点1-6和节点91-94。与程序netedit的y坐标。打开netedit，您可以在SUMO软件包的bin目录中找到它。首先，创建一个新的网络（“文件”->“新网络...”）。

然后选择“编辑”模式，可以通过两种方式进行：

![First.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image030.jpg)

![Menue.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image032.jpg)

首先，您创建一个节点，然后通过单击画布来创建第二个节点。两者都将自动连接，您将获得第一个优势。

![Second.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image034.jpg)

![Third.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image036.jpg)

下一步是切换到“检查”模式，并替换上面表1.2中定义的节点的名称和位置。像其他交通模拟软件一样，道路在SUMO中被表示为链接。要定义链接特征，必须首先使用数字，单词字符串或两者都定义每个链接的标识（id）。要编辑这些值，请使用鼠标左键单击表示连接处的红色圆圈。

![Fourth.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image037.png)

![Fifth.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image039.jpg)

如果按Enter键，您将获得新位置。

现在该保存网络了：您可以在File的下拉菜单中找到一个选择。对于我们这里的目的，将网络另存为...就足够了。请为您的网络选择一个合适的名称，例如quickstart.net.xml。稍后，当您从配置中引用网络时，将使用此名称。

在给定的示例中可以看到，双向都有街道。要为边缘提供此信息，您可以右键单击创建的边缘，然后选择“添加反向”，或者在边缘创建过程中选择双向选项。

![six.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image041.jpg)

![Seventh.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image043.jpg)

此外，必须更改一个属性以获得与示例描述中类似的输出：通道数。如果您处于检查模式，然后单击相关边并直接进行更改，则可以轻松更改车道数量。

![八分](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image044.png)

现在，您应该能够在此示例中创建其余所有给定的节点和边线，并更改名称，通道数并重置位置。不要忘记不时保存您的工作。虚拟节点911-914需要用于分析网络中传入和传出链路上的流量性能。如果需要，可以应用更多的虚拟节点（例如用于精确的几何对齐或用于指定检测器位置）。

下一步将是定义边缘之间的连接。要查看哪些连接已自动建立，请选中显示连接框。

SUMO中的默认设置基于所有可能的和逻辑的交通流量的给定几何设计。如果没有相应的规范，则可以掉头。默认设置是每个链接的最右边的车道与相应下游链接的最右边的车道对齐。在我们的示例中，期望以下连接：

| **edge ID   from** | **edge ID to** | **fromLane** | **toLane** |
| ------------------ | -------------- | ------------ | ---------- |
| L2                 | L12            | 0            | 0          |
| L2                 | L12            | 0            | 1个        |
| L2                 | L12            | 1个          | 2个        |
| L4                 | L14            | 0            | 0          |
| L4                 | L14            | 1个          | 1个        |
| L4                 | L14            | 1个          | 2个        |
| L9                 | L11            | 0            | 0          |
| L9                 | L11            | 1个          | 1个        |
| L9                 | L11            | 1个          | 2个        |
| L9                 | L15            | 1个          | 1个        |
| L9                 | L15            | 2个          | 2个        |
| L16                | L10            | 0            | 0          |
| L16                | L10            | 1个          | 1个        |
| L16                | L10            | 1个          | 2个        |
| L16                | L11            | 2个          | 2个        |
| L12                | L15            | 0            | 0          |
| L12                | L15            | 1个          | 1个        |
| L12                | L10            | 1个          | 0          |
| L12                | L10            | 1个          | 1个        |
| L12                | L10            | 2个          | 2个        |
| L14                | L16            | 1个          | 1个        |
| L14                | L16            | 1个          | 0          |
| L14                | L16            | 2个          | 2个        |
| L14                | L18            | 0            | 0          |
| L14                | L18            | 1个          | 1个        |
| L14                | L18            | 1个          | 2个        |
| L17                | L16            | 0            | 0          |
| L17                | L16            | 1个          | 1个        |
| L17                | L16            | 1个          | 2个        |
| L17                | L13            | 1个          | 0          |
| L17                | L13            | 1个          | 1个        |
| L17                | L13            | 2个          | 2个        |

每个属性的含义如下：

（a）来自：将为其指定流量移动的链接的ID。

（b）至：上面定义的链接的下游链接的ID。

（c）fromLane / toLane：已连接的（a）中定义的链接的车道号和（b）中的链接的车道号。

如果更改为连接模式，则可以指定新连接或更改现有连接。通过单击选定的边缘，这是可能的。如您在下图左侧所看到的，图例中显示了染色边缘的不同含义。

![con1.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image046.jpg)

-另一个主题是每个边缘的优先级。在我们的示例中，默认情况下优先级为1。要更改优先级，请选择要修改的边缘（请参见下图）。切换到检查模式。然后，您可以通过单击所选边之一来更改所有所选边的优先级信息。在示例中，具有3条车道和2条车道的东行和西行道路的优先级应为3，而北行（L16）和南行（L15）的优先级应为2。

![prio1.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image048.jpg)

![prio2.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image050.jpg)

l 交通需求

为了满足交通需求，示例网络中有四种车辆类型（A，B，C和D辆汽车）。所有驾驶员在驾驶中均达到50％完美。表1.1中列出了相应的信息。在调查时间15:00至15:15内，每辆车辆每30秒钟将有一辆车辆从每个起点出发前往每个目的地。

| **车辆类型** | **最大限度。加速度（米/****秒）** | **最大限度。减速度（m / s****）** | **长度（米）** | **最大限度。速度（米/****秒）** |
| ------------ | --------------------------------- | --------------------------------- | -------------- | ------------------------------- |
| 车A          | 3.0                               | 6.0                               | 5.0            | 50.0                            |
| 车B          | 2.0                               | 6.0                               | 7.5            | 50.0                            |
| 车C          | 1.0                               | 5.0                               | 5.0            | 40.0                            |
| 卡片         | 1.0                               | 5.0                               | 7.5            | 30.0                            |

在扩展名为.rou.xml的文件中，定义了交通需求和路线数据以及车辆类型数据。清单1.5中显示了示例网络的相应格式。

l 车辆类型

清单1.5显示，首先根据表1.1中的信息定义所有车辆类型。相关属性包括：

（a）id：车辆类型的ID，由用户使用数字，字串或两者定义；

（b）加速度：相应车辆类型的最大加速度（以m / s2为单位）；

（c）减速度：相应车辆类型的最大减速度（以m / s2为单位）；

（d）西格玛（sigma）：驾驶员在驾驶中的不完善之处（介于0和1之间）；

（e）长度：车辆长度（以米为单位）；

（f）maxSpeed：最大车速（以m / s为单位）；

（g）颜色：车辆类型的颜色。它分别定义了3个数字（0和1之间），分别代表红色，绿色和蓝色。值用逗号分隔，并用引号引起来，值之间没有空格。例如，1,0,0代表红色，0,1,0代表绿色，0,0,1代表蓝色。

属性的顺序可以更改。对于所有车辆类型，属性sigma被分配为0.5。

清单1.5：

<?xml version="1.0" encoding="UTF-8"?>

<routes>

 <vType accel="3.0" decel="6.0" id="CarA" length="5.0" minGap="2.5" maxSpeed="50.0" sigma="0.5" />

 <vType accel="2.0" decel="6.0" id="CarB" length="7.5" minGap="2.5" maxSpeed="50.0" sigma="0.5" />

 <vType accel="1.0" decel="5.0" id="CarC" length="5.0" minGap="2.5" maxSpeed="40.0" sigma="0.5" />

 <vType accel="1.0" decel="5.0" id="CarD" length="7.5" minGap="2.5" maxSpeed="30.0" sigma="0.5" />

 <route id="route01" edges="D2 L2 L12 L10 L7 D7"/>

 <route id="route02" edges="D2 L2 L12 L15 L18 L5 D5"/>

 <route id="route03" edges="D2 L2 L12 L15 L13 L3 D3"/>

 <route id="route04" edges="D4 L4 L14 L18 L5 D5"/>

 <route id="route05" edges="D4 L4 L14 L16 L10 L7 D7"/>

 <route id="route06" edges="D4 L4 L14 L16 L11 L1 D1"/>

 <route id="route07" edges="D6 L6 L17 L13 L3 D3"/>

 <route id="route08" edges="D6 L6 L17 L16 L11 L1 D1"/>

 <route id="route09" edges="D6 L6 L17 L16 L10 L7 D7"/>

 <route id="route10" edges="D8 L8 L9 L11 L1 D1"/>

 <route id="route11" edges="D8 L8 L9 L15 L13 L3 D3"/>

 <route id="route12" edges="D8 L8 L9 L15 L18 L5 D5"/>

 <vehicle depart="54000" id="veh0" route="route01" type="CarA" color="1,0,0" />

 <vehicle depart="54000" id="veh1" route="route02" type="CarA" />

 <vehicle depart="54000" id="veh2" route="route03" type="CarA" />

 <vehicle depart="54000" id="veh3" route="route04" type="CarA" />

 <vehicle depart="54000" id="veh4" route="route05" type="CarA" />

 <vehicle depart="54000" id="veh5" route="route06" type="CarA" />

 <vehicle depart="54000" id="veh6" route="route07" type="CarA" />

 <vehicle depart="54000" id="veh7" route="route08" type="CarA" />

 <vehicle depart="54000" id="veh8" route="route09" type="CarA" />

 <vehicle depart="54000" id="veh9" route="route10" type="CarA" />

 <vehicle depart="54000" id="veh10" route="route11" type="CarA" />

 <vehicle depart="54000" id="veh11" route="route12" type="CarA" />

 <vehicle depart="54000" id="veh12" route="route01" type="CarB" color="1,0,0" />

 <vehicle depart="54000" id="veh13" route="route02" type="CarB" />

 <vehicle depart="54000" id="veh14" route="route03" type="CarB" />

 <vehicle depart="54000" id="veh15" route="route04" type="CarB" />

 <vehicle depart="54000" id="veh16" route="route05" type="CarB" />

 <vehicle depart="54000" id="veh17" route="route06" type="CarB" />

 <vehicle depart="54000" id="veh18" route="route07" type="CarB" />

...

</routes>

l 交通路线

在车辆类型信息之后，还需要定义交通路线数据。输入属性包括：

（a）id：某条路线的ID，由用户使用数字，字串或两者同时定义。

（b）边：链接名称的顺序，组成定义的路线。

l 交通需求

交通需求数据定义了四个属性：

（a）出发：某辆车的出发时间。

（b）id：特定车辆的ID，由用户使用数字和/或字串或两者来定义。

（c）路线：指定车辆使用的路线。

（d）类型：已定义车辆类型的ID。

l 模拟

SUMO中的交通模拟可以通过以下两种方式进行。图1.8给出了仿真过程的概述。

括号中的所有文件名都是示例中使用的文件名。

![图片：image008.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image051.gif)

l 命令行

使用命令行可以实现有效的交通模拟执行，尤其是在处理大型复杂交通网络时。为了简化执行过程，建议在配置文件中指定所有必需的执行操作，例如输入文件的路径和名称，输出类型，输出目录和模拟时间段。

清单1.7。示例网络的流量模拟的配置文件（quickstart.sumocfg）

<?xml version="1.0" encoding="iso-8859-1"?>

<configuration xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"

 xsi:noNamespaceSchemaLocation="http://sumo.dlr.de/xsd/sumoConfiguration.xsd">

  <input>

​    <net-file value="quickstart.net.xml"/>

​    <route-files value="quickstart.rou.xml"/>

  </input>

  <time>

​    <begin value="54000"/>

​    <end value="54900"/>

  </time>

  <time-to-teleport value="-1"/>

</configuration>

我们在<time-to-teleport value="-1"/>此处使用该选项，以禁止自动删除在十字路口前等待时间过长的车辆。

对于示例网络，清单1.7中显示了相应的配置文件，然后可以使用以下命令进行流量模拟：

  sumo –c quickstart.sumocfg

l SUMO-GUI

sumo-gui的应用是使用SUMO执行交通模拟的另一种方法。在执行过程中，可以观察到每个车辆的运动和交通进展，并且可以从视觉上识别可能的瓶颈。sumo-gui需要所有执行动作的配置文件，例如清单1.7中的动作 。双击程序 sumo-gui.exe和sumo-gui工作窗口将自动打开。通过在菜单栏的“文件”菜单下打开相应的配置文件，可以激活所调查的网络。然后，可以通过按下主工具栏中的绿色三角形按钮来执行交通仿真。当用户按下红色正方形按钮时，可以随时停止模拟。如果仿真时间未到，可以通过按绿色三角形来恢复已停止的仿真。图1.9给出了一个示例。

![图像：image009.jpg](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image052.jpg)

## 6    验证应用程序XML的输入

### 6.1  验证XML输入

所有SUMO应用程序都支持对其输入进行XML验证。要启用此功能，可以使用以下选项：

| **选项**                                                     | **描述**                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| **-X** [**](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types)   **--xml****验证** [**](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types) | 设置XML输入的模式验证方案（“从不”，“自动”或“始终”）；*默认值：自动*** |
| **--xml-validation.net** [**](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types) | 设置SUMO网络输入的模式验证方案（“从不”，“自动”或“始终”）；*默认值：从不*** |

通过激活XML解析器中的XML模式处理来执行验证。这捕获了许多常见的输入错误，例如拼写错误和应放置在另一个元素中的属性。

验证的另一个前提条件是输入文件根元素中的架构减速，例如

<routes xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="http://sumo.dlr.de/xsd/routes_file.xsd">

将验证选项设置为始终时，忽略此声明是错误的。

模式验证可能会大大减慢XML解析速度，因此默认情况下将禁用网络输入（因为网络不应该手动编辑，因此仍然有效）。

### 6.2  添加架构声明

由SUMO应用程序之一写入的文件将自动接收适当的架构声明。从头开始编写输入文件时，必须将模式声明手动添加到根元素，如下所示：

  <ROOT_ELEMENT xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"

​     xsi:noNamespaceSchemaLocation="http://sumo.dlr.de/xsd/SCHEMA_FILE">

其中应根据下表设置ROOT_ELEMENT和SCHEMA_FILE：

| **应用选项**                                            | **ROOT_ELEMENT** | **SCHEMA_FILE**      |
| ------------------------------------------------------- | ---------------- | -------------------- |
| **--route-files**，-- **trip-files**，-- **flow-files** | 路线             | routes_file.xsd      |
| **-****其他文件**                                       | 添加             | Additional_file.xsd  |
| **--node-files**                                        | 结点             | nodes_file.xsd       |
| **--edge****文件**                                      | 边缘             | edges_file.xsd       |
| **-****连接文件**                                       | 连接数           | connections_file.xsd |
| **--tllogic-****文件**                                  | 逻辑             | tllogic_file.xsd     |
| **--type-files**                                        | 类型             | types_file.xsd       |
| **--weight-files**                                      | 均值数据         | meandata_file.xsd    |

# 第三章 网络构建

## 1    SUMO道路网介绍

![eichstaett.net.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image054.jpg)

一个SUMO网络文件描述了一个地图，模拟车辆沿道路或横跨运行的道路和路口的交通环境的一部分。粗略地说，SUMO网络是有向图。节点通常在SUMO上下文中称为“路口”，代表路口和“边缘”道路或街道。请注意，边缘是单向的。具体来说，SUMO网络包含以下信息：

每条街道（边缘）作为车道的集合，包括每条车道的位置，形状和速度限制，

路口引用的交通信号灯逻辑，

交界处，包括其通行权管制，

交叉路口（节点）上的车道之间的连接。

此外，根据使用的输入格式和设置的处理选项，还可以找到

地区，

回旋处说明。

尽管SUMO网络文件可以被人类读取（XML），但并不意味着可以手动进行编辑。相反，您应该将SUMO XML描述文件 与netconvert一起使用。您也可以从各种格式转换使用现有的地图 netconvert或产生几何形状简单，抽象的路线图与netgenerate。要修改现有的.net.xml文件，您可以将netconvert和补丁文件一起加载它。您还可以使用netedit来构建自己的道路网络或对从netconvert或 netgenerate获得的道路网络进行返工。

### 1.1  网络格式

SUMO道路网络被编码为XML文件。内容按实例按以下顺序分组：

适用于该网络的地图投影

边缘 首先，先给出内部边缘，然后给出平边缘；每个边都包含属于它的车道列表

交通灯逻辑

路口，包括通行权定义；首先是普通路口，然后是内部路口

连接，首先是普通的，然后是内部的

可选的回旋处

#### 1.1.1    坐标与对齐

网络使用笛卡尔度量坐标，其中最左边的节点在x = 0处，而最底部的节点在y = 0处。这意味着，在导入时，netconvert和 netgenerate会投影网络，首先，如果原始网络未使用笛卡尔坐标和/或度量坐标。然后，他们将道路网移至（0,0）的原点。

该过程记录在元素内的生成网络中location。您可以在此处找到以下属性：

| **名称**      | **类型**                                                     | **描述**                                       |
| ------------- | ------------------------------------------------------------ | ---------------------------------------------- |
| netOffset     | 偏移量（[*<2D-POSITION>*](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types)） | 用于将网络移动到（0,0）的偏移量                |
| Edge          | 边界（[*<2D-BOUNDING_BOX>*](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types)） | 跨越转换后的网络（现在给出的网络）的节点的边界 |
| origBoundary  | 边界（[*<2D-BOUNDING_BOX>*](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types)） | 投影和转换之前的网络初始边界                   |
| projParameter | 投影参数                                                     | 信息网络的投影方式（请参阅下文）               |

projParameter 可能具有以下值之一：

| **编码方式**                                                 | **描述**                                               |
| ------------------------------------------------------------ | ------------------------------------------------------ |
| '！'                                                         | 没有应用投影。                                         |
| '-'                                                          | 应用了“简单”投影                                       |
| '。'                                                         | ？                                                     |
| 项目定义（[**](https://sumo.dlr.de/docs/Basics/Notation.html#referenced_data_types)） | 投影是使用proj完成的，并使用这些参数对其进行了初始化。 |

为了从x / y坐标SUMO报告中获得原始坐标，必须先减去网络偏移。然后，关于，必须对初始投影进行逆变换 projParameter。对于投影项目的网络，可以使用名为pj_inv的proj函数执行逆变换。首先必须使用来自的投影参数来初始化proj projParameter。对于项目投影的网络，这看起来像：

Position2D cartesian = sumoXY(x, y);

projPJ myProjection = pj_init_plus(projParameter.c_str());

cartesian.sub(netOffset);

projUV p;

p.u = cartesian.x();

p.v = cartesian.y();

p = pj_inv(p, myProjection);

p.u *= RAD_TO_DEG;

p.v *= RAD_TO_DEG;

cartesian.set(p.u, p.v);

对于无投影的网络（projParameter='！'），仅必须应用偏移量。对于具有“简单”投影（projParameter='-'）的网络，当前尚不知道反投影方法。

SUMO道路网络意在向北对齐。当然，这取决于用户如何定义道路网络，但是当从“开放街道地图”或形状文件的来源中导入时，向上方向应对应于北方。

#### 1.1.2    边缘和车道

“普通”和“内部”边缘的编码方式几乎相同，但是它们在强制属性和使用属性方面有所不同。

l 法线边缘

“正常”边缘是两个节点之间的连接（“连接”）。

<edge id="<ID>" from="<FROM_NODE_ID>" to="<TO_NODE_ID>" priority="<PRIORITY>">

  ... one or more lanes ...

</edge>

在此，ID（上面示例中的<ID>）是在网络导入期间读取的ID。在属性from和 to中分别指定了开始节点和结束节点的ID 。优先级是确定通行权规则的抽象序数。function上面的示例中省略了该属性，因为该 属性默认为normal示例边缘的function值“ ” 。

边的属性是：

| **名称** | **类型**                                                     | **描述**                              |
| -------- | ------------------------------------------------------------ | ------------------------------------- |
| ID       | id（字符串）                                                 | 边缘的id                              |
| From     | id（字符串）                                                 | 它开始于的节点的id                    |
| to       | id（字符串）                                                 | 它结束于的节点的id                    |
| priority | 整数                                                         | 指明道路的重要性（可选）              |
| function | 枚举（“ normal”，“ internal”，“ connector”，“ crossing”，“ walkingarea”） | 抽象边缘目的（可选，默认为“ normal”） |

对于仿真，仅关注“功能”属性。它描述了边缘的使用方式，以及它是在现实世界中可以找到的边缘，还是仅用于分配的辅助构造。定义了以下目的：

normal：边缘是道路网络的平原部分，例如高速公路或连接两条道路的普通街道

connector：边缘是宏观连接器-并非真实世界道路网的一部分。尽管如此，在模拟中，“连接器”道路和“正常”节点之间没有区别。只有sumo-gui允许隐藏连接器边缘。

internal：边缘是相交的一部分（位于相交内），请参见上文。

crossing：

walkingarea：

l 车道

每个边都包括其组成的车道的定义。下面的示例显示具有两个车道的单个边。注意，坐标既可以是2D也可以是3D。

 <edge id="<ID>" from="<FROM_NODE_ID>" to="<TO_NODE_ID>" priority="<PRIORITY>">

​    <lane id="<ID>_0" index="0" speed="<SPEED>" length="<LENGTH>" shape="0.00,495.05 248.50,495.05"/>

​    <lane id="<ID>_1" index="1" speed="<SPEED>" length="<LENGTH>" shape="0.00,498.35,2.00 248.50,498.35,3.00"/>

  </edge>

可以看到，该ID由车道所属的边缘的ID和行驶编号组成，两者均由下划线（_）分隔。最右边车道的行驶数字从零开始。“ index”属性中也给出了相同的数字。车道也按此数字排序。@note：这是高度重复的

车道的属性是：

| **名称**   | **类型**               | **描述**                                                     |
| ---------- | ---------------------- | ------------------------------------------------------------ |
| **ID**     | id（字符串）           | 车道编号                                                     |
| Index      | 运行编号（无符号整数） | 一个运行数字，从最右边的车道以零开始                         |
| **speed**  | 漂浮                   | 该车道上允许的最大速度[m  / s]                               |
| **length** | 漂浮                   | 该车道的长度[m]                                              |
| **shape**  | 位置向量               | 车道的几何形状，由描述车道中心线的折线给出；不能为空或少于两个位置 |

应该注意的是，即使边缘的所有车道与形状的几何长度不同，当前其所有车道也都具有相同的长度。 netconvert甚至明确允许覆盖几何长度。此外，即使将网络移到（0,0）开始，也不能保证网络的所有部分都具有正坐标。

l 内部边缘

内部边缘位于相交内，并将传入的法线边缘与传出的法线边缘连接起来 。如果使用--no-internal-links选项构建网络，则不包括内部边缘。内部边缘的示例可能如下所示：

<edge id="<ID>" function="internal">

  ... one lane ...

</edge>

内部边缘的ID组成为：<NODE_ID> _ <EDGE_INDEX> 其中<NODE_ID>是边缘所在节点的ID， <EDGE_INDEX>是围绕该节点顺时针运行的运行编号（从北开始） ）。请注意，该ID的前缀为“：”。如果通过内部边缘连接的传入和传出边缘具有多个通道，则内部边缘也具有多个通道（根据这两个边缘之间的连接数）。如果是多车道内部边缘，则INDEX会以车道数跳跃，因此EDGE_INDEX + LANE_INDEX = CONNECTION_INDEX。

下表中给出了这些属性。

| **名称** | **类型**     | **描述**                      |
| -------- | ------------ | ----------------------------- |
| **ID**   | id（字符串） | 内部边缘的id                  |
| function | “ internal”  | 始终以“ internal”表示内部优势 |

l 止损抵销

每个边缘或车道可能会携带一个stopOffset子元素，以为某些类别的车辆指定额外的停车偏移量：

<edge id="<ID>">

  <stopOffset value="<distance in m.>" vClasses="<space-separated list of vClasses>" />

  <lane id="<ID>" index="<INDEX>" ... >

​    <stopOffset value="<distance in m.>" exceptions="<space-separated list of vClasses>" />

  </lane>

  ...

</edge>

 

为边缘定义该元素将影响边缘的所有不拥有自己stopOffset元素的车道。请注意，可以定义受停止偏移量影响的所有车辆类别（属性vClasses），也可以定义不受影响的所有车辆类别（属性exceptions）。您不能同时使用这两个属性。value-attribute指定从车道末端停止指定车辆类别所需的距离。

 

| **名称**       | **类型**     | **描述**                             |
| -------------- | ------------ | ------------------------------------ |
| **value**      | 值（双精度） | 停止偏移量为正值，以米为单位。       |
| **vClasses**   | vClass列表   | 指定stopOffset适用于哪些车辆类别。   |
| **exceptions** | vClass列表   | 指定stopOffset不适用于哪些车辆类别。 |

l 信号灯

交通信号灯程序定义交通信号灯的阶段。

 <tlLogic id="<ID>" type="<ALGORITHM_ID>" programID="<PROGRAM_ID>" offset="<TIME_OFFSET>">

​    <phase duration="<DURATION#1>" state="<STATE#1>"/>

​    <phase duration="<DURATION#1>" state="<STATE#1>"/>

​    ... further states ...

​    <phase duration="<DURATION#n>" state="<STATE#n>"/>

  </tlLogic>

l 交界处和通行权

交汇处代表不同的河流交叉处的区域，包括车辆穿越交叉路口时必须遵循的通行规则。一个示例可能是：

<junction id="<ID>" type="<JUNCTION_TYPE>" x="<X-POSITION>" y="<Y-POSITION>"

​     incLanes="<INCOMING_LANES>" intLanes="<INTERNAL_LANES>"

​     shape="<SHAPE>">

  ... requests ...

</junction>

联结本身由以下属性描述：

| **名称**     | **类型**      | **描述**                                                     |
| ------------ | ------------- | ------------------------------------------------------------ |
| **ID**       | id（字符串）  | 交界处的编号；请注意，控制该路口时，交通信号灯定义必须使用相同的ID。 |
| x            | X位置（真实） | 相交的x坐标                                                  |
| y            | y位置（真实） | 相交的y坐标                                                  |
| z            | z位置（真实） | 相交的（可选）z坐标                                          |
| **incLanes** | 编号清单      | 在交叉路口结束的车道的ID；按方向排序，顺时针，向上= 0        |
| **intLanes** | 编号清单      | 交叉路口内车道的ID                                           |
| **shape**    | 职位清单      | 描述十字路口道路边界的多边形                                 |
| customShape  | 布尔          | 形状是否由用户自定义（因此不应由[netconvert](https://sumo.dlr.de/docs/netconvert.html)或[netedit](https://sumo.dlr.de/docs/Netedit/index.html)重建），默认为*False* |

请注意，连接点的x / y位置描述的是给定值，而不是连接点的计算中心。允许两个节点具有相同的位置。

l 链接

普通连接或“链接”描述了可以从输入车道到达哪些输出车道。另外，给出了用于通过交叉路口的第一个车道。其他信息描述了连接的方向和“状态”。如果连接由交通信号灯控制，则会给出交通信号灯的名称以及在交通信号灯的相位定义内控制此连接的信号的索引。连接编码为：

<connection from="<FROM_EDGE_ID>" to="<TO_EDGE_ID>" fromLane="<FROM_LANE_INDEX>" toLane="<TO_LANE_INDEX>"

​      via="<VIA_LANE_ID>" tl="<TRAFFIC_LIGHT_ID>" linkIndex="12" dir="r" state="o"/>

| **名称**      | **类型**                                                     | **描述**                                                     |
| ------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| from          | 边缘ID（字符串）                                             | 连接开始的入站边缘的ID                                       |
| to            | 边缘ID（字符串）                                             | 连接结束的出站边缘的ID                                       |
| **fromLane**  | 索引（无符号整数）                                           | 连接开始的入站边缘的车道                                     |
| **toLane**    | 索引（无符号整数）                                           | 连接终止的输出边缘的通道                                     |
| **via**       | 车道编号（字串）                                             | 用来在连接处传递此连接的通道的ID                             |
| **tl**        | 交通灯ID（字符串）                                           | 控制此连接的交通信号灯的ID；如果连接不受交通信号灯控制，则缺少属性 |
| **linkIndex** | 索引（无符号整数）                                           | 负责交通信号灯内连接的信号的索引；如果连接不受交通信号灯控制，则缺少属性 |
| **dir**       | 枚举（“ s” =直行，“ t” =转弯，“ l” =左，“ r” =右，“ L” =部分左，R =部分右，“ invalid” =无方向） | 连接方向                                                     |
| **state**     | 枚举（“-” =死角，“ =” =相等，“ m” =次要链接，“ M” =主要链接，仅红绿灯：“ O” =控制器关闭，“ o” =黄色闪烁，“ y” =黄色次要链接，“ Y” =黄色主要链接，“ r” =红色，“ g” =绿色次要链接，“ G”绿色主要链接） | 连接状态                                                     |

在不使用netconvert创建这些连接时（不建议使用），应考虑到具有内部通道的连接遵循特殊模式。例如，当通道1_f_0需要通过1_v_0连接到1_t_0时，存在以下连接条目：[从= 1_f_0，通过= 1_v_0到= 1_t_0]和[从= 1_v_0到= 1_t_0]。如果省略后者，SUMO将不会加载网络。如果在必要的连接旁边存在连接[从= 1_f_0到= 1_v_0]，它也不会加载。

 

l 链接指数

每个连接都有关联的索引，可以通过自定义gui设置并激活Junctions-> Show ... index来在 sumo-gui中显示该索引。这些索引通常是相同的，但可以彼此独立配置。

交界处索引：该索引在#Requests部分中进行了 描述。无法修改。索引对应于<junctions>s incLanes属性的顺序，也对应于元素的顺序<connection>。这些索引从顶部开始沿顺时针方向（在右侧网络中）围绕结点运行。

TLS索引：此索引分配给由交通信号灯控制的连接 。对于连接的交通信号灯（控制多个路口），该索引不同于路口索引，因为后者不再唯一。可以使用.con.xml 文件配置TLS索引。自定义索引可用于创建信号组（始终具有相同状态并共享相同索引的多个连接），从而简化交通灯阶段的状态定义。

l 回旋处

网络中的环形交叉路口会影响通行权（在网络构建过程中在路口的Requests <request>元素中进行了编码 ）。它们在网络文件中的存在有两个原因：

它有助于使用netconvert重新导入.net.xml-文件

变道模型可能会考虑回旋处

每个回旋处均由其节点和边线定义（有些冗余）：

<roundabout nodes="nodeID1 nodeID2 ..." edges="edgeID1 edgeID2 ..."/>

## 2    抽象网络生成

netgenerate允许生成三种类型的抽象网络：网格，蜘蛛网和随机网络。

您要创建的网络类型必须使用以下开关之一声明：-- grid，-- spider或--rand。您可以使用--output <文件名>或-o <文件名>简短地提供要生成的网络名称，默认为“ net.net.xml”。

### 2.1  网格状网络

您可以描述要建立的在x方向和y方向上的结点数量，以及它们之间应该相距多远。接合点数量的参数为--grid.x-number和--grid.y-number，而接合点之间的距离为--grid.x-length和--grid.y-length。如果要构建两个轴的值都相同的网络，请使用--grid.number和--grid.length。长度以米为单位。可以给出另一个选项--grid.attach-length，这会在网格的边界处添加给定长度的街道，以使所有交叉口都具有四个街道（尚不可能在x和y方向上具有不同的附着长度）。

用于构建的示例用法可能是：

netgenerate --grid --grid.number=10 --grid.length=400 --output-file=MySUMOFile.net.xml

netgenerate --grid --grid.x-number=20 --grid.y-number=5 \

 --grid.y-length=40 --grid.x-length=200 --output-file=MySUMOFile.net.xml

这些调用将分别生成以下网络：

![https://sumo.dlr.de/docs/images/Netgen_grid1.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image055.gif)

![https://sumo.dlr.de/docs/images/Netgen_grid2.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image056.gif)

### 2.2  类蜘蛛网络

蜘蛛网是由将它们划分的轴数（参数--spider.arm-number或--arms，默认值为13），由其构成的圆的数量（--spider.circle-number或-界，默认为20）和所述圈之间的距离（--spider.space半径或--radius以米为单位，默认值是100）。

（可选）您可以通过指定--spider.omit-center或--nocenter来省略网络的中央结。这也提供了一种生成圆形网络的简便方法。例如使用

netgenerate --spider --spider-omit-center --output-file=MySUMOFile.net.xml

 

--spider --spider.arm-number=10 --spider.circle-number=10 \

 --spider.space-radius=100 --output-file=MySUMOFile.net.xml

 

 netgenerate --spider --spider.arm-number=4 --spider.circle-number=3 \

 --spider.space-radius=100 --output-file=MySUMOFile.net.xml

![https://sumo.dlr.de/docs/images/Netgen_spider1.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image057.gif)![https://sumo.dlr.de/docs/images/Netgen_spider2.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image058.gif)

### 2.3  随机网络

随机网络生成器按照其名称所说的进行操作，它构建随机网络。可能会更改一些设置：

--rand.iterations <INT>：

--rand.bidi-probability <FLOAT>：建立反向边缘的概率

--rand.max-distance <FLOAT>：最大边缘长度

--rand.min-distance <FLOAT>：最小边长

--rand.min-angle <FLOAT>：两条边之间的最小角度

--rand.num-tries <INT>：

--rand.connectivity <FLOAT>：

--rand.neighbor-dist1 <浮点>：

--rand.neighbor-dist2 <浮点>：

--rand.neighbor-dist3 <FLOAT>：

--rand.neighbor-dist4 <浮点>：

--rand.neighbor-dist5 <FLOAT>：

--rand.neighbor-dist6 <FLOAT>：

一个例子：

netgenerate --rand -o MySUMOFile.net.xml --rand.iterations=200

此调用将生成以下网络：

![https://sumo.dlr.de/docs/images/Netgen_random1.gif](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image059.gif)

## 3    使用netconvert导入网络

## 4    使用netedit创建和修改网络

netedit是一个可视化网络编辑器。它可用于从头开始创建网络以及修改现有网络的所有方面。具有强大的选择和突出显示界面，它也可以用于调试网络属性。netedit建立在netconvert之上。作为一般经验法则，netconvert可以做的任何事情，netedit也可以做的。netedit具有无限的撤消/重做功能，因此可以快速纠正编辑错误。编辑命令通常用鼠标左键发出（根据当前的编辑模式）。用户界面紧跟sumo-gui的界面。其他键盘热键记录在帮助菜单。

### 4.1  输入

netedit是一个GUI应用程序，可通过菜单选择输入。支持以下输入格式：

SUMO-net文件

OSM文件

netconvert配置文件

### 4.2  输出

SUMO-net文件

纯XML文件

### 4.3  热键

| **文件快捷方式**     | **钥匙**         | **描述**                             |
| -------------------- | ---------------- | ------------------------------------ |
| 新窗户               | Ctrl + Shift + N | 打开一个新的netedit窗口              |
| 新网络               | Ctrl + N         | 创建一个新的网络                     |
| 开放网络             | Ctrl + O         | 打开现有网络                         |
| 开放式配置           | Ctrl + T         | 打开现有的SUMO配置                   |
| 导入国外网络         | Ctrl + F         | 导入国外网络                         |
| 重装                 | Ctrl + R         | 重新加载网络                         |
| 保存网络             | Ctrl + S         | 保存网络                             |
| 将网络另存为         | Ctrl + Shift + S | 将网络保存到另一个文件中             |
| 保存纯XML            | Ctrl + L         | 将网络另存为纯XML                    |
| 保存已加入的路口     | Ctrl + J         | 保存网络的联接结点                   |
| 加载附加内容和形状   | Ctrl + A         | 加载其他文件                         |
| 保存附加内容和形状   | Ctrl + Shift + A | 将其他文件保存在文件中               |
| 负载需求元素         | Ctrl + D         | 加载形状的文件                       |
| 保存需求要素         | Ctrl + Shift + D | 将需求元素保存在文件中               |
| 加载TLS程序          | Ctrl + K         | 加载形状的文件                       |
| 保存TLS程序          | Ctrl + Shift + K | 将兴趣点保存在文件中                 |
| 关闭                 | Ctrl + W         | 紧密的网络                           |
| **辑捷径**           | **钥匙**         | **描述**                             |
| 撤消                 | Ctrl + Z         | 撤消上一次更改                       |
| 重做                 | Ctrl + Y         | 重做上一次更改                       |
| **超模式快捷方式**   | **钥匙**         | **描述**                             |
| 网络                 | F2               | 更改为超级模式网络（默认）           |
| 要求                 | F3               | 更改为超级模式需求（意味着重新计算） |
| 数据                 | F4               | 更改为超级模式数据（意味着重新计算） |
| **通用模式快捷方式** | **钥匙**         | **描述**                             |
| 删除                 | d                | 更改为“删除”模式                     |
| 检查                 | 一世             | 更改为“检查”模式                     |
| 选择                 | 小号             | 更改为模式“选择”                     |
| 移动                 | 中号             | 更改为“移动”模式                     |
| **网络模式快捷方式** | **钥匙**         | **描述**                             |
| 创建边缘             | E                | 更改为“创建边缘”模式                 |
| 联系                 | C                | 更改为“连接”模式                     |
| 禁酒令               | w ^              | 更改为“禁止”模式                     |
| 红绿灯               | Ť                | 更改为“交通灯”模式                   |
| 额外的               | 一种             | 更改为“其他”模式                     |
| 穿越                 | [R               | 更改为“穿越”模式                     |
| 兴趣点               | P                | 更改为“  POI-Poly”模式               |
| **需求模式快捷方式** | **钥匙**         | **描述**                             |
| 建立路线             | [R               | 更改为“创建路线”模式                 |
| 创建车辆             | 伏特             | 更改为“创建车辆”模式                 |
| 创建车辆类型         | Ť                | 更改为“创建车辆类型”模式             |
| 创建止损             | 一种             | 更改为“创建停靠站”模式               |
| 创建人员类型         | w ^              | 更改为“创建人员类型”模式             |
| 创造人物             | P                | 更改为“创建人”模式                   |
| 创建人员计划         | C                | 更改为“创建人员计划”模式             |
| **数据模式快捷方式** | **钥匙**         | **描述**                             |
| 边缘数据             | E                | 更改为“创建边缘数据”模式             |
| 边缘关系数据         | E                | 更改为“创建边缘关系数据”模式         |
| **处理快捷方式**     | **钥匙**         | **描述**                             |
| 计算结点             | F5               | 计算网络结点                         |
| 清洁结               | F6               | 清洁网络连接                         |
| 加入选定的路口       | F7               | 加入网络的选定路口                   |
| 选项                 | F10              | 打开选项对话框                       |
| **找到快捷方式**     | **钥匙**         | **描述**                             |
| 找到连接点           | Shift + j        | 打开对话框以找到路口                 |
| 定位边缘             | Shift + e        | 打开对话框以找到边缘                 |
| 找到TLS              | Shift + T        | 打开对话框以找到交通灯               |

 

| **帮助快捷方式** | **钥匙** | **描述**                   |
| ---------------- | -------- | -------------------------- |
| 在线文件         | F1       | 在网络浏览器中打开在线文档 |
| 关于             | F12      | 打开关于对话框             |

 

| **文字版捷径** | **钥匙** | **描述**                              |
| -------------- | -------- | ------------------------------------- |
| 切             | Ctrl + X | 剪切文本字段的选定文本                |
| 复制           | Ctrl + C | 复制文本字段的选定文本                |
| 粘贴           | Ctrl + V | 将先前剪切/复制的文本粘贴到文本字段中 |
| 选择所有文字   | Ctrl + A | 选择文本字段中的所有文本              |

除了这些热键之外，还支持用于在sumo-gui中移动和缩放的所有热键。

<Button-Left>：执行模式特定的操作

<Button-Right>：打开上下文菜单

<Button-Right-Drag>：更改缩放

<Button-Left-Drag>：移动视图（平移）

在“移动”模式下指向边缘：移动或创建几何点

在“移动”模式下指向路口：移动路口

在“移动”模式下，指向选定对象：移动所有选定的结点和包括几何在内的边。如果选择了边缘的两个交点，请移动整个几何。否则，仅将几何图形移动到光标附近

<ESC>

在“创建边缘”模式下：清除当前选定的源结

在“选择”模式下：清除当前选择；取消矩形选择

在“连接”模式下：取消选择当前车道并取消所有更改

在“交通信号灯”模式下：将更改恢复为当前的交通信号灯

编辑接合点形状时：中止编辑当前接合点形状

<DELETE>：删除所有当前选择的项目

<SHIFT>：

在“选择”模式下：按住<SHIFT>并拖动鼠标进行矩形选择

在“选择”模式下：<SHIFT>-左键单击选择车道而不是边缘

在“检查”模式下：<SHIFT>-左键单击检查车道而不是边缘

在“删除”模式下：<SHIFT>-左键单击删除泳道而不是边缘

<CTRL>：

在“创建边缘”模式下，允许在不定义结点的情况下移动视图

在“创建附加项”模式下，允许在不添加附加项的情况下移动视图

在“ POI-Poly”模式下，允许在不添加POI的情况下移动视图

<Enter>

在“检查”模式下：确认属性更改

在“连接”模式下：取消选择当前通道并保存所有更改

在“交通灯”模式下：将更改保存到当前交通灯

在“ TAZ”模式下：将更改保存到当前交通信号灯

编辑交汇点形状时：保存当前交汇点形状

### 4.4  处理菜单

计算结点（F5）：重新计算所有结点的几何形状和逻辑。当进入需要此信息的模式（连接，交通灯）时，将自动触发此操作。

清洁交界处（F6）：删除所有没有任何相邻边的交界处（保存网络时不包括这些交界处。它们保留在编辑器中，直到被清理以备将来重用为止）。

连接选定的连接点（F7）：将选定的连接点连接到单个连接点（请参见连接连接点）。

选项（F10）：检查并设置所有选项。这些选项与netconvert在命令行或配置中接受的选项相同。

## 5    高程数据建立

可以从以下来源导入高程数据

直接从网络输入

从OSM（有一些技巧）

从OpenDRIVE或Shapefile

通过应用补充文件中的额外数据

从shape文件目通过使用netconvert选项--heightmap.shapefiles

从灰度高度映射使用netconvert选项--heightmap.geotiff。

来自edg.xml文件作为形状规范的一部分

通过在netedit移动模式下沿z轴移动几何点和结点来实现。

## 6    坐标

SUMO网络始终以笛卡尔坐标（米）进行编码，并且可能包含地理参考信息以允许转换为lon，lat。默认情况下，笛卡尔坐标使用UTM投影，其原点已更改为，因此网络的左下角为0,0。

从OSM导入网络时 ，地理参考会自动包含在生成的.net.xml文件中

从plain-xml 文件导入网络时 ，坐标可以lon，lat给出，并可以使用--proj.utm等投影选项进行导入

从Shapefile导入网络时，地理参考的可用性取决于源数据的格式。

### 6.1  检查地理坐标

在sumo-gui中，右键单击地理参考网络中的任意位置时，可以使用将光标地理位置复制到剪贴板的选项。将所得的纬度，经度的坐标适合粘贴到任何地图引擎如[maps.google.com]或[maps.bing.com]。此外，窗口右下角显示了网络坐标以及光标位置处的地理坐标。

### 6.2  坐标转换

使用 TraCI，可以在网络坐标（m，m）和地理坐标（lon，lat）之间转换坐标，反之亦然

使用sumolib ，可以在网络坐标（m，m）和地理坐标（lon，lat）之间转换坐标，反之亦然

### 6.3  坐标输出

可以使用netconvert命令将网络导出为地理坐标中的plain-xml

netconvert --sumo-net-file myNet.net.xml --plain-output-prefix plain --proj.plain-geo

 

通过添加选项--fcd-output.geo，可以在地理坐标中获得FCD输出

# 第四章 需求模型

## 1    SUMO需求建模简介

生成网络后，可以使用sumo-gui对其进行查看 ，但不会有汽车在行驶。仍然需要有关车辆的某种描述。这称为交通需求。从现在开始，我们将使用以下术语：行程是由起点（街道），目的地终点和出发时间定义的从一个地方到另一个地方的车辆运动。一个途径是扩大之旅，这意味着，该路由定义不仅包含第一个和最后边缘，但所有边缘的车辆会通过。相扑和 相扑需要路线作为车辆运动的输入。有几种生成SUMO路由的方法。选择取决于您可用的输入数据：

使用行程定义：

如上所述，每个行程至少包括起点和终点以及出发时间。当您要手动创建需求或编写自己的脚本以导入自定义数据时，这很有用。您可以使用 duarouter将旅程变成路线。请参阅 Demand / Shortest_or_Optimal_Path_Routing 和 Demand / Dynamic_User_Assignment，或者您可以将行程直接加载到相扑中 （更多详细信息）。

使用流定义：

这与使用行程定义的方法大致相同，但是使用此方法可以将出发和到达边缘相同的车辆合并

使用随机化

如果您无权进行任何测量，但是结果非常不切实际，这是获取流量的一种快速方法。请参阅 工具/Trip#randomTrips.py

使用OD矩阵

交通当局通常可以提供起点-目的地矩阵（或OD矩阵）。必须使用od2trips将它们转换为行程 。请参阅 需求/导入_O / D_矩阵， 需求/ Shortest_or_Optimal_Path_Routing 和 需求/动态_用户_分配。

使用流量定义和转向比

人们也可以将目的地边缘留给流量，而在路口使用转弯比。参见 jtrrouter。

使用探测器数据（观测点）

当局通常使用感应环路和类似设备来测量流量。使用dfrouter，您可以使用此数据来生成需求。请参阅 Demand / Routes_from_Observation_Points。

用手

您当然可以手动生成路由XML文件。参见 Definition_of_Vehicles，_Vehicle_Types，_and_Routes。

使用人口统计

程序activitygen可用于将人口统计数据转换为交通需求。请参阅 基于需求/活动的需求生成。

使用其他来源的数据

请参见SUMO_User_Documentation＃Demand_Modelling

 

到目前为止，SUMO软件包包含四个用于生成路线的应用程序。duarouter负责从其他仿真包中导入路线或其定义，并使用Dijkstra的最短路径算法来计算路线。此外，结合模拟， duarouter可以计算C. Gawron制定的动态用户分配。 如果要统计流量，在路口使用流量和转弯百分比，则可以使用jtrrouter。od2trips可帮助您将OD矩阵（起点/终点矩阵）转换为行程。该 dfrouter计算从给定的观测点测量路线。

 

## 2    车辆定义车辆类型路线

## 3    使用netedit定义流量需求

### 3.1  路线

需求要素是netedit用来定义SUMO的车辆需求的要素。所有这些元素都可以在超级模式需求（F3）中创建，检查和选择。

 

![https://sumo.dlr.de/docs/images/GNERoute.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image061.jpg)

### 3.2  车辆

车辆是NETEDIT中在一定路径上通过街道（边缘或车道）的任何移动元素的表示形式。

单击起点和终点就定义了行程。NETEDIT会自动计算单击边之间的短路最小路径。如果用户定义了“过孔”边缘列表，则还将使用过孔边缘来计算路径。在检查行程时绘制路径。

![https://sumo.dlr.de/docs/images/GNETrip.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image063.jpg)

在路线上定义的车辆遵循由给定路线定义的路径。要创建它，只需在路线上单击即可。

![https://sumo.dlr.de/docs/images/GNEVehicle.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image065.jpg)

单击网络中的边沿列表来定义具有嵌入式路线的车辆。NETEDIT会自动计算单击边之间的短路最小路径。

![https://sumo.dlr.de/docs/images/GNEVehicleEmbeddedRoute.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image067.jpg)

单击起点和终点边来定义流。NETEDIT会自动计算单击边之间的短路最小路径。如果用户定义了“过孔”边缘列表，则还将使用过孔边缘来计算路径。在检查流量的同时绘制路径。

![https://sumo.dlr.de/docs/images/GNEFlow.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image069.jpg)

在路由上定义的流遵循由给定路由定义的路径。要创建它，只需在路线上单击即可。

![https://sumo.dlr.de/docs/images/GNEFlowRoute.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image071.jpg)

单击网络中的边缘列表，即可定义具有嵌入式路由的流。NETEDIT会自动计算单击边之间的短路最小路径。

![https://sumo.dlr.de/docs/images/GNEFlowEmbeddedRoute.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image073.jpg)

### 3.3  车辆类型

使用“车辆类型”元素作为父级来定义车辆。有两种编辑载具的方法。第一个是框架，可以在其中创建和编辑其基本属性，第二个框架是“属性编辑器”，在其中可以编辑所有属性。

![https://sumo.dlr.de/docs/images/GNEVehicleType.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image075.jpg)

![https://sumo.dlr.de/docs/images/GNEVehicleTypeDialog.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image077.jpg)

停止将车辆停在车道停止的给定位置。可以在车道上或停靠处（BusStop，ContainerStop，ChargingStation或停车区）定义停靠点，并且始终在父元素（路线或车辆）中定义停靠点

### 3.4  人数

人代表NETEDIT网络中的行人。所有人都需要一个人计划，这个人计划可以是散步，人行，乘车或停车。人员计划可以从边缘或busStop开始或结束。

![https://sumo.dlr.de/docs/images/GNEPedestrian.png](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image079.jpg)

## 4    模拟公共交通

## 5    模拟个人和旅行链

## 6    物流模拟

## 7    最短或最佳路径路由

## 8    多式联运

## 9    仿真中的布线

## 10   计算动态用户分配

给一个车辆初始-目的地关系，通过仿真来决定从初始地点到路网的行驶边界。其中最简单的方法是使用Djikstra 或者A*算法来去计算最优和最快的路线。算法需要假设在每条路网的行驶时间。该时间在仿真之前并不能完全知道，因为其时间还要取决于在路网上车辆的数量。在交通负载路网中考虑行驶时间来确定合适路线的问题被叫做用户分配。SUMO在下面提供不同的工具去解决这个问题。

### 10.1      迭代的任务（动态用户平衡）

<SUMO_HOME>/tools/assign/duaIterate.py 工具被用于计算动态用户平衡。

python duaIterate.py -n <network-file> -t <trip-file> -l <nr-of-iterations>

duaIterate.py支持很多选项，任何没有被列出的选项可以通过duaIterate.py –help然后可以得到sumo选项的介绍。

该脚本试图计算用户平衡。即，它试图为每辆车找到一条路线（上述旅行文件中的每次旅行），以使每辆车都无法通过使用不同的方式来降低其行驶成本（通常是行驶时间）路线。它如此反复地

l 呼叫duarouter以已知的最新边际成本在网络中路由车辆（从空网络行驶时间开始）

l 调用相扑来模拟“真实的”旅行时间，这是由计算出的路线得出的。结果边缘成本在净路由步骤中使用。

可以根据所使用的选项将迭代次数设置为动态确定的固定次数。为了确保收敛，采用了不同的方法来根据路线成本计算路线选择概率（因此，车辆并不总是选择“最便宜”的路线）。通常，路由器会在每次迭代中将新路线添加到每个车辆的路线集合中（至少在当前路线中没有一个是“最便宜的”的情况下），并且可以根据以下所述的路线选择机制进行选择。

在duarouter的连续调用之间，.rou.alt.xml格式不仅用于记录当前的最佳路由，而且还用于记录先前计算的替代路由。这些路线在路线分布中收集，并在确定下一个模拟步骤中要驾驶的实际路线时使用。这并不总是目前成本最低的一种，而是通过以下所述的可配置算法从替代路线的分布中抽样的。

### 10.2      路线选择算法

下面实现的两种方法称为 Gawron和 Logit。每种方法的输入是网络边缘上的权重或成本函数（w），来自模拟或默认成本（在第一步或尚未走过的边缘），以及一组线路![http://latex.codecogs.com/gif.latex?R](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image080.gif)，其中每个路径![http://latex.codecogs.com/gif.latex?r](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image081.gif)有一个老的成本![http://latex.codecogs.com/gif.latex?c_r](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image082.gif)和老概率![http://latex.codecogs.com/gif.latex?p_r](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image083.gif)（从最后一次迭代），需要一个新的成本![http://latex.codecogs.com/gif.latex?c_r%27](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image084.gif)和新的可能性![http://latex.codecogs.com/gif.latex?p_r%27](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image085.gif)。

#### 10.2.1  Gawron算法

Gawron算法计算出从每个驾驶员的一组备用路线中进行选择的概率。考虑以下值来计算这些概率：

上一个模拟步骤中沿使用路线的行驶时间

一组替代路线的边缘行驶时间总和

先前选择路线的可能性

#### 10.2.2  Logit算法

Logit机制将固定公式应用于每条路线，以计算新的概率。它忽略了旧成本和旧概率，并直接将路线成本作为上一次仿真得出的边成本之和。

![http://latex.codecogs.com/gif.latex?c_r%27%20=%20\sum_%7be\in%20r%7dw(e)](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image086.gif)

概率是通过指数函数计算得出的，该函数的参数按所有路径值的总和进行缩放：

![http://latex.codecogs.com/gif.latex?p_r%27%20=%20\frac%7b\exp(\theta%20c_r%27)%7d%7b\sum_%7bs\in%20R%7d\exp(\theta%20c_s%27)%7d](file:///C:/Users/DIANTA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image087.gif)

### 10.3      中止

选项--max-convergence-deviation可用于检测收敛并自动中止迭代。否则，将使用固定数量的迭代。一旦脚本完成，任何生成的.rou.xml文件都可以用于仿真，但是最后一个应该是最好的。

### 10.4      使用范围

默认情况下，车辆类型取自输入的行程文件，然后通过duarouter迭代传播（始终作为书面路线文件的一部分）。为了使用附加文件中的车辆类型定义，必须设置其他选项

duaIterate.py -n ... -t ... -l ... 

 --additional-file <FILE_WITH_VTYPES> 

 duarouter--aditional-file <FILE_WITH_VTYPES> 

 duarouter--vtype-output dummy.xml

以字符串duarouter开头的选项将直接传递到duarouter，并且必须使用选项vtype-output dummy.xml来防止在生成的输出文件中重复定义车辆类型。

### 10.5      及时分配

上面的迭代用户分配的替代方法是增量分配。当<trip>直接在sumo中使用input 而不是将<vehicle>s与预定义路线一起使用时，这会自动发生。在这种情况下，每辆车在出发时都会计算出最快的路径计算，这可以防止所有车辆盲目地驶入同一堵车，并且凭经验可以很好地工作（对于较大的场景）。

使用自动路由/路由设备机制来计算此增量分配的 路由。由于此设备允许各种配置选项，因此可以使用脚本 Tools / Assign＃one-shot.py自动尝试不同的参数设置。

## 11   产生行人交通需求

## 12   生成车辆类型分布以对车队进行建模

### 12.1      使用工具createVehTypeDistribution.py

通过从所需vType参数的可配置值分布中采样来创建车辆类型分布。例子：

python tools/createVehTypeDistribution.py config.txt

唯一需要的参数是配置文件，格式如下所示（示例config.txt）：

tau; normal(0.8,0.1)

sigma; normal(0.5,0.2)

length; normal(4.9,0.2); [3.5,5.5]

param; myCustomParameter; normal(5, 2); [0, 12]

vClass; passenger

carFollowModel; Krauss

在配置文件中，每个车辆类型属性使用一行。语法为：[param; ] <AtrributeOrParameterName>; <ValueOrDistribution> [; <限制>]

如果在行的开头给出了前缀参数，则假定要对车辆参数的值（作为param元素的子vehicle元素）进行采样。否则，对元素的属性值vehicle进行采样。ValueOrDistribution可以是字符串，标量值或分布定义。可用的发行版及其语法为：

 

mu和sd为浮点数的“normal（mu，sd）”：具有均值mu和标准差sd的正态分布。

“normalCapped（mu，sd，min，max）”默认情况下，不接受任何负值，但可以通过设置负下限来启用。

mu和sd为浮点数的“lognormal(mu,sd)”：具有均值mu和标准差sd的正态分布。

限制a和b为浮点数的“uniform(a,b)”：a和b之间的均匀分布。

参数为alpha和beta的“gamma(alpha,beta)”：Gamma分布。

其他选项：

--output-file配置要写入的输出文件的名称

--name创建的发行版的名称

--size要填充分布的要采样的s的数量

--seed设置随机数生成器的种子

l 从单个车辆的测量值中检测参数

为了获得均值和偏差，必须从数据集中获得多个值。建议以下内容：

accel：每辆车的最大（或高百分位数）加速度

减速：每辆车的最大减速度（或高百分比）

speedFactor：每辆车的速度/ speedLimit的最大（或高百分位数）商

### 12.2      extractTest.py

如果您想运行包含在测试文件夹中的模拟方案，此脚本将提取测试方案。

python tools/extractTest.py <path to test directory>

或使用在线测试提取。在在线工具中，您可以输入所需测试的路径（例如，<SUMO_HOME> / tests / sumo / extended / rerouter / use_routing_device）到表单中，并获得包含所有文件的zip文件。

### 12.3      generateParkingLots.py

该脚本生成停车场。例子：

python tools/generateParkingLots.py -b <xmin, ymin, xmax, ymax> -c <connecting edge>

 [-i <parking-id> -n <number of parking spaces> -l <space-length> -a <space-angle> ...]

或者使用下列代码：

python tools/generateParkingLots.py -x <x-pos> -y <y-pos> -c <connecting edge>

 [-i <parking-id> -n <number of parking spaces> -l <space-length> -a <space-angle> ...]

必需的参数是停车场和连接边缘（-连接边缘）的形状（-边界框）或位置（--x轴和--y轴）。可以通过调用python tools / generateParkingLots.py --help获得更多选项。

 

其他选项：

--parking-id定义停车场的名称/ ID

--parking-spaces定义停车位的数量

--start-position定义停车场入口/出口的起始位置

--end-position定义停车场入口/出口的终点位置

--space-length定义每个停车位的长度

--space-angle定义停车位的角度

--x-space-distance定义两个停车位位置之间的横向距离（x方向）

--y-space-distance定义两个停车位位置之间的纵向距离（y方向）

--rotation-degree定义停车场的旋转角度

--adjustrate-x定义存在旋转的x轴的修改率

--adjustrate-y定义存在旋转的y轴的修改率

--output-suffix输出后缀

--fullname停车区的全名

--verbose告诉我你在做什么

### 12.4      generateStationEdges.py

该脚本为每个公共交通站点生成一个行人专用道（以.nod.xml和.edg.xml文件的形式。输出适用于扩展纯铁路网络，而行人基础设施的最小限度用于出发，更改火车和例如：

python tools/generateStationEdges.py rail.net.xml stops.xml

 netconvert -s rail.net.xml -e stops.access.edg.xml -n stops.access.nod.xml --ptstop-files stops.xml -o railForPersons.net.xml --ptstop-output stopsWithAccess.xml

##  
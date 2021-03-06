---
keyword: MapReduce
---

# 新建MapReduce任务

本文为您介绍如何基于Dataphin构建MapReduce类型的离线计算任务。

完成JAR资源包的上传，详情请参见[新建资源](/cn.zh-CN/数据开发/数据处理/新建资源.md)。

MapReduce任务中引用到的JAR资源包需提前创建，因此需要您在资源管理中上传JAR资源包，然后在MapReduce代码任务中引用。

1.  登录[Dataphin控制台](https://dataphin.console.aliyun.com/workingArea)。

2.  在Dataphin控制台页面，选择工作区地域后，单击**进入Dataphin\>\>**。

    您可以通过以下方式，快速进入数据开发模块：

    -   单击**快速开始相关工作**区域的**数据研发**。
    -   单击**快速进入研发项目**区域的**Dev**或**Basic**项目，选择开发数据的项目空间。
    **说明：**

    -   如果您通过**快速开始相关工作**进入数据开发模块，则跳过步骤3.i。
    -   如果您通过**快速进入研发项目**进入数据开发模块，则跳过步骤3.ii。
3.  进入**计算任务**页面。

    1.  在Dataphin首页，单击顶部菜单栏的**研发**。

    2.  在数据**开发**页面，单击项目名称后的![test](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3497549951/p110384.png)图标后，单击**Dev**或**Basic**页签，选择数据开发的项目空间（**Dev**或**Basic**项目）。

        如果您当前访问的是**Dev**或**Basic**项目，且项目空间为您的数据开发空间，则不需要选择项目空间。

    3.  在数据**开发**页面，单击**数据处理**页签。

        如果进入数据**开发**页面后，系统默认进入**数据处理**页签，则无需再次单击**数据处理**页签。

    4.  在**数据处理**页签，单击左侧导航栏![agaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8980863061/p176215.png)**计算任务**图标。

4.  在**计算任务**页面，进入新建MapReduce任务文件对话框。

    -   单击**计算任务**后的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8397549951/p72394.png)图标，选择**MAXC任务** \> **MAX\_COMPUTE\_MR**。
    -   单击项目名称后的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8397549951/p72706.png)图标，选择**数据处理** \> **计算任务** \> **MAX\_COMPUTE\_MR**。
    -   在**开发**首页，单击**MAXC\_MR**后的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8397549951/p72708.png)图标。
5.  编写并运行代码。

    1.  在**新建文件**对话框，配置参数。

        ![fagaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0097549951/p88553.png)

        |参数|描述|
        |--|--|
        |**名称**|填写离线计算任务的名称，例如MR。|
        |**调度类型**|选择任务的调度类型。**调度类型**包括：         -   **周期性节点**，自动参与系统的周期性调度。
        -   **手动节点**，需要手动触发任务的运行。 |
        |**描述**|填写对任务的简单描述。|
        |**选择目录**|选择离线计算任务的目录。|

    2.  单击**确定**。

    3.  在**代码编写**页面，编写MapReduce离线计算任务的代码，详情请参见[MapReduce](/cn.zh-CN/开发/MapReduce/概述/MapReduce.md)。

        ![faga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0097549951/p88555.png)

        代码示例如下：

        ```
        @resource_reference{"mr_odps.jar"}
        add jar mr_odps.jar as momo.jar -f;
        jar -resources  momo.jar -classpath mr_odps.jar hive.WordCountOdps wc_in wc_out;
        ```

    4.  检查代码。

        代码编写完成后，单击**预编译**，系统帮助您检查编写的SQL代码的语法。

        如果预编译失败，您可以单击页面上方的**格式化**，系统自动帮助您调整语法格式。调整完格式，您可以单击**刷新**，刷新页面上的代码。

    5.  代码编写完成后，单击页面右上方的**执行**，运行代码。

6.  配置调度参数。

    -   如果离线计算任务的调度类型为**周期性节点**，则需要配置调度参数，详情请参见[调度配置](/cn.zh-CN/数据开发/数据处理/调度配置.md)。
    -   如果离线计算任务的调度类型为**手动节点**，需要手动触发任务的调度。
7.  在代码编写页面，保存并提交MapReduce任务。

    1.  单击页面右上方的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1197549951/p72337.png)图标，保存代码。

    2.  单击页面右上方的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1197549951/p73470.png)图标，提交代码。

    3.  在**提交备注**页面，填写备注信息。

    4.  单击**确定并提交**。

8.  发布MapReduce任务。

    -   如果您的开发模式是Dev-Prod模式，则需要发布MapReduce任务，详情请参见[管理发布任务](/cn.zh-CN/任务发布/管理发布任务.md)。
    -   如果您的开发模式是Basic模式，则提交成功后的MapReduce任务，即可参与生产环境的调度。


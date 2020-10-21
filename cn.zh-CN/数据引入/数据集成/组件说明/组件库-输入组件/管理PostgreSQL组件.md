---
keyword: [输入组件, PostgreSQL]
---

# 管理PostgreSQL组件

本文为您介绍如何配置、复制、删除PostgreSQL组件及如何选择数据的发送方式。

**PostgreSQL**输入组件适用于从**PostgreSQL**数据库中读取数据至Dataphin平台，进行数据的整合和再加工的场景。

## 配置属性

1.  登录[Dataphin控制台](https://dataphin.console.aliyun.com/workingArea)。

2.  在Dataphin控制台页面，**选择工作区Region**后，单击**进入Dataphin\>\>**。

3.  进入**创建管道开发脚本**页面。

    1.  在Dataphin首页，单击**研发**，进入数据**开发**页面。

    2.  将鼠标悬停在**开发**上，单击**集成**，进入数据**集成**页面。

    3.  将鼠标悬停在![ddd](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2593819951/p80295.png)图标，单击**离线单条管道**。

        ![sss](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/3593819951/p80296.png)

    4.  根据**创建管道开发脚本**页面提示完成参数的配置，单击**确定**。

        ![ddd](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/3593819951/p80303.png)

        |参数|描述|
        |--|--|
        |**管道名称**|填写管道名称。|
        |**调度类型**|选择管道的调度类型。**调度类型**包括：         -   **周期性节点**指需定期执行的任务。
        -   **手动节点**指没有依赖关系，需手动触发的任务。 |
        |**描述**|填写对离线单条管道的简单描述。|
        |**选择目录**|选择离线单条管道所在的文件夹。|

4.  离线单条管道脚本的开发页面，单击页面右上角的**组件库**。

    ![ddd](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/3593819951/p80313.png)

5.  单击**输入**前的![dgd](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/3593819951/p80354.png)图标。

6.  将**PostgreSQL**组件拖到左侧的管道画布中。

7.  将鼠标放置在**PostgreSQL**组件框内右键单击，选择**属性配置**。

8.  根据**PostgreSQL输入配置**页面提示，配置参数。

    ![faga](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/9883819951/p86495.png)

    |参数|说明|
    |--|--|
    |**步骤名称**|根据当前组件的使用场景，填写名称。|
    |**数据源**|选择数据源。选取Dataphin系统中已配置的数据源，且数据源需同时具备以下两个条件：     -   数据源类型为PostgreSQL。
    -   执行**属性配置**的账号具有该数据源的同步读权限，如果没有权限，则需要申请数据源权限，详情请参见[管理数据源权限](/cn.zh-CN/资产中心/安全中心/我的权限/操作数据源权限.md)。
同时您可以单击**数据源**后的![dfag](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2193819951/p80969.png)图标，进入规划模块添加数据源，详情请参见[新建PostgreSQL数据源](/cn.zh-CN/数仓规划/数据源/新建离线数据源/新建PostgreSQL数据源.md)。|
    |**来源表量**|选择来源表量。来源表量包括**单表**和**多表**。 **说明：** **多表**指多张具有相同表结构的表。 |
    |**表**|选择来源表：     -   如果**来源表量**选择了**单表**，则单击![geg](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/0193819951/p80970.png)图标，选择输入的**表**。
    -   如果**来源表**选择了**多表**，则执行以下操作，添加表：
        1.  在输入框中，输入表的表达式。

系统支持枚举形式、类正则形式及两者混合形式，例如`table_[001-100];table_102`。

        2.  单击![gega](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/5983819951/p127162.png)图标。
        3.  在**确认匹配详情**对话框中，选择匹配的表。
        4.  单击**确认**。 |
    |**切分建**|选择**切分建**。您可以将源数据表中某一列作为切分键，建议使用主键或有索引的列作为切分键。|
    |**输入过滤**|填写输入字段的过滤信息，例如`ds=${bizdate}`。**输入过滤**适用于以下两种场景：     -   固定的某一部分数据。
    -   参数过滤。 |
    |**输出字段**|根据左侧页面的输入配置，为您展示输出的字段。您也可以通过如下操作管理字段：     -   单击**操作**列下的![sgaga](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2193819951/p80971.png)图标，删除多余的字段。
    -   单击**字段管理**，在**字段管理**页面中查看该表**未选的输入字段**和**已选的输入字段**：

        -   选择某个字段后，单击![gege](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1293819951/p80980.png)图标，将**未选的输入字段**移入到**已选的输入字段**。
        -   选择某个字段后，单击![sfsga](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1293819951/p80985.png)图标，将**已选的输入字段**移入到**未选的输入字段**。
![geg](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1193819951/p80973.png) |

9.  单击**确认**，完成**PostgreSQL**输入组件的属性配置。


## 复制PostgreSQL

1.  将鼠标放置在**PostgreSQL**组件框内右键单击，单击**复制**。

2.  在管道画布中右键单击后，选择**粘贴**，完成**PostgreSQL**输入组件的复制。


## 删除PostgreSQL

1.  将鼠标放置在**PostgreSQL**组件框内右键单击，单击**删除**。

2.  在确认弹框中单击**确定**，完成**PostgreSQL**输入组件的删除。


## 选择数据的发送方式

当输入组件在连接多个下游组件时，需要选择输入组件的数据发送到下游节点的方式。

1.  将鼠标放置在**PostgreSQL**组件框内右键单击，单击**数据发送方式**。

2.  选择数据发送的方式。

    **数据发送方式**包括：

    -   **复制**：上游节点的数据根据下游节点数量进行等份复制，且每个下游节点的数据都是上游节点的全部数据。
    -   **轮流分发**：上游节点的数据根据下游节点数量进行轮流分发，且所有下游节点的数据之和等于上游节点的数据。


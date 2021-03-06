---
keyword: HDFS数据源
---

# 新建HDFS数据源

本文为您介绍如何新建HDFS类型的数据源。

-   已获取HDFS的**JDBC URL**。
-   已获取HDFS的**DefaultFS**。

1.  登录[Dataphin控制台](https://dataphin.console.aliyun.com/workingArea)。

2.  在Dataphin控制台页面，选择工作区地域后，单击**进入Dataphin\>\>**。

3.  进入数仓**规划**页面。

    -   在Dataphin首页，单击顶部菜单栏的**规划**。
    -   在Dataphin首页，单击顶部菜单栏下方的**智能数仓规划**。
4.  在左侧导航栏中，单击**数据源**。

5.  在**数据源**页面，单击右上方的**新建数据源**。

6.  在**新建数据源**对话框中，填写数据源信息。

    ![fa'gafaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8755209951/p95495.png)

    |参数|描述|
    |--|--|
    |**数据源类型**|选择数据源类型为**HDFS**。|
    |**数据源名称**|填写数据源名称。数据源名称由汉字、数字、字母、下划线（\_）或短划线（-）组合组成。|
    |**数据源描述**|填写对数据源简单的描述。|
    |**数据源配置**|配置数据源：     -   如果开发模式是Basic模式，则选择**生产数据源**。
    -   如果开发模式是Dev-Prod模式，则可以通过以下方式配置数据源：
        -   单击**生产+开发数据源**，配置生产环境和开发环境的数据源。
        -   单击**生产数据源**，配置生产数据源。完成生产数据源的创建后，单击**开发数据源**，配置开发环境的数据源。

![fagaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6278209951/p93912.png)

**说明：** 系统支持配置**生产数据源**和**开发数据源**为相同的数据源，也可以配置为不同的数据源。 |
    |**生产数据源**或**生产+开发数据源**|**DefaultFS**|填写的正确DefaultFS。填写的格式为hdfs://ServerIP:Port。|
    |**Kerberos**|选择**开启**或**关闭**，如果您选择**开启**，则需要配置如下参数：     -   **KDC Server**：KDC（密钥分发中心）统一服务地址，支持配置多个地址，使用英文逗号（,）分割。
    -   **Keytab File**：基于KDC加密方式，生成的解密密钥文件。
    -   **Principal**：基于KDC加密方式，认证的Principal名。 |

7.  单击**测试连接**。

8.  测试成功后，单击**确定**，完成HDFS数据源的创建。



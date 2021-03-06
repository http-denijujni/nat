# 创建DNAT条目

NAT网关支持DNAT功能，将NAT网关上的公网IP映射给ECS实例使用，使ECS实例能够提供互联网服务。DNAT支持端口映射和IP映射。

您已经创建了NAT网关并绑定了弹性公网IP（EIP）。详细信息，请参见[创建NAT网关](/cn.zh-CN/NAT网关实例/创建NAT网关.md)和[绑定EIP](/cn.zh-CN/NAT网关实例/管理EIP/绑定EIP.md)。

**说明：** 如果您在2017年11月3日之前购买过NAT带宽包，请确保NAT带宽包中有可用的公网IP。

如果您的ECS实例已经绑定了EIP，则不支持为该ECS实例添加DNAT条目。

如需为该ECS实例添加DNAT条目，请先将ECS实例与EIP解绑。解绑后，再为该ECS实例添加DNAT条目。详细信息，请参见[解绑EIP](/cn.zh-CN/用户指南/解绑EIP.md)和[创建DNAT条目](/cn.zh-CN/DNAT/创建DNAT条目.md)。

**说明：** 如果存量ECS实例绑定了EIP，且处于NAT网关的DNAT条目中，则ECS实例优先通过绑定的EIP进行公网通信。

1.  登录[NAT网关管理控制台](https://vpc.console.aliyun.com/nat)。

2.  在顶部菜单栏处，选择NAT网关的地域。

3.  在**NAT网关**页面，找到目标NAT网关实例，单击**操作**列下的**设置DNAT**。

4.  在DNAT条目列表区域，单击**创建DNAT条目**。

5.  在创建DNAT条目对话框，根据以下信息配置DNAT条目，然后单击**确定**。

    |配置|说明|
    |:-|:-|
    |**公网IP地址**|选择要提供互联网通信的公网IP。 **说明：**

    -   普通型NAT网关不支持将一个公网IP同时用于DNAT条目和SNAT条目。
    -   增强型NAT网关白名单支持将一个公网IP同时用于DNAT条目和SNAT条目。如需使用，请[提交工单](https://selfservice.console.aliyun.com/ticket/category/natgw/today)。 |
    |**私网IP地址**|选择要通过DNAT规则进行公网通信的ECS实例。您可以通过以下两种方式指定目标ECS实例的私网IP：     -   **从ECS或弹性网卡对应IP进行选择**：从ECS实例或弹性网卡列表中选择ECS实例。
    -   **自填**：输入目标ECS实例的私网IP。

**说明：** 自填的私网IP必须属于本VPC的CIDR范围，也可直接输入一个已有的ECS实例的私网IP。 |
    |**端口设置**|选择DNAT映射的方式：     -   **所有端口**：该方式属于IP映射，任何访问该公网IP的请求都将转发到目标ECS实例上。
    -   **具体端口**：该方式属于端口映射，NAT网关会将以指定协议和端口访问该公网IP的请求转发到目标ECS实例的指定端口上。

选择具体端口后，请根据业务需求设置以下参数：

        -   **公网端口**：进行端口转发的外部端口。
        -   **私网端口**：进行端口转发的内部端口。
        -   **协议类型**：转发端口的协议类型。 |
    |**条目名称**|输入DNAT条目的名称。 名称长度为2~128个字符，以大小写字母或中文开头， 可包含数字、下划线（\_）和短横线（-）。 |


**相关文档**  


[CreateForwardEntry](/cn.zh-CN/API参考/NAT网关/CreateForwardEntry.md)


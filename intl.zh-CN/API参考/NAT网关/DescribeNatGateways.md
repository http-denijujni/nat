# DescribeNatGateways

调用DescribeNatGateways查询已创建的NAT网关。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=DescribeNatGateways&type=RPC&version=2016-04-28)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeNatGateways|要执行的操作，取值：**DescribeNatGateways**。 |
|RegionId|String|是|cn-hangzhou|NAT网关所在的地域，您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。 |
|NatGatewayId|String|否|ngw-bp1uewa15k4iy5770\*\*\*\*|要查询的NAT网关的ID。 |
|VpcId|String|否|vpc-bp15zckdt37pq72z\*\*\*\*|NAT网关所属的VPC的ID。 |
|Name|String|否|test|要查询的NAT网关的名称。 |
|InstanceChargeType|String|否|PostPaid|NAT网关实例的付费模式，取值：

 -   **PostPaid**：按量付费。
-   **PrePaid**：包年包月。

 **说明：** 国际站仅支持**PostPaid**（按量付费）。 |
|Spec|String|否|Large|NAT网关的规格，取值：

 -   **Small**（默认值）：小型。
-   **Middle**：中型。
-   **Large**：大型。
-   **XLarge.1**：超大型-1。 |
|NatType|String|否|Normal|NAT网关的类型，取值：

 -   **Normal**：普通型。
-   **Enhanced**：增强型。 |
|ResourceGroupId|String|否|rg-bp67acfmxazb4ph\*\*\*\*|NAT网关所属的资源组ID。 |
|PageNumber|Integer|否|10|列表的页码，默认值为**1**。 |
|PageSize|Integer|否|1|分页查询时每页的行数，最大值为**50**，默认值为**10**。 |
|DryRun|Boolean|否|true|是否只预检此次请求，取值：

 **true**：发送检查请求，不会查询资源状况。检查项包括AccessKey是否有效、RAM用户的授权情况和是否填写了必需参数。如果检查不通过，则返回对应错误。如果检查通过，会返回错误码`DryRunOperation`。

 **false**（默认值）：发送正常请求，通过检查后返回2XX HTTP状态码并直接查询资源状况。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|NatGateways|Array of NatGateway| |NAT网关的详细信息。 |
|NatGateway| | | |
|BusinessStatus|String|Normal|NAT网关的业务状态。

 -   **Normal**：正常。
-   **FinancialLocked**：欠费锁定状态。 |
|CreationTime|String|2017-06-08T12:20:55|创建时间。按照ISO8601标准表示，并需要使用UTC时间。格式为：YYYY-MM-DDThh:mmZ。 |
|DeletionProtection|Boolean|true|是否开启了删除保护功能。

 -   **true**：已开启。
-   **false**：未开启。 |
|Description|String|NAT|NAT网关的描述。 |
|EcsMetricEnabled|Boolean|true|是否开启了网关流量监控功能。

 -   **true**：开启了网关流量监控功能。
-   **false**：未开启网关流量监控功能。 |
|ExpiredTime|String|2017-08-26T16:00Z|NAT网关的过期时间。 |
|ForwardTableIds|List|ftb-uf6gj3mhsg94qsqst\*\*\*\*|DNAT表ID。 |
|InstanceChargeType|String|PostPaid|NAT网关实例的付费模式。

 -   **PostPaid**：按量付费。
-   **PrePaid**：包年包月。

 **说明：** 国际站仅支持**PostPaid**（按量付费）。 |
|InternetChargeType|String|PayBySpec|NAT网关的计费类型。

 -   **PayBySpec**：按固定规格计费。
-   **PayByLcu**：按使用量计费。 |
|IpLists|Array of IpList| |NAT网关绑定的弹性公网IP。 |
|IpList| | | |
|IpAddress|String|116.62.222.xx|弹性公网IP的地址。 |
|SnatEntryEnabled|Boolean|false|已经用于DNAT条目的IP，是否还可用于SNAT条目。

 -   **true**：还可用于SNAT条目。
-   **false**：不可用于SNAT条目。 |
|Name|String|abc|NAT网关实例名称。 |
|NatGatewayId|String|ngw-bp1047e2d4z7kf2ki\*\*\*\*|NAT网关的ID。 |
|NatGatewayPrivateInfo|Struct| |增强型NAT网关的私网信息。

 **说明：** **NatType**取值为**Normal**时，该列表中返回的参数均为空值。 |
|EniInstanceId|String|10|弹性网卡实例ID。 |
|IzNo|String|cn-hangzhou-b|NAT网关所属的可用区。 |
|MaxBandwidth|Integer|5120|最大带宽值，单位为Mbps。 |
|PrivateIpAddress|String|192.168.1.xx|私网IP地址。 |
|VswitchId|String|vsw-bp1s2laxhdf9ayjbo\*\*\*\*|NAT网关所属的交换机ID。 |
|NatType|String|Normal|NAT网关的类型。

 -   **Normal**：普通型NAT网关。
-   **Enhanced**：增强型NAT网关。 |
|RegionId|String|cn-hangzhou|NAT网关的所在地域ID。 |
|ResourceGroupId|String|rg-bp67acfmxazb4ph\*\*\*\*|资源组ID。 |
|SnatTableIds|List|stb-uf6dalcdu0krz423p\*\*\*\*|NAT网关的SNAT表ID。 |
|Spec|String|Small|NAT网关的规格。

 -   **Small**：小型。
-   **Middle**：中型。
-   **Large**：大型。
-   **XLarge.1**：超大型-1。 |
|Status|String|Initiating|NAT网关的状态。

 **Creating**：创建NAT网关是异步操作，在创建完成之前是Creating状态。

 **Available**：NAT网关创建完成后的状态，是稳定状态。

 **Modifying**：变配NAT网关是异步操作，在变配的过程中是Modifying状态。

 **Deleting**：删除NAT网关是异步操作，在删除的过程中是Deleting状态。

 **Converting**：普通型NAT网关转换到增强型NAT网关是异步操作，在转换过程中是Converting状态。 |
|VpcId|String|vpc-bp15zckdt37pq72z\*\*\*\*|NAT网关所属的VPC的ID。 |
|PageNumber|Integer|10|当前页码。 |
|PageSize|Integer|10|每页包含的条目数。 |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|请求ID。 |
|TotalCount|Integer|10|列表条目数。 |

## 示例

请求示例

```
http(s)://vpc.aliyuncs.com/?Action=DescribeNatGateways
&RegionId=cn-hangzhou
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeNatGatewaysResponse>
    <PageNumber>1</PageNumber>
    <TotalCount>1</TotalCount>
    <PageSize>10</PageSize>
    <RequestId>1207C80C-7CAB-4874-A9A0-D19EC9F35490</RequestId>
    <NatGateways>
            <NatGateway>
                    <Description></Description>
                    <Spec>Small</Spec>
                    <IpLists>
                            <IpList>
                                    <IpAddress>118.xx.xx.181</IpAddress>
                                    <AllocationId>eip-bp1xyg5ipmh3nledx****</AllocationId>
                                    <UsingStatus>UsedBySnatTable</UsingStatus>
                            </IpList>
                            <IpList>
                                    <IpAddress>47.xx.xx.34</IpAddress>
                                    <AllocationId>eip-bp19eue77u20cffjc****</AllocationId>
                                    <UsingStatus>UsedByForwardTable</UsingStatus>
                            </IpList>
                    </IpLists>
                    <ForwardTableIds>
                            <ForwardTableId>ftb-bp15o9aylj19vfvgt****</ForwardTableId>
                    </ForwardTableIds>
                    <VpcId>vpc-bp15k6sx6fhdz2jw4****</VpcId>
                    <NatGatewayId>ngw-bp1047e2d4z7kf2ki****</NatGatewayId>
                    <CreationTime>2018-01-10T09:48:29Z</CreationTime>
                    <Name></Name>
                    <Status>Available</Status>
                    <BusinessStatus>Normal</BusinessStatus>
                    <RegionId>cn-hangzhou</RegionId>
                    <SnatTableIds>
                            <SnatTableId>stb-bp1tyr0o48w6wymur****</SnatTableId>
                    </SnatTableIds>
                    <InstanceChargeType>PostPaid</InstanceChargeType>
            </NatGateway>
    </NatGateways>
</DescribeNatGatewaysResponse>
```

`JSON` 格式

```
{
    "PageNumber": 1, 
    "TotalCount": 1, 
    "PageSize": 10, 
    "RequestId": "1207C80C-7CAB-4874-A9A0-D19EC9F35490", 
    "NatGateways": {
        "NatGateway": [ 
            {
                "Description": "", 
                "Spec": "Small", 
                "IpLists": {
                    "IpList": [
                        {
                            "IpAddress": "118.xx.xx.181", 
                            "AllocationId": "eip-bp1xyg5ipmh3nledx****", 
                            "UsingStatus": "UsedBySnatTable"
                        }, 
                        {
                            "IpAddress": "47.xx.xx.34", 
                            "AllocationId": "eip-bp19eue77u20cffjc****", 
                            "UsingStatus": "UsedByForwardTable"
                        }
                    ]
                }, 
                "ForwardTableIds": {
                    "ForwardTableId": [
                        "ftb-bp15o9aylj19vfvgt****"
                    ]
                }, 
                "VpcId": "vpc-bp15k6sx6fhdz2jw4****", 
                "NatGatewayId": "ngw-bp1047e2d4z7kf2ki****", 
                "CreationTime": "2018-01-10T09:48:29Z", 
                "Name": "", 
                "Status": "Available", 
                "BusinessStatus": "Normal", 
                "RegionId": "cn-hangzhou", 
                "SnatTableIds": {
                    "SnatTableId": [
                        "stb-bp1tyr0o48w6wymur****"
                    ]
                }, 
                "InstanceChargeType": "PostPaid"
            }
        ]
    }
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|404|InvalidRegionId.NotFound|The specified RegionId does not exist in our records.|指定的 RegionId 不存在，请您检查此产品在该地域是否可用。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Vpc)查看更多错误码。


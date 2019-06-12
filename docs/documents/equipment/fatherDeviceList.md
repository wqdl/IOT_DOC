# fatherDeviceList

父设备列表(添加子设备时使用)

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述     |
| ------------ | ------ | -------- | -------- |
| ACCESS_TOKEN | string | 是       | 身份验证 |
| ppid         | int    | 是       | 产品id   |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 消息体，详情见表body                                       |

*表 body*

| 名称 | 类型 | 描述                           |
| ---- | ---- | ------------------------------ |
| list | list | 产品列表信息，详情参见下表List |

*表  List*

| 名称        | 类型   | 描述                         |
| ----------- | ------ | ---------------------------- |
| nodetype    | int    | 节点类型(1设备2网关）        |
| depid       | int    | 所属企业id                   |
| productname | string | 产品名称                     |
| sonnum      | int    | 子设备数量                   |
| devicename  | string | 设备名称                     |
| pdid        | int    | 设备id                       |
| ppid        | int    | 产品id                       |
| status      | int    | 设备状态(1在线2离线3未激活） |
| deptname    | string | 所属企业名称                 |

## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/DeviceController/fatherDeviceList
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&ppid=3
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {
        "list": [
            {
                "nodetype": 1,
                "deptid": 12520,
                "productname": "测试模拟程序专用不要删除",
                "sonnum": 0,
                "devicename": "222222222222222",
                "pdid": 41,
                "ppid": 3,
                "status": 3,
                "deptname": "浙江德世电器有限公司"
            },
            {
                "nodetype": 1,
                "deptid": 12520,
                "productname": "测试模拟程序专用不要删除",
                "sonnum": 0,
                "devicename": "fffffffffff",
                "pdid": 42,
                "ppid": 3,
                "status": 3,
                "deptname": "浙江德世电器有限公司"
            },
            {
                "nodetype": 1,
                "deptid": 12520,
                "productname": "测试模拟程序专用不要删除",
                "sonnum": 0,
                "devicename": "ffffffffffffff",
                "pdid": 43,
                "ppid": 3,
                "status": 3,
                "deptname": "浙江德世电器有限公司"
            },
            {
                "nodetype": 1,
                "deptid": 12862,
                "productname": "测试模拟程序专用不要删除",
                "sonnum": 0,
                "devicename": "3333333",
                "pdid": 47,
                "ppid": 3,
                "status": 3,
                "deptname": "永康市动力网络科技有限公司"
            },
            {
                "nodetype": 1,
                "deptid": 12863,
                "productname": "测试模拟程序专用不要删除",
                "sonnum": 0,
                "devicename": "ha好123____",
                "pdid": 48,
                "ppid": 3,
                "status": 3,
                "deptname": "浙江三锋实业股份有限公司"
            },
            {
                "nodetype": 1,
                "deptid": 12864,
                "productname": "测试模拟程序专用不要删除",
                "sonnum": 0,
                "devicename": "d874d889fb654764a0d96b1387dcc00a",
                "pdid": 52,
                "ppid": 3,
                "status": 3,
                "deptname": "永康市开源动力工具有限公司"
            }
        ]
    }
}
```


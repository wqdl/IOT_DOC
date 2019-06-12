# sonDeviceList

子设备列表

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述               |
| ------------ | ------ | -------- | ------------------ |
| ACCESS_TOKEN | string | 是       | 身份验证           |
| text         | string | 否       | 搜索名称           |
| pdid         | int    | 是       | 父设备id           |
| pageNum      | int    | 否       | 返回结果中的第几页 |
| pageSize     | int    | 否       | 每页显示的数量     |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 消息体，详情见表body                                       |

*表 body*

| 名称 | 类型 | 描述                           |
| ---- | ---- | ------------------------------ |
| pdid | int  | 所属产品id                     |
| list | list | 产品列表信息，详情参见下表List |

*表 List*

| 名称     | 类型   | 描述               |
| -------- | ------ | ------------------ |
| pageNum  | int    | 返回结果中的第几页 |
| pageSize | int    | 每页显示的数量     |
| startRow | int    | 开始位置行数       |
| endRow   | int    | 结束位置行数       |
| total    | string | 设备总数           |
| pages    | int    | 总页数             |
| result   | list   | 详情请见下表result |

*表 ProductList*

| 名称        | 类型   | 描述                         |
| ----------- | ------ | ---------------------------- |
| nodetype    | int    | 节点类型(1设备2网关）        |
| productname | string | 产品名称                     |
| sonnum      | int    | 子设备数量                   |
| devicename  | string | 设备名称                     |
| pdid        | int    | 设备id                       |
| status      | int    | 设备状态(1在线2离线3未激活） |

## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/DeviceController/sonDeviceList
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&pdid=79
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {
        "pdid": 79,
        "list": {
            "pageNum": 1,
            "pageSize": 10,
            "startRow": 0,
            "endRow": 10,
            "total": 1,
            "pages": 1,
            "result": [
                {
                    "nodetype": 1,
                    "productname": "newproduct",
                    "sonnum": 0,
                    "devicename": "qwer2",
                    "pdid": 81,
                    "status": 3
                }
            ]
        }
    }
}
```


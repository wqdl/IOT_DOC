# deviceList

设备列表

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述               |
| ------------ | ------ | -------- | ------------------ |
| ACCESS_TOKEN | string | 是       | 身份验证           |
| text         | string | 否       | 搜索名称           |
| pageNum      | int    | 否       | 返回结果中的第几页 |
| pageSize     | int    | 否       | 每页显示的数量     |
| ppid         | int    | 否       | 所属产品id         |
| depid        | int    | 否       | 所属平台id         |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 调用成功时返回的产品信息。详情参见下表body                 |

*表 body*

| 名称      | 类型   | 描述                           |
| --------- | ------ | ------------------------------ |
| text      | string | 传入的搜索名称                 |
| allNum    | int    | 设备总数                       |
| activeNum | int    | 激活设备数                     |
| onlineNum | int    | 当前在线数                     |
| list      | list   | 产品列表信息，详情参见下表List |

*表 List*

| 名称     | 类型 | 描述                    |
| -------- | ---- | ----------------------- |
| pageNum  | int  | 返回结果中的第几页      |
| pageSize | int  | 每页显示的数量          |
| startRow | int  | 开始位置行数            |
| endRow   | int  | 结束位置行数            |
| total    | int  | 设备总数                |
| pages    | int  | 总页数                  |
| result   | list | 详情请见下表ProductList |

*表 ProductList*

| 名称        | 类型   | 描述                 |
| ----------- | ------ | -------------------- |
| devicename  | int    | 设备数量             |
| productname | string | 产品名称             |
| nodetype    | int    | 设备类型(1设备2网关) |
| deptid      | int    | 所属运营商的id       |
| pdid        | int    | 设备id               |
| ppid        | int    | 产品id               |
| deptname    | string | 所属运营商的名字     |
| status      | int    | 1在线2离线3未激活    |
| sonnum      | int    | 子设备数             |

## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/DeviceController/deviceList
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&text=测试
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {
        "activeNum": 0,
        "text": "测试",
        "onlineNum": 0,
        "list": {
            "pageNum": 1,
            "pageSize": 10,
            "startRow": 0,
            "endRow": 10,
            "total": 2,
            "pages": 1,
            "result": [
                {
                    "nodetype": 1,
                    "deptid": 12862,
                    "productname": "123123",
                    "sonnum": 0,
                    "devicename": "测试fergruoh",
                    "pdid": 60,
                    "ppid": 4,
                    "status": 3,
                    "deptname": "永康市动力网络科技有限公司"
                },
                {
                    "nodetype": 1,
                    "deptid": 12862,
                    "productname": "123123",
                    "sonnum": 0,
                    "devicename": "测试fergruoh",
                    "pdid": 61,
                    "ppid": 4,
                    "status": 3,
                    "deptname": "永康市动力网络科技有限公司"
                }
            ]
        },
        "allNum": 2
    }
}
```
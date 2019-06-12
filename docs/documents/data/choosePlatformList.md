# choosePlatformList

选择物联网平台列表(在添加添加设备时)

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述     |
| ------------ | ------ | -------- | -------- |
| ACCESS_TOKEN | string | 是       | 身份验证 |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 返回数据。详情见下表body                                   |

表body

| 名称 | 类型 | 描述           |
| ---- | ---- | -------------- |
| list | list | 详情见下表list |

表list

| 名称     | 类型   | 描述         |
| -------- | ------ | ------------ |
| depitid  | int    | 运营商deptid |
| poid     | int    | 运营商id     |
| deptname | string | 运营商名称   |



## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/IotController/choosePlatformList
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {
        "list": [
            {
                "deptid": 12589,
                "poid": 69,
                "deptname": "缙云县工业互联网平台"
            },
            {
                "deptid": 12942,
                "poid": 91,
                "deptname": "运营商测试第一天"
            },
            {
                "deptid": 12519,
                "poid": 54,
                "deptname": "YK"
            },
            {
                "deptid": 11865,
                "poid": 49,
                "deptname": "TestOrg"
            },
            {
                "deptid": 12974,
                "poid": 101,
                "deptname": "上海黄埔运营商第二个"
            }
        ]
    }
}
```


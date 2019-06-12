# showHistory

查看历史数据

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述                                             |
| ------------ | ------ | -------- | ------------------------------------------------ |
| ACCESS_TOKEN | string | 是       | 身份验证                                         |
| pdid         | int    | 是       | 设备id                                           |
| pfpid        | int    | 是       | 参数id                                           |
| type         | int    | 否       | 类别（1:1小时,2:24小时,3:7天,4:自定义,null全部） |
| minTime      | string | 否       | type为4时使用,最小时间                           |
| maxTime      | string | 否       | type为4时使用,最大时间                           |

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

*表 List*

| 名称  | 类型   | 描述   |
| ----- | ------ | ------ |
| time  | date   | 时间   |
| value | string | 对应值 |

## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/DeviceController/showHistory
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&pdid=64
&pfpid=71
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {
        "list": [
            {
                "time": "May 14, 2019 11:41:37 PM",
                "value": "12"
            },
            {
                "time": "May 14, 2019 11:41:41 PM",
                "value": "12"
            },
            {
                "time": "May 14, 2019 11:43:04 PM",
                "value": "13"
            },
            {
                "time": "May 14, 2019 11:43:05 PM",
                "value": "13"
            },
            {
                "time": "May 14, 2019 11:45:30 PM",
                "value": "14"
            },
            {
                "time": "May 14, 2019 11:45:30 PM",
                "value": "14"
            },
            {
                "time": "May 14, 2019 11:45:33 PM",
                "value": "15"
            },
            {
                "time": "May 14, 2019 11:45:34 PM",
                "value": "15"
            },
            {
                "time": "May 15, 2019 9:39:35 AM",
                "value": "1"
            },
            {
                "time": "May 15, 2019 9:39:35 AM",
                "value": "1"
            }
        ]
    }
}
```


# batchInfo

批次详情

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述                       |
| ------------ | ------ | -------- | -------------------------- |
| ACCESS_TOKEN | string | 是       | 身份验证                   |
| pageNum      | int    | 否       | 返回结果中的第几页         |
| pageSize     | int    | 否       | 每页显示的数量             |
| pdbid        | int    | 是       | 批次id                     |
| type         | int    | 否       | 设备id（1已激活，2未激活） |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 调用成功时返回的产品信息。详情参见下表body                 |

*表 body*

| 名称         | 类型 | 描述                           |
| ------------ | ---- | ------------------------------ |
| pdbid        | int  | 批次id                         |
| allNum       | int  | 设备总数                       |
| activeNum    | int  | 激活设备数                     |
| notActiveNum | int  | 未激活设备数                   |
| createTime   | date | 添加时间                       |
| list         | list | 产品列表信息，详情参见下表List |

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

*表 result*

| 名称       | 类型   | 描述                          |
| ---------- | ------ | ----------------------------- |
| devicename | string | 设备名称                      |
| pdid       | int    | 设备id                        |
| secret     | string | 产品secret                    |
| productkey | string | 产品key                       |
| status     | int    | 设备状态（1在线2离线3未激活） |

## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/DeviceController/batchInfo
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&pdbid=1
&type=2
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {
        "pdbid": 1,
        "activeNum": 0,
        "createTime": "Apr 28, 2019 12:00:00 AM",
        "notActiveNum": 6,
        "list": {
            "pageNum": 1,
            "pageSize": 10,
            "startRow": 0,
            "endRow": 10,
            "total": 6,
            "pages": 1,
            "result": [
                {
                    "devicename": "222222222222222",
                    "pdid": 41,
                    "secret": "fbe8a49ff82f46d199239f26627cbbdb",
                    "productKey": "waneqi234key",
                    "status": 3
                },
                {
                    "devicename": "fffffffffff",
                    "pdid": 42,
                    "secret": "3017deaa15bd4aaa93a90d0a2807cb14",
                    "productKey": "waneqi234key",
                    "status": 3
                },
                {
                    "devicename": "ffffffffffffff",
                    "pdid": 43,
                    "secret": "f9c421453f35436e8b825aa113e0a947",
                    "productKey": "waneqi234key",
                    "status": 3
                },
                {
                    "devicename": "3333333",
                    "pdid": 47,
                    "secret": "ea2c3aaa1afb42f6a2b5576d5eb03a75",
                    "productKey": "waneqi234key",
                    "status": 3
                },
                {
                    "devicename": "ha好123____",
                    "pdid": 48,
                    "secret": "ee16cd1867bd408b8db04ce2d0b326aa",
                    "productKey": "waneqi234key",
                    "status": 3
                },
                {
                    "devicename": "d874d889fb654764a0d96b1387dcc00a",
                    "pdid": 52,
                    "secret": "31fcbcd25cd543fc9c55c049f512af47",
                    "productKey": "waneqi234key",
                    "status": 3
                }
            ]
        },
        "allNum": 6
    }
}
```


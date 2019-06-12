# deviceInfo

设备详情

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述     |
| ------------ | ------ | -------- | -------- |
| ACCESS_TOKEN | string | 是       | 身份验证 |
| pdid         | int    | 是       | 设备id   |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 调用成功时返回的产品信息。详情参见下表body                 |

*表 body*

| 名称 | 类型 | 描述                    |
| ---- | ---- | ----------------------- |
| pdid | int  | 设备id                  |
| map  | map  | 设备详情，详情见下表map |



*表 map*

| 名称        | 类型   | 描述                        |
| ----------- | ------ | --------------------------- |
| createtime  | date   | 添加时间                    |
| nodetype    | int    | 设备类型(1设备2网关)        |
| productname | string | 产品名称                    |
| devicename  | string | 设备名称                    |
| pdid        | int    | 设备id                      |
| secret      | string | 产品secret                  |
| productkey  | string | 产品key                     |
| ppid        | int    | 产品id                      |
| status      | int    | 当前状态(1在线2离线3未激活) |

## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/DeviceController/deviceInfo
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&pdid=75
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {
        "pdid": 75,
        "map": {
            "createtime": "May 29, 2019",
            "nodetype": 1,
            "productname": "产品一号_1",
            "devicename": "qwer4",
            "pdid": 75,
            "secret": "9bc11f52ef404d70a594da760d0fe956",
            "productkey": "0eac912f-ceff-4e9c-af37-575631382eef产品一号key",
            "ppid": 6,
            "status": 3
        }
    }
}
```


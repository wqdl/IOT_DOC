# parameterInfo

获取参数详情，根据function_parameter_id

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述                       |
| ------------ | ------ | -------- | -------------------------- |
| ACCESS_TOKEN | string | 是       | 身份验证                   |
| pfpid        | int    | 是       | 属性、事件、服务的参数的id |

## 返回参数

| 名称    | 类型   | 描述                                                         |
| ------- | ------ | ------------------------------------------------------------ |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成   |
| msg     | string | 调用接口时返回的信息。                                       |
| body    | body   | 调用成功时返回的属性、事件、服务的参数信息。详情参见下表body |

*表 body*

| 名称 | 类型 | 描述                                            |
| ---- | ---- | ----------------------------------------------- |
| map  | map  | 属性、事件、服务信息的参数详情，详情参见下表Map |

*表 Map*

| 名称       | 类型   | 描述                                                         |
| ---------- | ------ | ------------------------------------------------------------ |
| dataformat | int    | 数据类型（1.int32 (整数型),2.float (单精度浮点型),3.double (双精度浮点型),4.enum (枚举型),5.bool (布尔型),6.text (字符串),7.date (时间型),8.struct (结构体),9.array (数组)） |
| unit       | i      | 单位id                                                       |
| min        | int    | 取值范围的最小值                                             |
| max        | int    | 取值范围的最大值                                             |
| pfid       | int    | 属性、事件、服务id                                           |
| unitname   | string | 单位的值                                                     |
| step       | int    | 步长（分辨率）                                               |
| tag        | string | 参数标识符                                                   |
| type       | int    | 1入参2反参                                                   |
| pfpid      | int    | 属性、事件、服务的参数id                                     |



## 示例

### 请求示例

```java
http://127.0.0.1:7777/iext/back/openv1/ProductController/parameterInfo
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&pfpid=67
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {
        "map": {
            "dataformat": 1,
            "unit": 1,
            "min": 60,
            "max": 100,
            "pfid": 106,
            "unitname": "无 /",
            "name": "当前温度",
            "step": 1,
            "tag": "temp",
            "type": 2,
            "pfpid": 67
        }
    }
}
```


# productInfo

获取产品详情

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述         |
| ------------ | ------ | -------- | ------------ |
| ACCESS_TOKEN | string | 是       | 身份验证     |
| ppid         | int    | 是       | 所属运营商id |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 调用成功时返回的产品列表信息。详情参见下表body             |

*表 body*

| 名称 | 类型 | 描述                          |
| ---- | ---- | ----------------------------- |
| ppid | int  | 传入的产品id                  |
| map  | map  | 产品信息详情，详情参见下表Map |

*表 Map*

| 名称       | 类型   | 描述                                               |
| ---------- | ------ | -------------------------------------------------- |
| devicenum  | int    | 设备数量                                           |
| protocol   | int    | 接入协议（1.wifi联网,2.以太网,3.蜂窝（2G/3G/4G）） |
| dataformat | int    | 数据格式(1 JSON)                                   |
| createtime | date   | 创建时间                                           |
| sercet     | int    | 所属运营商id                                       |
| nodetype   | string | 节点类型(1设备2网关)                               |
| isjoin     | int    | 是否接入网关(1接入2不接入)                         |
| name       | string | 产品名称                                           |
| productKey | string | 产品key                                            |
| describes  | string | 产品描述                                           |
| ppid       | int    | 产品id                                             |

## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/ProductController/productInfo
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&ppid=39
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {
        "map": {
            "devicenum": 1,
            "protocol": 1,
            "dataformat": 1,
            "createtime": "May 13, 2019",
            "sercet": "0371fa0cbce041ce98355894686a9788",
            "nodetype": 1,
            "isjoin": 1,
            "name": "秦牌灯泡",
            "productKey": "fc79df0e824047c798c79da14bdfd0a7",
            "describes": "秦牌灯泡",
            "ppid": 39
        },
        "ppid": 39
    }
}
```


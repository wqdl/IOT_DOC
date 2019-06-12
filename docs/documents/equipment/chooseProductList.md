# chooseProductList

选择产品列表

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述         |
| ------------ | ------ | -------- | ------------ |
| ACCESS_TOKEN | string | 是       | 身份验证     |
| text         | string | 否       | 搜索产品名称 |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 调用成功时返回的产品信息。详情参见下表body                 |

*表 body*

| 名称 | 类型   | 描述                                  |
| ---- | ------ | ------------------------------------- |
| text | string | 传入的搜索产品名称                    |
| list | list   | 产品列表信息，详情参见下表ProductList |

*表 ProductList*

| 名称       | 类型   | 描述                 |
| ---------- | ------ | -------------------- |
| devicename | int    | 设备数量             |
| createtime | date   | 添加时间             |
| nodetype   | int    | 设备类型(1设备2网关) |
| deptid     | int    | 所属运营商的id       |
| productkey | string | 产品Key              |
| ppid       | int    | 产品id               |
| deptname   | string | 所属运营商的名字     |

## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/DeviceController/chooseProductList
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&text=测试
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {
        "text": "测试",
        "list": [
            {
                "devicenum": 6,
                "createtime": "Apr 19, 2019",
                "nodetype": 1,
                "name": "测试模拟程序专用不要删除",
                "deptid": 12519,
                "productkey": "waneqi234key",
                "ppid": 3,
                "deptname": "永康工业大数据平台"
            },
           	.......
        ]
    }
}
```


# chooseProductList

产品列表（在添加添加设备时)

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述         |
| ------------ | ------ | -------- | ------------ |
| ACCESS_TOKEN | string | 是       | 身份验证     |
| deptid       | int    | 是       | 运营商deptid |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 返回数据。详情见下表body                                   |

表body

| 名称        | 类型 | 描述                  |
| ----------- | ---- | --------------------- |
| productList | list | 详情见下表productList |

表productList

| 名称 | 类型   | 描述     |
| ---- | ------ | -------- |
| name | string | 产品名称 |
| ppid | int    | 产品id   |



## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/IotController/chooseProductList
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&deptid=12519
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {
        "productList": [
            {
                "name": "测试模拟程序专用不要删除",
                "ppid": 3
            },
            {
                "name": "123123",
                "ppid": 4
            },
            {
                "name": "33333",
                "ppid": 18
            },
            {
                "name": "333333333333333",
                "ppid": 19
            },
            {
                "name": "测试key",
                "ppid": 21
            },
            {
                "name": "测试啦啦",
                "ppid": 22
            },
            {
                "name": "fdsgfdg",
                "ppid": 24
            }
        ]
    }
}
```


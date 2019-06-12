# deleteProduct

删除产品

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述         |
| ------------ | ------ | -------- | ------------ |
| ACCESS_TOKEN | string | 是       | 身份验证     |
| ppid         | int    | 是       | 产品id       |
| type         | int    | 是       | 1运营商2企业 |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 返回数据。                                                 |



## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/IotController/deviceList
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&ppid=49
&type=1
```

### 返回示例

```json
 {
    "success": 1,
    "msg": "操作成功！",
    "body": {}
}
```


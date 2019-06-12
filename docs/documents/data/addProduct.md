# addProduct

添加产品

## 请求方式

post 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述                                           |
| ------------ | ------ | -------- | ---------------------------------------------- |
| ACCESS_TOKEN | string | 是       | 身份验证                                       |
| deptid       | int    | 是       | 运营商deptid                                   |
| name         | string | 是       | 产品名称                                       |
| nodetype     | int    | 是       | 节点类型(1设备2网关)                           |
| isjoin       | int    | 是       | 是否接入网关(1接入2不接入)                     |
| protocol     | int    | 是       | 网关协议(1MQTT默认1)                           |
| dataformat   | int    | 是       | 数据格式(1JSON默认1)                           |
| connectway   | int    | 否       | 联网方式1.wifi联网,2.以太网,3.蜂窝（2G/3G/4G） |
| describe     | string | 是       | 描述                                           |

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
&name=test
&nodetype=1
&isjion=1
&protocol=1
&dataformat=1
&describe=测试
&deptid=12589
&connectway
```

### 返回示例

```json

 {
    "success": 1,
    "msg": "操作成功！",
    "body": {}
}
```


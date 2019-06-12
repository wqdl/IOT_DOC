# publishMsg

发布消息

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述            |
| ------------ | ------ | -------- | --------------- |
| ACCESS_TOKEN | string | 是       | 身份验证        |
| ptid         | int    | 是       | topic的id       |
| url          | string | 是       | topic的url      |
| content      | string | 是       | 消息内容        |
| type         | int    | 是       | Qos(1读写2只读) |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 消息体                                                     |

## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/DeviceController/publishMsg
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&ptid=70
&url=/fc79df0e824047c798c79da14bdfd0a7/客厅灯泡/property/set
&content={"properties":{"switch":"1"},"topicType":"set"}
&type=1
```

### 返回示例

```json
{"success":1,"msg":"操作成功！","body":{}}
```


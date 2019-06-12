# setExpect

设置期望值

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述     |
| ------------ | ------ | -------- | -------- |
| ACCESS_TOKEN | string | 是       | 身份验证 |
| pdid         | int    | 是       | 设备id   |
| pfpid        | int    | 是       | 参数id   |
| value        | string | 是       | 期望值   |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 消息体，详情见表body                                       |

## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/DeviceController/setExpect
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&pdid=79
&pfpid=32
&value=69
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {}
}
```


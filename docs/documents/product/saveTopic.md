# saveTopic

保存/修改 topic

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述                     |
| ------------ | ------ | -------- | ------------------------ |
| ACCESS_TOKEN | string | 是       | 身份验证                 |
| ptid         | int    | 否       | topic_id                 |
| ppid         | int    | 是       | 产品id                   |
| permission   | int    | 是       | 设备操作权限(1发布2订阅) |
| url          | string | 是       | 定义的 topic_url         |
| describe     | string | 否       | 描述                     |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |

## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/ProductController/saveTopic
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&ptid=100
&ppid=39
&permission=1
&url=topic_url
&describe=topic_用途
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {}
}
```


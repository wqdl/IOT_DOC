# topicInfo

获取 topic 详情

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述          |
| ------------ | ------ | -------- | ------------- |
| ACCESS_TOKEN | string | 是       | 身份验证      |
| ptid         | int    | 是       | 产品 topic_id |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 调用成功时返回的产品 topic 信息。详情参见下表body          |

*表 body*

| 名称 | 类型 | 描述                            |
| ---- | ---- | ------------------------------- |
| map  | map  | topic 信息详情，详情参见下表Map |

*表 Map*

| 名称       | 类型   | 描述                     |
| ---------- | ------ | ------------------------ |
| topicLei   | string | topic_url 前缀           |
| createtime | date   | 创建时间                 |
| permission | int    | 设备操作权限(1发布2订阅) |
| ptid       | int    | topic_id                 |
| url        | string | topic_url 后缀           |
| describes  | string | 产品描述                 |
| ppid       | string | 产品id                   |

## 示例

### 请求示例

```java
http://127.0.0.1:7777/iext/back/openv1/ProductController/topicInfo
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&ptid=114
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {
        "map": {
            "topicLei": "/884497a549aa4614a08ec8c3a7cb2c15/${deviceName}/user/",
            "createtime": "五月 30, 2019",
            "permission": 1,
            "ptid": 114,
            "url": "post",
            "describes": "设备属性上报",
            "ppid": 48
        }
    }
}
```


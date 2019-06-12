# editProduct

修改产品名称和描述，根据产品id

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述           |
| ------------ | ------ | -------- | -------------- |
| ACCESS_TOKEN | string | 是       | 身份验证       |
| ppid         | int    | 是       | 产品id         |
| name         | string | 是       | 修改的产品名称 |
| describe     | string | 否       | 修改的产品描述 |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |

## 示例

### 请求示例

```java
http://127.0.0.1:7777/iext/back/openv1/ProductController/editProduct
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&ppid=40
&name=修改的名称
&describe=修改的描述
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {}
}
```


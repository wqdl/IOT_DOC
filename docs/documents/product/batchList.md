# productList

产品列表

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述               |
| ------------ | ------ | -------- | ------------------ |
| ACCESS_TOKEN | string | 是       | 身份验证           |
| text         | string | 否       | 搜索产品的名称     |
| pageNum      | int    | 否       | 返回结果中的第几页 |
| pageSize     | int    | 否       | 每页显示的数量     |
| deptid       | int    | 否       | 所属运营商id       |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 调用成功时返回的产品列表信息。详情参见下表body             |

*表 body*

| 名称 | 类型   | 描述                           |
| ---- | ------ | ------------------------------ |
| text | string | 传入的搜索产品的名称           |
| list | list   | 产品列表信息，详情参见下表List |

*表 List*

| 名称     | 类型   | 描述                    |
| -------- | ------ | ----------------------- |
| pageNum  | int    | 返回结果中的第几页      |
| pageSize | int    | 每页显示的数量          |
| startRow | int    | 开始位置行数            |
| endRow   | int    | 结束位置行数            |
| total    | string | 设备总数                |
| pages    | int    | 总页数                  |
| result   | list   | 详情请见下表ProductList |

*表 ProductList*

| 名称       | 类型   | 描述                 |
| ---------- | ------ | -------------------- |
| devicenum  | int    | 设备数量             |
| createtime | date   | 添加时间             |
| nodetype   | int    | 节点类型(1设备2网关) |
| name       | int    | 产品名称             |
| deptid     | int    | 所属运营商id         |
| productkey | string | 产品key              |
| ppid       | int    | 产品id               |
| deptname   | string | 所属运营商名字       |

## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/ProductController/productList
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&text=产品
&pageNum=1
&pageSize=10
&deptid=12589
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {
        "text": "产品",
        "list": {
            "pageNum": 1,
            "pageSize": 10,
            "startRow": 0,
            "endRow": 10,
            "total": 4,
            "pages": 1,
            "result": [
                {
                    "devicenum": 11,
                    "createtime": "Apr 22, 2019",
                    "nodetype": 1,
                    "name": "产品一号_1",
                    "deptid": 12589,
                    "productkey": "0eac912f-ceff-4e9c-af37-575631382eef产品一号key",
                    "ppid": 6,
                    "deptname": "缙云县工业互联网平台"
                },
                ......
            ]
        }
    }
}
```


# productList

产品列表

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述                                    |
| ------------ | ------ | -------- | --------------------------------------- |
| ACCESS_TOKEN | string | 是       | 身份验证                                |
| text         | string | 否       | 搜索名称                                |
| deptid       | int    | 是       | type=1时运营商deptid,type=2时企业deptid |
| pageNum      | int    | 否       | 返回结果中的第几页                      |
| pageSize     | int    | 否       | 每页显示的数量                          |
| type         | int    | 是       | 类型1运营商产品列表2企业                |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 返回数据。详情参见下表body                                 |

*表 body*

| 名称   | 类型   | 描述                           |
| ------ | ------ | ------------------------------ |
| deptid | int    | 运营商deptid                   |
| text   | string | 所属产品id                     |
| list   | list   | 产品列表信息，详情参见下表List |

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
| createtime | date   | 添加时间             |
| nodetype   | int    | 节点类型(1设备2网关) |
| devicenum  | int    | 设备数量             |
| ppid       | int    | 产品id               |
| name       | string | 产品名称             |
| deptname   | string | 所属平台名称         |
| deptid     | int    | 运营商deptid         |
| productkey | string | 产品key              |

## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/IotController/productList
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&deptid=12626
&type=2
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {
        "deptid": 12626,
        "list": {
            "pageNum": 1,
            "pageSize": 10,
            "startRow": 0,
            "endRow": 10,
            "total": 1,
            "pages": 1,
            "result": [
                {
                    "devicenum": 4,
                    "createtime": "四月 22, 2019",
                    "nodetype": 2,
                    "name": "jinyun",
                    "deptid": 12589,
                    "productkey": "75609af7-e3d5-4151-badf-a7693a5ccb61jinyunkey",
                    "ppid": 10,
                    "deptname": "缙云县工业互联网平台"
                }
            ]
        }
    }
}
```


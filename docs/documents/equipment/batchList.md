# batchList

批次列表

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述               |
| ------------ | ------ | -------- | ------------------ |
| ACCESS_TOKEN | string | 是       | 身份验证           |
| pageNum      | int    | 否       | 返回结果中的第几页 |
| pageSize     | int    | 否       | 每页显示的数量     |
| ppid         | int    | 否       | 所属产品id         |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 返回数据。详情参见下表body                                 |

*表 body*

| 名称      | 类型 | 描述                           |
| --------- | ---- | ------------------------------ |
| allNum    | int  | 设备总数                       |
| activeNum | int  | 激活设备数                     |
| onlineNum | int  | 当前在线数                     |
| ppid      | int  | 所属产品id                     |
| list      | list | 产品列表信息，详情参见下表List |

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

| 名称       | 类型   | 描述     |
| ---------- | ------ | -------- |
| pdbid      | int    | 批次id   |
| createtime | date   | 添加时间 |
| num        | int    | 添加数量 |
| ppid       | int    | 产品id   |
| ppname     | string | 产品名称 |

## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/DeviceController/batchList
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&ppid=3
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {
        "activeNum": 0,
        "onlineNum": 0,
        "list": {
            "pageNum": 1,
            "pageSize": 10,
            "startRow": 0,
            "endRow": 10,
            "total": 1,
            "pages": 1,
            "result": [
                {
                    "pdbid": 1,
                    "createtime": "Apr 28, 2019",
                    "num": 6,
                    "ppname": "测试模拟程序专用不要删除",
                    "productkey": "waneqi234key",
                    "ppid": 3
                }
            ]
        },
        "ppid": 3,
        "allNum": 6
    }
}
```


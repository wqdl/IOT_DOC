# chooseDeptList

所属企业列表(添加设备)

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述         |
| ------------ | ------ | -------- | ------------ |
| ACCESS_TOKEN | string | 是       | 身份验证     |
| deptid       | int    | 是       | 运营商deptid |

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 返回数据。详情见下表body                                   |

表body

| 名称     | 类型 | 描述               |
| -------- | ---- | ------------------ |
| deptList | list | 详情见下表deptList |

表deptList

| 名称     | 类型   | 描述     |
| -------- | ------ | -------- |
| deptid   | int    | 企业id   |
| deptname | string | 企业名称 |



## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/IotController/chooseDeptList
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&deptid=12519
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {
        "deptList": [
            {
                "deptid": 12520,
                "deptname": "浙江德世电器有限公司"
            },
            {
                "deptid": 12862,
                "deptname": "永康市动力网络科技有限公司"
            },
            {
                "deptid": 12863,
                "deptname": "浙江三锋实业股份有限公司"
            },
            {
                "deptid": 12864,
                "deptname": "永康市开源动力工具有限公司"
            },
            ......
        ]
    }
}
```


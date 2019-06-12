# addDeviceList

批量添加设备

## 请求方式

GET 方式

## 请求参数

| 名称         | 类型   | 是否必需 | 描述                                    |
| ------------ | ------ | -------- | --------------------------------------- |
| ACCESS_TOKEN | string | 是       | 身份验证                                |
| deptid       | int    | 是       | 所属企业deptid                          |
| ppid         | int    | 是       | 产品id                                  |
| file         | file   | 是       | 文件，文件类型是xls，文件模板见下面图片 |

![1559269079096](图片\1559269079096.png)

## 返回参数

| 名称    | 类型   | 描述                                                       |
| ------- | ------ | ---------------------------------------------------------- |
| success | int    | 请求是否成功，0失败， 1成功， 2不在线， 3错误， 4 已经完成 |
| msg     | string | 调用接口时返回的信息。                                     |
| body    | body   | 返回数据。                                                 |

## 示例

### 请求示例

```java
http://iot.dev.idaqi.com/iext/back/openv1/IotController/addDeviceList
?ACCESS_TOKEN=您获取到的ACCESS_TOKEN
&deptid=12625
&ppid=6
```

### 返回示例

```json
{
    "success": 1,
    "msg": "操作成功！",
    "body": {}
}
```


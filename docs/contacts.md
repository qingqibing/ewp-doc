# 项目联系人
## 查询联系人列表
|接口地址|请求方式|
|:---|:---|
|/pas/contact/list| POST |

### 请求参数
|参数名称|描述|类型|是否必须|其他说明|
|:---|:---|:---|:---|:---|
|pageSize|每天显示条数|number|true|默认10条 设置为0时，则不分页
|pageNum|页码|number|true|默认第一页
|[condition](#联系人列表查询条件)|[联系人列表查询条件](#联系人列表查询条件)|object|true|

#### 联系人列表查询条件
|参数名称|描述|类型|是否必须|其他说明|
|:---|:---|:---|:---|:---|
|name|姓名|string|false|
|projectId|项目id|string|true| 项目ID必须传
|unitId|机构ID|string|false
|unitName|机构名称|string|false
|unitTypeId|单位类型ID|string|false
|sectionId|标段ID|string|false
|positionId|职位ID|string|false


### 响应参数
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|code|number|返回码|
|resultMsg | string | 返回码描述| 
|[data](#查询联系人列表泛型数据)| object | [查询联系人列表泛型数据](#查询联系人列表泛型数据) |

#### 查询联系人列表泛型数据
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|totalCount|number|总记录数
|totalPages|number|总页数
|currentSize|number|当前页记录数|
|pageNum|number|当前页数
|[list](#联系人参数)|array[object]|[联系人列表](#联系人参数)
##### 联系人参数
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|id| string| 联系人ID
|projectId| string|所属项目ID
|unitId|string|所属单位ID
|unitName|string| 所属单位ID |
|unitTypeId|string|所属单位类型ID
|unitType|string|所属单位类型名称
|sectionId|string|标段ID
|sectionName| string|标段名称
|name|string| 姓名
|positionId|string|职位ID
|position| string|职位名称
|phone|string | 手机号
|email|string|邮箱

### 请求示例
```
{
	"pageSize": "10",
	"pageNum": "1",
	"condition": {
		"name": "",
		"projectId": "bceb9e46155e429fb5f45d2b8d2a137f",
		"unitId": "",
		"unitName": "",
		"unitTypeId": "",
		"sectionId": "",
		"positionId": ""
	}
}
```

### 返回示例
```
{
    "code": 0, 
    "resultMsg": "操作成功", 
    "data": {
        "totalCount": 11, 
        "totalPages": 2, 
        "currentSize": 10, 
        "pageNum": 1, 
        "list": [
            {
                "id": "d7336aaf1ceb43e785312547f7dca2d2", 
                "projectId": "bceb9e46155e429fb5f45d2b8d2a137f", 
                "unitName": "单位08", 
                "unitTypeId": "101004", 
                "unitType": "环评公司", 
                "sectionId": "f1fa0ddcb10e4d9e8f46ba0d07780380", 
                "sectionName": "杭绍台站前2标", 
                "name": "李维真", 
                "positionId": "103004", 
                "position": "副教授", 
                "phone": "15825632547", 
                "email": "84615@qq.com"
            }
        ]
    }, 
    "optionalData": {
        "present": true
    }, 
    "success": true
}
```
---
## 查询联系人详情
|接口地址|请求方式|
|:---|:---|
|/pas/contact/detail| GET |
### 请求参数
|参数名称|描述|类型|是否必须|其他说明|
|:---|:---|:---|:---|:---|
|id| 联系人ID|string|true|

### 响应参数
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|code|number|返回码|
|resultMsg | string | 返回码描述| 
|[data](#联系人参数详情)| object | [联系人参数详情](#联系人参数详情) |

#### 联系人参数详情
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|id| string|主键ID
|projectId| string|所属项目ID
|unitId|string | 所属单位ID|
|unitName| string|所属单位名称
|unitType|string|所属单位类型ID
|sectionId| string| 标段ID
|sectionName| string|标段名称
|name| string|姓名
|positionId|string|职位ID
|position|string|职位名称
|phone|string |手机号
|email|string|邮箱

### 请求示例
```
ip:port/pas/contact/detail?id=38720b1119d74f47b0f081be3e8de549
```

### 响应示例
```
{
    "code": 0, 
    "resultMsg": "操作成功", 
    "data": {
        "id": "38720b1119d74f47b0f081be3e8de549", 
        "projectId": "bceb9e46155e429fb5f45d2b8d2a137f", 
        "unitId": null, 
        "unitName": "中铁隧道局", 
        "unitTypeId": "101002", 
        "unitType": "施工单位", 
        "sectionId": "6e1289f245db4961805eb1c701824364", 
        "sectionName": "杭绍台站前3标", 
        "name": "刘建国", 
        "positionId": "103001", 
        "position": "初级工程师", 
        "phone": "13758563258", 
        "email": "465165as@qq.com"
    }, 
    "optionalData": {
        "present": true
    }, 
    "success": true
}
```
--- 
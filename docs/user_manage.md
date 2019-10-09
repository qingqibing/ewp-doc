# 人员管理模块
## 登陆接口
|接口地址|请求方式|
|:---|:---|
|/am/auth/login| POST |

### 请求参数
|参数名称|描述|类型|是否必须|其他说明|
|:---|:---|:---|:---|:---|
|userName| 用户名 | string | true |
|password|密码|string|true| md5加密|

### 响应参数
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|code|number|返回码|
|resultMsg | string | 返回码描述| 
|[data](#登陆接口泛型数据)| object | 登陆接口泛型数据 |

#### 登陆接口泛型数据
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|token|string|token|
|rightForYTGis|boolean|是否有盐通GIS 权限 true 表示有|
|[userInfo](#用户信息)|object|用户信息|
|[employee](#员工信息)|object|员工信息|
|[organizationModel](#机构信息)|object|机构信息|
|[projectList](#用户可管理的项目列表)|array[object]|用户可管理的项目列表|

##### 用户信息
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|id|string|用户ID/userId|
|userName|string|用户名|
|userStatus|string|用户状态|
|userType|string|用户类型|
|createTime|string|创建时间|
|editTime|string|更新时间|

##### 员工信息
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|id|string| 员工ID、empId|
|userId|string|用户ID|
|orgId|string|所属机构ID|
|orgName|string|所属机构名称|
|orgTypeId| string|所属机构类型ID|
|positionId| string|职位ID|
|positionName|string|职位名称|
|code|string|员工编号|
|name| string|员工姓名|
|phone|string|手机号|
|email|string|邮箱|
|createTime|string|创建时间|
|editTime|string|更新时间|

##### 用户可管理的项目列表
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|projectId| string | 项目ID
|projectName| string | 项目名称

##### 机构信息
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|id| string|机构ID、orgId
|number|string|机构编码
|name|string|机构名称
|typeId|string|机构类型ID
|principalName|string|负责人姓名
|principalPhone|string|负责人电话
|parentId|string|父级ID
|logoUrl|string|机构logo url
|createTime|string|创建时间
|editTime|string|更新时间

### 请求示例
```
{
	"userName": "cxl",
	"password": "202cb962ac59075b964b07152d234b70"
}
```
### 响应示例
```
{
    "code": 0, 
    "resultMsg": "操作成功", 
    "data": {
        "token": "0556ce4f-60cf-40df-94a4-59de05d1e1ec", 
        "userInfo": {
            "id": "961b6b0ac22a11e8af7de0d55e9232d2", 
            "userName": "cxl", 
            "userStatus": "115001", 
            "userType": "136001", 
            "createTime": "2018-09-27 15:54:39", 
            "editTime": "2019-04-01 15:27:08"
        }, 
        "employee": {
            "id": "415957a7c21f11e8af7de0d55e9232d2", 
            "userId": "961b6b0ac22a11e8af7de0d55e9232d2", 
            "orgId": "5ae6bba9bd7511e8af7de0d55e9232d2", 
            "orgName": "杭绍台铁路筹建协调小组", 
            "orgTypeId": "101001", 
            "positionId": "103003", 
            "positionName": "高级工程师", 
            "code": "cxl", 
            "name": "cxl", 
            "phone": "18328667563", 
            "email": "18328667563@163.com", 
            "createTime": "2018-09-27 14:33:33", 
            "editTime": "2018-09-27 15:54:39"
        }, 
        "organizationModel": {
            "id": "5ae6bba9bd7511e8af7de0d55e9232d2", 
            "number": "HST0001", 
            "name": "杭绍台铁路筹建协调小组", 
            "typeId": "101001", 
            "principalName": "吴培荣", 
            "principalPhone": "13000000000", 
            "parentId": "0", 
            "logoUrl": "/jpg/微信图片_20180727115024.jpg", 
            "createTime": "2018-09-21 16:07:16", 
            "editTime": "2019-01-25 09:58:55"
        }, 
        "projectList": [
            {
                "projectId": "bceb9e46155e429fb5f45d2b8d2a137f", 
                "projectName": "杭州经绍兴至台州"
            }
        ], 
        "rightForYTGis": false
    }, 
    "success": true, 
    "optionalData": {
        "present": true
    }
}
```

## 退出登录
|接口地址|请求方式|
|:---|:---|
|/am/auth/logout| GET |

### 响应参数
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|code|number|返回码|
|resultMsg | string | 返回码描述| 
|[data]| object | 泛型数据 |

### 响应示例
```
{
    "code": 0, 
    "resultMsg": "操作成功", 
    "data": null, 
    "success": true, 
    "optionalData": {
        "present": false
    }
}
```
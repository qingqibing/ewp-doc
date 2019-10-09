# 项目信息管理
## 查询项目详情
|接口地址|请求方式|
|:---|:---|
|/pas/project/detail| GET |
### 请求参数
|参数名称|描述|类型|是否必须|其他说明|
|:---|:---|:---|:---|:---|
|id| 项目ID | string | true |
### 响应参数
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|code|number|返回码|
|resultMsg | string | 返回码描述| 
|[data](#查询项目详情泛型数据)| object | [查询项目详情泛型数据](#查询项目详情泛型数据)|

#### 查询项目详情泛型数据
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|id|string|项目主键ID
|serialNumber|string|项目编号
|name|string|项目名称
|shortName|string|简称|
|mode|number|项目模式ID
|modeName| string|项目模式描述
|mileage|number|里程数（公里）
|sectionNumber|number|标段数|
|principalName| string| 负责人姓名
|principalPhone|string|负责人电话
|planedStartTime|string|计划开工时间
|planedTrafficTime|string|计划通车时间
|investment|number|项目投资金额（千万）
|investmentInEnvironmental|number| 环保投资金额（千万）|
|describe|string|项目描述
|[units](#关联单位列表)|array[object]|[关联单位列表](#关联单位列表)|
|[attachments](#项目详情附件列表)|array[object]|[项目详情附件列表](#项目详情附件列表)
|[progresses](#项目进度列表)|array[object]|[项目进度列表](#项目进度列表)
|[startPoints](#项目起点)|array[object]|[项目起点](#项目起点)|

##### 关联单位列表 
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|unitId|string|单位ID
|groupCode|string| 分组ID<br/> 分组ID是为了解决水保监理和环保监理两种类型<br/>水保监理的groupCode为unit001<br>环保监理的groupCode为unit002.<br>其他的groupCode与type字段相同
|name| string|单位名称
|type| number|单位类型
|typeDesc|string|单位类型描述|

##### 项目详情附件列表
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|name|string|附件名称
|type|number|附件类型
|typeDesc|string|附件类型描述
|url|string|附件保存地址|

##### 项目进度列表
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|progress| string | 进度编码 见数据字典
|progressDesc| string |进度描述
|progressTime|string |进度时间
##### 项目起点
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|lineType|string|线路类型
|lineTypeDesc| string|线路类型描述
|orderNumber| string|点序号
|longitude|string|经度
|latitude| string|纬度
|pointType|string|点类型|
|pointSerialNumber|string|点编号
|pointName|string|点名称

### 请求示例
```
ip:port/pas/project/detail?id=bceb9e46155e429fb5f45d2b8d2a137f
```
### 响应示例
```
{
    "code": 0, 
    "resultMsg": "操作成功", 
    "data": {
        "id": "bceb9e46155e429fb5f45d2b8d2a137f", 
        "serialNumber": "HZ-SX-TZ-01ZK", 
        "name": "杭州经绍兴至台州", 
        "shortName": "杭绍台铁路", 
        "mode": "106003", 
        "modeName": "EPC", 
        "mileage": 224.37, 
        "sectionNumber": 8, 
        "principalName": "李力鹏", 
        "principalPhone": "15338769816", 
        "planedStartTime": "2018/06", 
        "planedTrafficTime": "2020/12", 
        "investment": 4489.4, 
        "investmentInEnvironmental": 84, 
        "describe": "本工程由既有杭甬客专的绍兴北站接轨，而后经绍兴市越城、上虞、嵊州、新昌和台州市天台、临海、椒江、路桥、温岭等县市区，终于既有甬台温铁路的温岭站，新建正线全长 224.368 km，新建绍兴地区联络线及动车走行线 7.468km、温岭地区联络线及动车走行线 8.718km。正线为双线电气化客运专线，设计速度
目标值为 350km/h。正线设桥梁 72 座/95.44km，占正线长度的 42.5%；正线设隧道 54 座/98.743km，占正线长度的 44.0%。全线共设绍兴北、新绍兴北、东关、三界、嵊州新昌、天台、临海、台州中心、温岭等 9 座车站，温岭地区新建动车运用所 1 处、绍兴地区新建动车存车场 1 处，新建牵引变电所 5 座。", 
        "units": [
            {
                "unitId": "f15166eec12e11e8af7de0d55e9232d2", 
                "groupCode": "101003", 
                "name": "中国设计二院", 
                "type": "101003", 
                "typeDesc": "设计单位"
            }
        ], 
        "attachments": [
            
            {
                "name": "IMG_20181022_152508.jpg", 
                "type": "0", 
                "typeDesc": "项目照片", 
                "url": "/download/828"
            }
        ], 
        "progresses": [
            {
                "progress": "128001", 
                "progressDesc": "启动", 
                "progressTime": "2018/08/01"
            }
        ], 
        "startPoints": [
            {
                "lineType": "0", 
                "lineTypeDesc": "计划线路", 
                "orderNumber": 1, 
                "longitude": 120.583384, 
                "latitude": 30.038617, 
                "pointType": "标段端点", 
                "pointSerialNumber": "DGK0+758.3",
                "pointName": null
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

## 查询项目下的标段列表
|接口地址|请求方式|
|:---|:---|
|/pas/section/list| POST |
### 请求参数
|参数名称|描述|类型|是否必须|其他说明|
|:---|:---|:---|:---|:---| 
|pageNum| 页码 | number | true |  默认第一页
|pageSize| 每页条数 |number| true| 默认10条 设置为0时，则不分页
|[condition](#查询条件)|[查询条件](#查询条件)|object|false|
#### 查询条件
|参数名称|描述|类型|是否必须|其他说明|
|:---|:---|:---|:---|:---| 
|projectId|所属项目主键ID|string|false| 

### 响应参数
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|code|number|返回码|
|resultMsg | string | 返回码描述| 
|[data](#标段列表数据)| object | [标段列表数据](#标段列表数据) |

#### 标段列表数据
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|totalCount|number|总记录数|
|totalPages|number|总页数|
|currentSize|number|当前页记录数
|pageNum|number|当前页数
|[list](#标段详细信息)|array[object]|[标段详细信息](#标段详细信息)

##### 标段详细信息
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
|id| string|标段ID|
|projectId|string|项目ID
|serialNumber|string|标段编号
|name|string|标段名称
|start|string|标段起点
|end|string|标段终点
|constructionUnitId|string|施工单位Id|
|constructionUnitName|string|施工单位名称
|principalName|string|负责人名称
|principalPhone|string|负责人电话
|remarks|string|备注|
|[persons](#标段人员列表)|array[object]|[标段人员列表](#标段人员列表)

###### 标段人员列表
| 参数名称 | 数据类型 | 描述 |
|:---|:---|:---|
 personId|string|人员ID
 name|string|人员名称
 type|number|人员类型
 typeDesc|string|人员类型描述
 
### 请求示例
```
{
	"pageNum": "1",
	"pageSize": "10",
	"condition": {
		"projectId": "bceb9e46155e429fb5f45d2b8d2a137f"
	}
}
```
### 响应示例
```
{
    "code": 0, 
    "resultMsg": "操作成功", 
    "data": {
        "totalCount": 8, 
        "totalPages": 1, 
        "currentSize": 8, 
        "pageNum": 1, 
        "list": [
            {
                "id": "da23f03842104c8fb16b3fbd5868b2e8", 
                "projectId": "bceb9e46155e429fb5f45d2b8d2a137f", 
                "serialNumber": "HSTZQ-1", 
                "name": "杭绍台站前1标", 
                "start": "GDK0+775.10", 
                "end": "DK27+380", 
                "constructionUnitId": "0fbf8b95c2fe11e8af7de0d55e9232d2", 
                "constructionUnitName": "中铁三局集团有限公司", 
                "principalName": "景晔", 
                "principalPhone": "18202910261", 
                "remarks": "含正线桥梁29.16km，绍兴北站(既有站)，绍兴梁场。", 
                "persons": [
                    {
                        "personId": null, 
                        "name": "景晔", 
                        "type": "3", 
                        "typeDesc": null
                    }
                ]
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
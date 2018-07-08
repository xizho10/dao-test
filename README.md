# 使用说明



本文大纲如下：
* [使用说明](#使用说明)
	* [1. 素材管理](#1-素材管理)
		* [1.1 厂家](#11-厂家)
		* [1.2 Frame](#12-Frame)
		* [1.3 Matcard](#13-Matcard])
		* [1.4 Background](#14-Background])
		* [1.5 Scene](#15-Scene])
	* [2. 平台管理](#2-平台管理)	
	* [3. 商户管理](#3-商户管理)
	* [4. 用户管理](#4-用户管理)	

## 1. 平台管理

###  1.1 **厂家**

>上传图片 /api/v1/warehouse/upload/factory

>增删改查  /api/v1/warehouse/factory

```
{
  "action":"update",//add update delete get getlist
  "id":"zjC5wy14",
  "info":""  //选填
}

{

  "id": "",
  "info":"",
  "name":"厂家名称",
  "displayname":"显示昵称",
  "icon":"url地址",
  "createtime":"创建时间"
  
}

```



###  1.2 **Frame**

>上传图片 /api/v1/warehouse/upload/frame

>增删改查  /api/v1/warehouse/info/frame

```
{
  "action":"update",//add update delete get getlist
  "id":"zjC5wy14",
  "info":"",
  "name":"名称",
  "factory":"厂家",
  "color":"",
  "style":"风格",
  "paytype":"付费类型",
  "state":"状态",
  "createtime":"创建时间"
}

{
  "action":"getlist",//检索
  "page":1,
  "pagesize":10,
  "name":"名称", //选填
  "factory":"厂家",//选填
  "color":"",//选填
  "style":"风格",//选填
  "paytype":"付费类型",//选填
  "state":"状态" //选填
}

{

  "id": "",
  "info":"",
  "name":"名称",
  "factory":"厂家",
  "color":"",
  "style":"风格",
  "paytype":"付费类型",
  "state":"状态",
  "createtime":"创建时间"
  
}

```

###  1.3 **Matcard**


>上传图片 /api/v1/warehouse/upload/matcard

>增删改查  /api/v1/warehouse/info/matcard

```
{
  "action":"update",//add update delete get getlist
  "id":"zjC5wy14",
  "info":["12345",9,true]
}

{
  "action":"getlist",//检索
  "page":1,
  "pagesize":10,
  "name":"名称", //选填
  "factory":"厂家",//选填
  "color":"",//选填
  "style":"风格",//选填
  "paytype":"付费类型",//选填
  "state":"状态" //选填
}

{

  "id": "",
  "info":"",
  "name":"名称",
  "factory":"厂家",
  "color":"",
  "style":"风格",
  "paytype":"付费类型",
  "state":"状态",
  "createtime":"创建时间"
  
}

```

###  1.4 **Background**


>上传图片 /api/v1/warehouse/upload/background

>增删改查  /api/v1/warehouse/info/background

```
{
  "action":"update",//add update delete get getlist
  "id":"zjC5wy14",
  "info":""
}

{
  "action":"getlist",//检索
  "page":1,
  "pagesize":10,
  "name":"名称", //选填
  "factory":"厂家",//选填
  "color":"",//选填
  "style":"风格",//选填
  "paytype":"付费类型",//选填
  "state":"状态" //选填
}

{

  "id": "",
  "info":"",
  "name":"名称",
  "paytype":"付费类型",
  "state":"状态",
  "createtime":"创建时间"
  
}

```

###  1.5 **Scene**


>上传图片 /api/v1/warehouse/upload/scene

>增删改查  /api/v1/warehouse/info/scene

```
{
  "action":"update",//add update delete get getlist
  "id":"zjC5wy14",
  "info":""
}

{
  "action":"getlist",//检索
  "page":1,
  "pagesize":10,
  "name":"名称", //选填
  "factory":"厂家",//选填
  "color":"",//选填
  "style":"风格",//选填
  "paytype":"付费类型",//选填
  "state":"状态" //选填
}

{

  "id": "",
  "info":"",
  "name":"名称",
  "type":"类型",
  "paytype":"付费类型",
  "state":"状态",
  "createtime":"创建时间"
  
}

```
## 2. 平台管理

###  2.1 **登录**

>登录 /api/v1/warehouse/platform/login


```
//短信登录
{
  "codeid": "77be1c15-c0a1-413e-87c3-af90604ff071",
  "code":"123456",
  "deviceid" : "C3B38031-AC78-4C2C-9C4A-469A28C54E60",  
  "nationcode":"86",
  "userphone" : "15821703552"
  
}

//第三方
{
  "openid": "openid2",
  "deviceid":"dev1"
}


{
    "action": "warehouseUserLogin",
    "error": 0,
    "desc": "SUCCESS",
    "result": {
        "createtime": "20180630230935",
        "usericon": "",
        "userphone": "15821703552",
        "userid": "81lK4X4Wz0",
        "deviceid": "C3B38031-AC78-4C2C-9C4A-469A28C54E60",
        "nationcode": "86",
        "username": "",
	"auth":"" //拥有的权限
    }
}

```

>添加子管理员  /api/v1/warehouse/platform/login

```
{
  "action": "addSubManager",
  "openid":"12345",
  "deviceid":"deviceid",
  "username":"user x",
  "auth":"frame,backgroud",
  "duty":"yunying"
}
```

>关闭子管理员权限 /api/v1/warehouse/platform

```
{

  "action": "update",
  "userid":"p81lASuaCxD2",
  "field":"state",
  "state":"disable"
}
```

>查询管理员列表 /api/v1/warehouse/platform

```
{

  "action": "getlist",
  "page":1,
  "pagesize":10
}
```

## 3. 商户管理

>登录 /api/v1/warehouse/shopowner/login


>修改素材   /api/v1/warehouse/shopowner

```
//短信登录
{

  "codeid": "77be1c15-c0a1-413e-87c3-af90604ff071",
  "code":"123456",
  "deviceid" : "C3B38031-AC78-4C2C-9C4A-469A28C54E60",  
  "nationcode":"86",
  "userphone" : "15821703552"
  
}
//第三方
{
  "openid": "openid2",
  "deviceid":"dev1"
}

//修改素材
{
 "action":"update",
 "field":"frame",//修改哪个字段就填哪个字段，目前只能改素材background，matcard，scene
 "frame":"ssgsdg" //填要改的 对应字段的内容
}
{
    "action": "warehouseUserLogin",
    "error": 0,
    "desc": "SUCCESS",
    "result": {
        "createtime": "20180630230935",
        "usericon": "",
        "userphone": "15821703552",
        "viptime": "",
        "background": "",//背景列表
        "userid": "81lK4X4Wz0",
        "deviceid": "C3B38031-AC78-4C2C-9C4A-469A28C54E60",
        "nationcode": "86",
        "matcard": "", //卡纸列表
        "username": "",
        "frame": "",//框列表
        "scene": ""//场景列表
    }
}
```

>增删改查子管理员、微代理  /api/v1/warehouse/shopowner/submanager

>设置素材是否上架    /api/v1/warehouse/shopowner/{material type}/{id}

>购买会员           /api/v1/warehouse/shopowner/buyvip

```
{
  "action":"update",//add update delete get getlist
  "name":"",
  "auth":"",权限
  "expire":"",过期时间
  "duty":""  职责
}
```

## 4. 用户管理

>查询用户列表  /api/v1/warehouse/user

```
{
  "action": "get",//通过userid或手机号查询
  "userid":"70PA4KY1bd",
  "usrphone":"15821703552"
}
{
  "action": "getlist",
  "type":"trdparty",//查询通过第三方注册的用户，填其他值是手机号注册的用户
  "page":1,
  "pagesize":10
}
```


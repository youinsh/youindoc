# 汉方接入流程：
## 汉方页面点击《申请加入互动》 调用有因注册用户接口如下：


### 用户--注册用户,app端用户注册返回token
```
POST /api/v1/user/register/
```
#### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`username`|`string`|是|用户昵称|
|`image`|`string`|是|头像|
|`user_id`|`int`|是|渠道方用户id|
|`channel_uid`|`string`|是|渠道方唯一标识：请从有因后台获取|
##### 请求示例
```json
POST /api/v1/user/register/

Content-Type: application/json
Authorization: jwt {{token}}
{
    "username":"xxx",
    "photo":"xxx",
    "user_id":xx,
    "channel_uid":"xxx"
}
```

#### 返回
```json
{
    "code": 200,
    "msg": "success",
    "result": {
        "token": "xxx",//有因用户token
        "user_id": 11, //有因用户id
        "exprise_time":“xxx”//token过期时间
    }
}
```

## 返回有因系统用户id和用户token以及token过期时间，汉方可以将有因用户对应本地用户写入数据库1对1
## 成功之后调用LeanCloud SDK发送自定义消息，消息体如下：
```
观看用户申请加入房间

{"_lctext":"{\"userId\":444,\"userJoin\":true,\"userStatus\":9,\"userName\":\"赵强测试\",\"dateTime\":1558086973000}","_lcattrs":{"avatar":"https://stagingcdn.youinsh.cn/staging/static/user/images/default_user.png"},"_lctype":-1}


userId：有因用户id
userJoin：true
userStatus：9
userName：用户昵称
dateTime：当前时间戳
avatar：用户头像
_lctype：-1
```



##有因系统主持人处理请求，同意，拒绝，不处理返回LeanCloud消息，汉方需要根据收到到LeanCloud消息解析
```
同意请求返回

{"_lctext":"{\"userId\":444,\"userJoin\":true,\"userStatus\":13,\"dateTime\":1558087136000,\"from\":\"webRTC\"}","_lcattrs":{"avatar":"https://stagingcdn.youinsh.cn/staging/static/user/images/default_user.png"},"_lctype":-1}

userId：有因用户id
dateTime：时间戳
avatar：用户头像
（其他参数都如上固定）
```

```
拒绝请求返回
{"_lctext":"{\"userId\":444,\"userJoin\":true,\"userStatus\":14,\"dateTime\":1558087178000,\"from\":\"webRTC\"}","_lcattrs":{"avatar":"https://stagingcdn.youinsh.cn/staging/static/user/images/default_user.png"},"_lctype":-1}

userId：有因用户id
dateTime：时间戳
avatar：用户头像
（其他参数都如上固定）

```
```
不处理请求，当汉方1分钟后还未收到任何接受或者拒绝当消息，则视为当前请求未被处理
```


## 当接受请求后，pc端web调用下面接口重定向到有因互动系统

### 会议系统--有因渠道方web端用户跳转播放
```
GET /api/v1/user/reg_from_channel/?user_id=xx&auth_token=xx&next=/course/webRTCUser/?id=xx&enterprise_id=xx
```
#### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`user_id`|`int`|是|渠道平台用户的ID|
|`auth_token`|`string`|是|自定义验证密钥：密钥格式请联系有因技术客服|
|`id`|`int`|是|课程id|
|`enterprise_id`|`int`|否|创建课程返回的enterprise_id|


##### 请求示例
get重定向到观看页面
#### 返回
```
嵌入网页播放页面
```


## app端调用以下接口获取用户token

### 用户--根据用户id获取用户token
```
POST /api/v1/user/get_token_channel/
```
#### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`user_id`|`int`|是|用户id|

##### 请求示例
```json
POST /api/v1/user/get_token_channel/

Content-Type: application/json
Authorization: jwt {{token}}
{
    "user_id":xx
}
```

#### 返回
```json
{
    "code": 200,
    "msg": "success",
    "result": {
        "token": "xxx",//有因用户token
        "exprise_time":“xxx”//token过期时间
    }
}
```

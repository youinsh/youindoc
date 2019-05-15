## 用户--注册用户,app端用户注册返回token

```
POST /api/v1/user/register/

```

### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`username`|`string`|是|用户昵称|
|`image`|`string`|是|头像|
|`user_id`|`int`|是|渠道方用户id|
|`channel_uid`|`string`|是|渠道方唯一标识：请从有因后台获取|

#### 请求示例

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

### 返回

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


## 会议系统--有因渠道方web端用户跳转播放
```
GET /api/v1/user/reg_from_channel/?user_id=xx&auth_token=xx&next=/course/webRTCUser/?id=xx&enterprise_id=xx
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`user_id`|`int`|是|渠道平台用户的ID|
|`auth_token`|`string`|是|自定义验证密钥：密钥格式请联系有因技术客服|
|`id`|`int`|是|课程id|
|`enterprise_id`|`int`|否|创建课程返回的enterprise_id|


#### 请求示例
get重定向到观看页面
### 返回
```
嵌入网页播放页面
```


## 访问地址
线上： https://live.youinsh.com
测试： https://live.test.youinsh.cn

## 访问密钥
app_id:	xxxxx

app_secret:	xxxxx

## 鉴权
```
用户名密码授权登陆页面 /user/oauth_login/?next=xxx

web微信授权登陆  /user/qiniu/web/wechat/?next=xxx
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`next`|`string`|是|授权成功之后的跳转地址|

#### 请求示例
用户授权后回调到七牛的回调地址，地址会带上参数scode
### 返回
如七牛next地址为:	http://xxxx.com/callback/
则会跳转到：http://xxxx.com/callback/?scode=xxxxx



## 获取用户jwt token

```
POST /user/scode/
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`app_id`|`string`|是|api授权唯一app_id|
|`app_secret`|`string`|是|api授权唯一密钥|
|`scode`|`string`|是|从回调地址中获取都scode|


#### 请求示例
```json
POST /user/scode/
Content-Type: application/json
{
    "app_id": "xxxxxx",
    "app_secret": "xxxxxxxx",
    "scode": "xxxxx"
   
}
```
### 返回
```json
HTTP CODE 200
```
### 错误
- 400 参数错误
- 408 scode过期（有效期为5分钟）
- 409 scode已经被使用（默认每个scode只能被调用一次，一次后失效）

```json
HTTP CODE 500
{
    "code": 200,
    "msg": "success",
    "result": {
        "exp_time": "1548730476",
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE1NDg3MzA0NzYsImVtYWlsIjoiIiwidXNlcl9pZCI6NDE2LCJ1c2VybmFtZSI6IjE3NTIxMDI4MjM2In0.GvoyAvyF98blMOYxIw_abHXW7TPTUaOAKzEzk3w-xqw"
    }
}


```

## 获取用户信息
```
GET /user/user_info/
```

### 参数


#### 请求示例
```json
GET /user/user_info/
Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```
### 返回
```json
HTTP CODE 200
{
    "msg": "success",
    "code": 200,
    "result": {
        "id": 386,		//用户自增主键
        "user_id": "571a5b94ddae11e8b85300163e0097a6",		//标识用户唯一uid
        "name": "jjjjjjjlk",		//昵称
        "sex": 1,		//性别	1:男，0:女
        "age": 30,		//年龄，此数据可以不更新，在有因平台年龄并不重要几乎是假数据
        "tel": "",			//手机号码，
	"photo": "https://staging.png",		头像地址，此字段用于前端显示
        "description": null			//个人简介
    }	
}
```

## 登出
```
GET /user/oauth_login_out/?next=xxx
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`next`|`string`|否|登出地址|

### 返回

返回授权地址

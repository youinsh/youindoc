## 访问地址
线上： https://niuclass.qiniuapi.com
测试： https://api-niuclass.qiniu.io

## 鉴权
```
POST /login
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`mobile`|`string`|是|渠道商在niuclass的账户|
|`password`|`string`|是|渠道商在niuclass账户的密码|

#### 请求示例
```json
POST /login
Content-Type: application/json

{
    "mobile": "192321213",
    "password": "Wxxhh2112333"
}
```
### 返回
返回的结果是 jwt token, 解析出来会有一个过期时间，如果过期了，那么渠道商需要重新鉴权。
在后面的每次请求都需要带上这个 jwt token，放在 header 里面里面：
`Authorization: Bearer {{token}}`
```json
{
    "token": "ebGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTgzLCJpc3N1cmVfYXQiOjE1NDgzMjQwsImV4cGlyZSI6NjI2MzIzfQ.cMyW1MNdF1HIk60p0XNgCWTh0mHX35G2ymaP4"
}
```


## 更新用户信息
```
PUT /api/user/profile
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`user_id`|`string`|是|用户的唯一 ID|
|`name`|`string`|否|用户的昵称, 如果不传那么就不更新|
|`mobile`|`string`|否|用户的手机, 如果不传那么就不更新|
|`avatar`|`string`|否|用户的头像，需要完整的 可以访问的地址，如果不传那么就不更新|
|`email`|`string`|否|用户的邮箱，如果不传那么就不更新|
|`description`|`string`|否|用户简介，如果不传那么就不更新|

#### 请求示例
```json
PUT /api/user/profile
Content-Type: application/json
Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
{
    "user_id": "uuid",
    "name": "test1",
    "mobile": "1000000000",
    "avatar": "http://helloworld.png",
    "email": "test@qiniu.com",
    "description": "Hello world"
}
```
### 返回
```json
HTTP CODE 200
```
### 错误
- 400 参数错误
- 404 用户没有找到
- 500 服务内部错误

```json
HTTP CODE 500
{
    "message": "update userinfo failed",
    "code": "INTERNAL_SERVER_ERROR"
}

```

## 获取课程列表
```
GET /api/courses
```

### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`limit`|`int`|否|每次请求的数据量，最大100，默认100|
|`offset`|`int`|否|偏移量，分页的时候需要|
|`start`|`timestamp`|否|时间范围，开始时间 单位 秒|
|`end`|`timestamp`|否|时间范围，结束时间 单位 秒，如果开始时间和结束时间都不传，默认返回在课程周期里面的课程|
|`organization_id`|否|机构ID，可以获取指定机构的课程，不传默认返回当前渠道商所以机构的课程|

#### 请求示例
```json
GET /api/courses?limit=50&offset=1
Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```
### 返回
```json
HTTP CODE 200
{
    "items": [{
        "id": 23, // 课程 ID
        "title": "古诗词鉴赏", // 课程名称
        "poster_url": "https://hellwea.com/porst.png", // 课程封面
        "description": "古诗词鉴赏", // 课程描述
        "duration": 3600, // 单节课时长
        "latest_class_time": 1548381600, // 课程最近的开始时间
        "organization_id": 23 // 课程属于的组织ID
    }...]
}
```

### 错误
- 400 参数错误
- 500 服务内部错误
- 403 没有权限查看指定组织的课程
```json
http code 403
{
    "message": "can't access organization",
    "code": "FORBIDDEN"
}
```

## 创建机构
```
POST /api/organization
```

### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`name`|`string`|是|机构名称|
|`key`|`string`|是|机构英文名称|
|`organization_owner`|`string`|是|机构的owner ID|
|`slogan`|`string`|否|机构口号|
|`description`|`string`|否|机构描述|
|`logo`|`string`|否|机构logo|
|`company`|`string`|否|机构所属的公司|

#### 请求示例
```json
POST /api/organization
Content-Type: application/json
Authorization: Bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

{
    "name": "古诗词鉴赏",
    "key": "Appreciating ancient Chinese poems",
    "organization_owner": "userid",
    "slogan": "It's easy to learn chinese poems",
    "description": "hello, welcome to our org",
    "logo": "https://helloworld.com/logo.png",
    "company": "未来科幻局"
}
```
### 返回
```json
HTTP CODE 201
{
    "id": 33,
    "name": "古诗词鉴赏",
    "key": "Appreciating ancient Chinese poems",
    "slogan": "It's easy to learn chinese poems",
    "description": "hello, welcome to our org",
    "logo": "https://helloworld.com/logo.png",
}
```
### 错误
- 400 参数错误
- 500 内部错误
```json
http code 500
{
    "message": "create organization failed",
    "code": "INTERNAL_SERVER_ERROR"
}
``

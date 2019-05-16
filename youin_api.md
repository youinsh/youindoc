<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [访问地址](#%E8%AE%BF%E9%97%AE%E5%9C%B0%E5%9D%80)
- [鉴权](#%E9%89%B4%E6%9D%83)
  - [参数](#%E5%8F%82%E6%95%B0)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B)
  - [返回](#%E8%BF%94%E5%9B%9E)
- [上传文件获取oss临时sts上传token](#%E4%B8%8A%E4%BC%A0%E6%96%87%E4%BB%B6%E8%8E%B7%E5%8F%96oss%E4%B8%B4%E6%97%B6sts%E4%B8%8A%E4%BC%A0token)
  - [参数](#%E5%8F%82%E6%95%B0-1)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-1)
  - [返回](#%E8%BF%94%E5%9B%9E-1)
  - [错误](#%E9%94%99%E8%AF%AF)
- [获取上传视频到oss到路径](#%E8%8E%B7%E5%8F%96%E4%B8%8A%E4%BC%A0%E8%A7%86%E9%A2%91%E5%88%B0oss%E5%88%B0%E8%B7%AF%E5%BE%84)
  - [参数](#%E5%8F%82%E6%95%B0-2)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-2)
  - [返回](#%E8%BF%94%E5%9B%9E-2)
  - [错误](#%E9%94%99%E8%AF%AF-1)
- [创建分类](#%E5%88%9B%E5%BB%BA%E5%88%86%E7%B1%BB)
  - [参数](#%E5%8F%82%E6%95%B0-3)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-3)
  - [返回](#%E8%BF%94%E5%9B%9E-3)
  - [错误](#%E9%94%99%E8%AF%AF-2)
- [获取分类列表](#%E8%8E%B7%E5%8F%96%E5%88%86%E7%B1%BB%E5%88%97%E8%A1%A8)
  - [参数](#%E5%8F%82%E6%95%B0-4)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-4)
  - [返回](#%E8%BF%94%E5%9B%9E-4)
- [分类---删除-上线-下线](#%E5%88%86%E7%B1%BB---%E5%88%A0%E9%99%A4-%E4%B8%8A%E7%BA%BF-%E4%B8%8B%E7%BA%BF)
  - [参数](#%E5%8F%82%E6%95%B0-5)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-5)
  - [返回](#%E8%BF%94%E5%9B%9E-5)
  - [错误](#%E9%94%99%E8%AF%AF-3)
- [分类-修改](#%E5%88%86%E7%B1%BB-%E4%BF%AE%E6%94%B9)
  - [参数](#%E5%8F%82%E6%95%B0-6)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-6)
  - [返回](#%E8%BF%94%E5%9B%9E-6)
  - [错误](#%E9%94%99%E8%AF%AF-4)
- [分类-置顶](#%E5%88%86%E7%B1%BB-%E7%BD%AE%E9%A1%B6)
  - [参数](#%E5%8F%82%E6%95%B0-7)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-7)
  - [返回](#%E8%BF%94%E5%9B%9E-7)
  - [错误](#%E9%94%99%E8%AF%AF-5)
- [直播-创建](#%E7%9B%B4%E6%92%AD-%E5%88%9B%E5%BB%BA)
  - [参数](#%E5%8F%82%E6%95%B0-8)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-8)
  - [返回](#%E8%BF%94%E5%9B%9E-8)
  - [错误](#%E9%94%99%E8%AF%AF-6)
- [录播-创建](#%E5%BD%95%E6%92%AD-%E5%88%9B%E5%BB%BA)
  - [参数](#%E5%8F%82%E6%95%B0-9)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-9)
  - [返回](#%E8%BF%94%E5%9B%9E-9)
  - [错误](#%E9%94%99%E8%AF%AF-7)
- [直播/录播-删除](#%E7%9B%B4%E6%92%AD%E5%BD%95%E6%92%AD-%E5%88%A0%E9%99%A4)
  - [参数](#%E5%8F%82%E6%95%B0-10)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-10)
  - [返回](#%E8%BF%94%E5%9B%9E-10)
  - [错误](#%E9%94%99%E8%AF%AF-8)
- [直播/录播-查看直播/录播课程详情](#%E7%9B%B4%E6%92%AD%E5%BD%95%E6%92%AD-%E6%9F%A5%E7%9C%8B%E7%9B%B4%E6%92%AD%E5%BD%95%E6%92%AD%E8%AF%BE%E7%A8%8B%E8%AF%A6%E6%83%85)
  - [参数](#%E5%8F%82%E6%95%B0-11)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-11)
  - [返回](#%E8%BF%94%E5%9B%9E-11)
  - [错误](#%E9%94%99%E8%AF%AF-9)
- [直播/录播-修改直播/录播信息](#%E7%9B%B4%E6%92%AD%E5%BD%95%E6%92%AD-%E4%BF%AE%E6%94%B9%E7%9B%B4%E6%92%AD%E5%BD%95%E6%92%AD%E4%BF%A1%E6%81%AF)
  - [参数](#%E5%8F%82%E6%95%B0-12)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-12)
  - [返回](#%E8%BF%94%E5%9B%9E-12)
- [直播--获取存在的直播列表](#%E7%9B%B4%E6%92%AD--%E8%8E%B7%E5%8F%96%E5%AD%98%E5%9C%A8%E7%9A%84%E7%9B%B4%E6%92%AD%E5%88%97%E8%A1%A8)
  - [参数](#%E5%8F%82%E6%95%B0-13)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-13)
  - [返回](#%E8%BF%94%E5%9B%9E-13)
  - [错误](#%E9%94%99%E8%AF%AF-10)
- [录播--获取录播列表](#%E5%BD%95%E6%92%AD--%E8%8E%B7%E5%8F%96%E5%BD%95%E6%92%AD%E5%88%97%E8%A1%A8)
  - [参数](#%E5%8F%82%E6%95%B0-14)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-14)
  - [返回](#%E8%BF%94%E5%9B%9E-14)
  - [错误](#%E9%94%99%E8%AF%AF-11)
- [直播/录播--获取推流地址、密钥，播放的视频地址](#%E7%9B%B4%E6%92%AD%E5%BD%95%E6%92%AD--%E8%8E%B7%E5%8F%96%E6%8E%A8%E6%B5%81%E5%9C%B0%E5%9D%80%E5%AF%86%E9%92%A5%E6%92%AD%E6%94%BE%E7%9A%84%E8%A7%86%E9%A2%91%E5%9C%B0%E5%9D%80)
  - [参数](#%E5%8F%82%E6%95%B0-15)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-15)
  - [返回](#%E8%BF%94%E5%9B%9E-15)
  - [错误](#%E9%94%99%E8%AF%AF-12)
- [直播--转成录播](#%E7%9B%B4%E6%92%AD--%E8%BD%AC%E6%88%90%E5%BD%95%E6%92%AD)
  - [参数](#%E5%8F%82%E6%95%B0-16)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-16)
  - [返回](#%E8%BF%94%E5%9B%9E-16)
- [用户--注册用户](#%E7%94%A8%E6%88%B7--%E6%B3%A8%E5%86%8C%E7%94%A8%E6%88%B7)
  - [参数](#%E5%8F%82%E6%95%B0-17)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-17)
  - [返回](#%E8%BF%94%E5%9B%9E-17)
- [用户--修改用户信息](#%E7%94%A8%E6%88%B7--%E4%BF%AE%E6%94%B9%E7%94%A8%E6%88%B7%E4%BF%A1%E6%81%AF)
  - [参数](#%E5%8F%82%E6%95%B0-18)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-18)
  - [返回](#%E8%BF%94%E5%9B%9E-18)
- [课程--开启白名单访问](#%E8%AF%BE%E7%A8%8B--%E5%BC%80%E5%90%AF%E7%99%BD%E5%90%8D%E5%8D%95%E8%AE%BF%E9%97%AE)
  - [参数](#%E5%8F%82%E6%95%B0-19)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-19)
  - [返回](#%E8%BF%94%E5%9B%9E-19)
- [添加用户到白名单](#%E6%B7%BB%E5%8A%A0%E7%94%A8%E6%88%B7%E5%88%B0%E7%99%BD%E5%90%8D%E5%8D%95)
  - [参数](#%E5%8F%82%E6%95%B0-20)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-20)
  - [返回](#%E8%BF%94%E5%9B%9E-20)
- [获取课程白名单列表](#%E8%8E%B7%E5%8F%96%E8%AF%BE%E7%A8%8B%E7%99%BD%E5%90%8D%E5%8D%95%E5%88%97%E8%A1%A8)
  - [参数](#%E5%8F%82%E6%95%B0-21)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-21)
  - [返回](#%E8%BF%94%E5%9B%9E-21)
- [从白名单中移除用户](#%E4%BB%8E%E7%99%BD%E5%90%8D%E5%8D%95%E4%B8%AD%E7%A7%BB%E9%99%A4%E7%94%A8%E6%88%B7)
  - [参数](#%E5%8F%82%E6%95%B0-22)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-22)
  - [返回](#%E8%BF%94%E5%9B%9E-22)
- [播放页面](#%E6%92%AD%E6%94%BE%E9%A1%B5%E9%9D%A2)
  - [参数](#%E5%8F%82%E6%95%B0-23)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-23)
  - [返回](#%E8%BF%94%E5%9B%9E-23)
- [web直播页面](#web%E7%9B%B4%E6%92%AD%E9%A1%B5%E9%9D%A2)
  - [参数](#%E5%8F%82%E6%95%B0-24)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-24)
- [结束直播](#%E7%BB%93%E6%9D%9F%E7%9B%B4%E6%92%AD)
  - [参数](#%E5%8F%82%E6%95%B0-25)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-25)
  - [返回](#%E8%BF%94%E5%9B%9E-24)
- [文档-根据课程id获取课程所有文档信息](#%E6%96%87%E6%A1%A3-%E6%A0%B9%E6%8D%AE%E8%AF%BE%E7%A8%8Bid%E8%8E%B7%E5%8F%96%E8%AF%BE%E7%A8%8B%E6%89%80%E6%9C%89%E6%96%87%E6%A1%A3%E4%BF%A1%E6%81%AF)
  - [参数](#%E5%8F%82%E6%95%B0-26)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-26)
  - [返回](#%E8%BF%94%E5%9B%9E-25)
- [文档-根据文档id获取文档详细信息](#%E6%96%87%E6%A1%A3-%E6%A0%B9%E6%8D%AE%E6%96%87%E6%A1%A3id%E8%8E%B7%E5%8F%96%E6%96%87%E6%A1%A3%E8%AF%A6%E7%BB%86%E4%BF%A1%E6%81%AF)
  - [参数](#%E5%8F%82%E6%95%B0-27)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-27)
  - [返回](#%E8%BF%94%E5%9B%9E-26)
- [文档-设置当前文档为演示文档](#%E6%96%87%E6%A1%A3-%E8%AE%BE%E7%BD%AE%E5%BD%93%E5%89%8D%E6%96%87%E6%A1%A3%E4%B8%BA%E6%BC%94%E7%A4%BA%E6%96%87%E6%A1%A3)
  - [参数](#%E5%8F%82%E6%95%B0-28)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-28)
  - [返回](#%E8%BF%94%E5%9B%9E-27)
- [文档-设置当前文档当前所翻页数](#%E6%96%87%E6%A1%A3-%E8%AE%BE%E7%BD%AE%E5%BD%93%E5%89%8D%E6%96%87%E6%A1%A3%E5%BD%93%E5%89%8D%E6%89%80%E7%BF%BB%E9%A1%B5%E6%95%B0)
  - [参数](#%E5%8F%82%E6%95%B0-29)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-29)
  - [返回](#%E8%BF%94%E5%9B%9E-28)
- [会议系统--有因渠道方web端用户跳转播放](#%E4%BC%9A%E8%AE%AE%E7%B3%BB%E7%BB%9F--%E6%9C%89%E5%9B%A0%E6%B8%A0%E9%81%93%E6%96%B9web%E7%AB%AF%E7%94%A8%E6%88%B7%E8%B7%B3%E8%BD%AC%E6%92%AD%E6%94%BE)
  - [参数](#%E5%8F%82%E6%95%B0-30)
    - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-30)
  - [返回](#%E8%BF%94%E5%9B%9E-29)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## 访问地址

线上： [https://live.youinsh.com](https://live.youinsh.com/)

测试： [https://live.test.youinsh.cn](https://live.test.youinsh.cn/)



## 鉴权

```

POST /api/v1/system/auth-token/

```

### 参数

|名称|类型|是否必须|描述|

|----|----|----|----|

|app_id`|`string`|是|渠道商在youin的账户使用接口权限的appid|

|app_secret`|`string`|是|渠道商在youin账户使用接口权限的的密码|



#### 请求示例

```json

POST /api/v1/system/auth-token/

Content-Type: application/json



{
    "app_id": "",
    "app_secret": ""
}

```

### 返回

返回的结果是 jwt token, 解析出来会有一个过期时间，如果过期了，那么渠道商需要重新鉴权。

在后面的每次请求都需要带上这个 jwt token，放在 header 里面里面：

```
Authorization: jwt {{token}}
```

```json

{
    "code": 200,
    "msg": "success",
    "result": {
        "exprise_time": 1545485899,
        "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6IjFAMS5jb20iLCJleHAiOjE1NDU0ODU4OTksInVzZXJfaWQiOjkxLCJlbWFpbCI6IiJ9._0eD1FHGwPXY4VqYHRlRk4Kx8_768S1KhW-7XNUrd3c"
    }
}

```





## 上传文件获取oss临时sts上传token

```

GET /api/v1/system/ali_oss_auth/

```

### 参数

|名称|类型|是否必须|描述|

|----|----|----|----|




#### 请求示例

```json

GET /api/v1/system/ali_oss_auth/

Content-Type: application/json

Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx



```

### 返回

```json
{
    "code": 200,
    "msg": "ok",
    "result": {
        "AccessKeyId": "STS.NJeYpUL97HqAgUSjPYBVgqZh1",
        "AccessKeySecret": "HXyuPG7tDFfLucqzLLK4QFqk1Ksfe138YNCY5xMieSLJ",
        "SecurityToken": "CAISiQJ1q6Ft5B2yfSjIr4nQEsrhoeYW/7OqZXPijlAMTtlLnp/D0zz2IHxNfnVoBOoXsfk/nW5Q7/oflr90UIQAXV3Ybcx2q49b8kasc4PEo8i4tQ7VRiI2XTr9MQXy+eOPScebJYqvV5XAQlTAkTAJstmeXD6+XlujHISUgJp8FLo+VRW5ajw0b7U/ZHEVyqkgOGDWKOymPzPzn2PUFzAIgAdnjn5l4qnNqa/1qDim1QClkrJM+Nuqf8H+MJA1bK0SCYnlgLZEEYPayzNV5hRw86N7sbdJ4z+vvKvGXwALv03babuLr402clcgOvUgZ6dArenhk+ZkoeDemY3qzwpXOuVYQ4JH8FVCJEauGoABE1S4DworAoAwhHFRrYAOo8/woePUCjQHgaek0CryRCgWWoY+z1dj963aQKNiMjata1CK+Py+7kp5tgpAnK68+LShPCo8vCh/n2zrrpkh2V/tf+MdnwcMncDWAA8qC3/wp7hBNocju9gVrxqTYX8RGMLmCNyknDlXpIyOUZbjkik=",
        "Expiration": "2018-12-17T06:45:31Z"
    }
}
```

### 错误

- 400 参数错误

- 404 用户没有找到

- 500 服务内部错误


## 获取上传视频到oss到路径

```

GET /api/v1/system/access_bucket/

```

### 参数

|名称|类型|是否必须|描述|

|----|----|----|----|




#### 请求示例

```json
当新建录播，需要用户本地上传视频文件到oss，
调用接口获取oss的临时token后上传

bucket_path：文件上传到oss到路径
上传完成之后oss会返回上传成功之后保存在oss中到文件名
使用path+文件名组成参数，带入新建录播中的video_record

GET /api/v1/system/access_bucket/

Content-Type: application/json

Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx



```

### 返回

```json
{
    "msg": "success",
    "result": {
        "bucket_path": "youinsh-staging/staging/record/34_3dee4fb009ad11e98f3300163e0097a6/",
        "path": "staging/record/34_3dee4fb009ad11e98f3300163e0097a6/"
    },
    "code": 200
}
```

### 错误

- 400 参数错误

- 404 用户没有找到

- 500 服务内部错误



## 创建分类
```
POST /api/v1/categories/create/
```

### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`category_name`|`string`|是|分类名称|
|`type`|`string`|是|1为普通分类  2为密码分类|
|`password`|`string`|否|当type=2，需填密码|


#### 请求示例
```json
POST /api/v1/categories/create/
Content-Type: application/json
Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

{
    "category_name": "test",
    "type": 1,
    "password": ""
}
```
### 返回
```json
HTTP CODE 200
{
    "msg": "success",
    "result": {},
    "code": 200
}
```
### 错误
- 10014 权限错误
- 10110 参数错误
- 500 内部错误
- 404 not found


## 获取分类列表
```
GET /api/v1/categories/list/?page=xx&size=xx
```

### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`page`|`int`|否|请求的当前页数，默认第一页|
|`size`|`int`|否|每页显示的数据条数，默认15条最大|


#### 请求示例
```json
GET /api/v1/categories/list/?page=xx&size=xx
Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```
### 返回
```json
HTTP CODE 200
{
    "previous": null,
    "result": [
        {
            "id": 758,
            "name": "test",
            "type": 1,
            "active": "上线",
            "is_fixed": "自定义分类",
            "create_time": "2018-12-07T14:37:18",
            "sort_no": 2
        },
        {
            "id": 759,
            "name": "123",
            "type": 1,
            "active": "上线",
            "is_fixed": "自定义分类",
            "create_time": "2018-12-19T15:21:44",
            "sort_no": 1
        }
    ],
    "code": 200,
    "count": 2,
    "msg": "success",
    "next": null
}
```

## 分类---删除-上线-下线
```
POST /api/v1/categories/delete/{{id}}/
```

### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`id`|`int`|是|分类id|
|`type`|`int`|是|1:上线  2:下线 3:删除|


#### 请求示例
```json
POST /api/v1/categories/delete/{{id}}/
Content-Type: application/json
Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

{"type":2}
```
### 返回
```json
HTTP CODE 200
{
    "msg": "success",
    "result": {},
    "code": 200
}
```
### 错误
- 10014 权限错误
- 10116 固定分类不可操作
- 10110 参数错误
- 400 调用失败
- 500 内部错误
- 404 not found


## 分类-修改
```
POST /api/v1/categories/update/{{id}}/
```

### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`id`|`int`|是|分类id|
|`category_name`|`int`|是|分类名称|
|`type`|`string`|是|1为普通分类  2为密码分类|
|`password`|`string`|否|当type=2，需填密码|


#### 请求示例
```json
POST /api/v1/categories/update/{{id}}/
Content-Type: application/json
Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

{
    "category_name": "name",
    "type": 1,
    "password": ""
}
```
### 返回
```json
HTTP CODE 200
{
    "msg": "success",
    "code": 200,
    "result": {}
}
```
### 错误
- 10014 权限错误
- 10116 固定分类不可操作
- 10110 参数错误
- 400 调用失败
- 500 内部错误
- 404 not found


## 分类-置顶
```
POST /api/v1/categories/setweight/{{id}}/
```

### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`id`|`int`|是|分类id|


#### 请求示例
```json
POST /api/v1/categories/setweight/{{id}}/
Content-Type: application/json
Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx


```
### 返回
```json
HTTP CODE 200
{
    "msg": "success",
    "code": 200,
    "result": {}
}
```
### 错误
- 10014 权限错误
- 10116 固定分类不可操作
- 10110 参数错误
- 400 调用失败
- 500 内部错误
- 404 not found



## 直播-创建
```
POST /api/v1/course/live/create/
此接口参数必须以form表单格式提交
```

### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`title`|`string`|是|直播的标题|
|`image`|`file`|是|直播封面图片|
|`start_time`|`string`|是|开始时间 格式：Y-m-d H:M|
|`description`|`string`|是|简介|
|`live_course`|`string`|是|固定为：live_course|
|`password`|`string`|否|设置课程密码|
|`browse_dummy_count`|`string`|否|初始浏览量|
|`profile_star_name`|`string`|否|讲师姓名|
|`signature`|`string`|否|讲师签名|
|`star_description_self`|`string`|否|讲师简介|
|`category_id`|`string`|否|分类的id|

#### 请求示例
```json
此接口提交数据需要使用form表单提交
所有参数默认type为string
image参数为上传的文件
可选参数可以为空或者不带入
若包含自定义讲师，则profile_star_name，signature，star_description_self三个参数都为必填，否则都不需要

POST /api/v1/course/live/create/
Content-Type: multipart/form-data
Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx


```
### 返回
```json
HTTP CODE 200
{
    "msg": "success",
    "code": 200,
    "result": {
        "course_id": 1622,   #返回创建完成的课程id
        "enterprise_id":216
    }
}
```
### 错误
- 10014 权限错误
- 10116 固定分类不可操作
- 10110 参数错误
- 400 调用失败
- 500 内部错误
- 404 not found


## 录播-创建
```
POST api/v1/course/live/create/
此接口参数必须以form表单格式提交
```

### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`title`|`string`|是|直播的标题|
|`image`|`file`|是|直播封面图片|
|`video_record`|`string`|是|视频上传到oss到路径|
|`description`|`string`|是|简介|
|`live_course`|`string`|是|固定为：replay_course|
|`password`|`string`|否|设置课程密码|
|`browse_dummy_count`|`string`|否|初始浏览量|
|`profile_star_name`|`string`|否|讲师姓名|
|`signature`|`string`|否|讲师签名|
|`star_description_self`|`string`|否|讲师简介|
|`category_id`|`string`|否|分类的id|

#### 请求示例
```json
此接口提交数据需要使用form表单提交
所有参数默认type为string
image参数为上传的文件
可选参数可以为空或者不带入
若包含自定义讲师，则profile_star_name，signature，star_description_self三个参数都为必填，否则都不需要
文件上传到oss
通过接口获取访问oss的sts签名，
通过接口获取上传视频的路径

获取到了路径path+上传后到文件名此目录即为video_record的参数，doc_doc_url同理

POST /api/v1/course/live/create/
Content-Type: application/x-www-form-urlencoded
Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx


```
### 返回
```json
HTTP CODE 200
{
    "msg": "success",
    "code": 200,
    "result": {
        "course_id": 1622   #返回创建完成的课程id
    }
}
```
### 错误
- 10014 权限错误
- 10116 固定分类不可操作
- 10110 参数错误
- 400 调用失败
- 500 内部错误
- 404 not found


## 直播/录播-删除
```
POST /api/v1/course/live/delete/{{id}}/
```

### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`id`|`int`|是|分类id|



#### 请求示例
```json
POST /api/v1/course/live/delete/{{id}}/
Content-Type: application/json
Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```
### 返回
```json
HTTP CODE 200
{
    "msg": "success",
    "code": 200,
    "result": {}
}
```
### 错误
- 10014 权限错误
- 10116 固定分类不可操作
- 10110 参数错误
- 400 调用失败
- 500 内部错误
- 404 not found



## 直播/录播-查看直播/录播课程详情

```

GET /api/v1/course/live/details/{{id}}/

```

### 参数

|名称|类型|是否必须|描述|

|----|----|----|----|
|`id`|`int`|是|分类id|



#### 请求示例

```json

GET /api/v1/course/live/details/{{id}}/

Content-Type: application/json

Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx



```

### 返回

```json
{
    "msg": "success",
    "result": {
        "id": 7132,     //课程id
        "video_id": "61ca28985f2311e9864500163e04c8e0", //课程video_id 
        "category": {       //所属的分类信息
            "id": 2868,
            "name": "分类1",
            "type": 1,
            "active": "上线",
            "is_fixed": "自定义分类",
            "create_time": "2018-12-21T17:20:19",
            "sort_no": 1
        },
        "type": 1,      //直播的类型 1:直播，2:录播，3:系列课，4:独立音频，5:导播直播
        "status": 9,    //直播状态：1=直播,2=预订,3=直播结束,4=录播，9主播不再
        "title": "test",//直播的标题
        "start_time": "2019-04-17T17:48:03",//直播开始时间，当开始时间已经在当前时间之前，则此参数不可更改
        "image": "https://youinsh-production.oss-cn-shanghai.aliyuncs.com/offical_website/img/zhibofengmian/3.jpg",//直播封面图
        "start_no": [//直播当前状态
            "主播不在",
            5
        ],
        "money": "0.00",//课程价格
        "bought": true,//是否已经报名
        "introduce_page": false,
        "description": "<p>12</p>",//介绍
        "password": null,//课程密码
        "url": null,//当视频为录播，此地址为录播播放地址
        "video_name": null,//当视频为录播，录播的视频文件名
        "record_url": "p/record/678_61ca28985f2311e9864500163e04c8e0/",//当视频为录播，上传录播视频的路径
        "browse_dummy_count": 1,//初始浏览量
        "support": 0,
        "sign_num": 0,//初始报名人数
        "sign_up_num": 1,//实际报名人数
        "show_sign_up_num": 1,//显示在前端的报名人数
        "doc_name": null,//文档名称
        "enterprise": {//当前企业信息
            "id": 678,
            "phone": "17521028236",
            "contacts": "张军",
            "email": "",
            "addr": "",
            "org_name": "张某某",
            "org_intro": "",
            "sign": "",
            "logo": "https://cdn.youinsh.cn/p/enterprise_logo/enterprise_logo/01b2d4f58e91cd8b6ab3bb3148c101e9.png",
            "status": 2,
            "is_local": false,
            "create_time": "2018-11-21T10:13:14",
            "is_active": true,
            "calculator_pattern": "on_flow",
            "background_image": null,
            "phone_background_image": null,
            "short_name": "",
            "QR_code": "https://cdn.youinsh.cn/p/enterprise_QR_code/enterprise_QR_code/d59bcbdd287d60c19279cdae4621e23b.jpeg",
            "backend_logo": "https://cdn.youinsh.cn/p/enterprise_backend_logo/enterprise_backend_logo/c72a82d984d0a0bfbb4d536c582acbd2.png"
        },
        "course_status": {
            "status": 9,
            "detail": "主播不在"
        },
        "chat_room_id": "5cb4185dc8959c00701cfffd",//聊天roomid
        "course_star": null,//讲师
        "create_time": "2019-04-15T10:08:38",//创建时间
        "chatroom_audit": "close",//聊天室管控是否开启
        "audio": "",
        "audio_url": null
    },
    "code": 200
}
```

### 错误

- 400 参数错误

- 404 用户没有找到

- 500 服务内部错误



## 直播/录播-修改直播/录播信息

```

POST /api/v1/course/live/update/{{id}}/

```

### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`title`|`string`|否|直播的标题|
|`image`|`file`|否|直播封面图片|
|`description`|`string`|否|简介|
|`password`|`string`|否|设置课程密码|
|`start_time`|`string`|否|开始时间|
|`browse_dummy_count`|`string`|否|初始浏览量|
|`profile_star_name`|`string`|否|讲师姓名|
|`signature`|`string`|否|讲师签名|
|`star_description_self`|`string`|否|讲师简介|
|`category_id`|`string`|否|分类的id|
|`category_name`|`string`|否|分类标题,|


#### 请求示例

```json

POST /api/v1/course/live/update/{{id}}/

Content-Type: multipart/form-data

所有参数需要更新的字段则带入，不需要更新的字段不要带入
当修改讲师profile_star_name、signature、star_description_self此3参数都得带入
当修改分类category_id、category_name必须都带入

```

### 返回

返回的结果是 jwt token, 解析出来会有一个过期时间，如果过期了，那么渠道商需要重新鉴权。

在后面的每次请求都需要带上这个 jwt token，放在 header 里面里面：

```
Authorization: jwt {{token}}
Content-Type: multipart/form-data
```

```json

{
    "msg": "success",
    "code": 200,
    "result": {}
}

```



## 直播--获取存在的直播列表

```
GET /api/v1/course/live/list/?page=xx&size=xx

```

### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|`page`|`int`|否|当前页数|
|`size`|`int`|否|每页显示的条数|



#### 请求示例

```json

GET /api/v1/course/live/list/?page=xx&size=xx

Content-Type: application/json

Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

### 返回

```json
{
    "result": [
        {
            "id": 7132,     //课程id
            "title": "test",//课程标题
            "start_time": "2019-04-17T17:48:03",//开始时间
            "course_status": {  //直播状态
                "next_url": "https://live.youinsh.com/course/live_room/7132/?enterprise_id=678",//进入直播或者生成录播地址（此地址访问需要头部信息带入Authorization）
                "item": "去直播",//此直播可以进入直播还是生成录播
                "status": 9//直播状态码
            },
            "image": "https://youinsh-production.oss-cn-shanghai.aliyuncs.com/offical_website/img/zhibofengmian/3.jpg",//封面图片
            "create_time": "2019-04-15T10:08:38",//创建时间
            "watch_url": "https://live.youinsh.com/course/details/?id=7132&enterprise_id=678",//观看地址
            "orders_num": 1//报名观看人数
        },
        {
            "id": 7068,
            "title": "2ED12D21D",
            "start_time": "2019-04-18T10:55:00",
            "course_status": {
                "next_url": "https://live.youinsh.com/course/live_room/7068/?enterprise_id=678",
                "item": "去直播",
                "status": 2
            },
            "image": "https://youinsh-production.oss-cn-shanghai.aliyuncs.com/offical_website/img/zhibofengmian/3.jpg",
            "create_time": "2019-04-10T18:27:17",
            "watch_url": "https://live.youinsh.com/course/details/?id=7068&enterprise_id=678",
            "orders_num": 0
        },
       
    ],
    "msg": "success",
    "count": 27,//总共查询的条数
    "next": "https://live.youinsh.com/api/v1/course/live/list/?page=2&size=10",//下一页请求地址
    "previous": null,//上一页请求地址
    "code": 200
}
```

### 错误

- 400 参数错误

- 404 用户没有找到

- 500 服务内部错误




## 录播--获取录播列表

```
GET /api/v1/course/replay/list/?page=xx&size=xx
```
### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|`page`|`int`|否|当前页数|
|`size`|`int`|否|每页显示的条数|



#### 请求示例

```json

GET /api/v1/course/replay/list/?page=xx&size=xx

Content-Type: application/json

Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

### 返回

```json
{
    "previous": null,//上一页地址
    "count": 20,//总数据条数
    "next": "http://127.0.0.1:8000/api/v1/course/replay/list/?page=2&size=2",//下一页地址
    "result": [
        {
            "id": 1570,//录播课程id
            "title": "ttttttttt",//课程名
            "start_time": "2018-12-07T09:40:32",//开始时间
            "image": "https://stagingcdn.youinsh.cn/staging/courses/039dce54f9c111e8ab51881fa100a65e/b8f3c0c9c728b5d967b7ccc8746b4270_thumbnail.jpeg",//封面图
            "create_time": "2018-12-07T09:45:33",//创建时间
            "watch_url": "http://localhost:8000/course/details/?id=1570&enterprise_id=34",//观看地址
            "orders_num": 0//报名人数
        },
        {
            "id": 1560,
            "title": "标题1",
            "start_time": "2018-12-22T00:00:00",
            "image": "https://stagingcdn.youinsh.cn/staging/courses/6e35fae6e32011e88f3300163e0097a6/7275589a7337f9ff24daa966e772c610_thumbnail.jpeg",
            "create_time": "2018-11-08T14:35:24",
            "watch_url": "http://localhost:8000/course/details/?id=1560&enterprise_id=34",
            "orders_num": 0
        }
    ],
    "msg": "success",
    "code": 200
}
```

### 错误

- 400 参数错误

- 404 用户没有找到

- 500 服务内部错误




## 直播/录播--获取推流地址、密钥，播放的视频地址

```
GET /api/v1/course/stream_url/{{id}}/
```

### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|`id`|`int`|是|课程id|

#### 请求示例

```json
GET /api/v1/course/stream_url/{{id}}/

Content-Type: application/json

Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

### 返回

```json
{
    "result": {
        "aliyun_channel": {
            "cdn_domain": "video-center.alivecdn.com",//obs推流域名
            "app_name": "enterprise210third",//obs推流app名称
            "publish_url": "rtmp://video-center.alivecdn.com/enterprise210third/15476190290411458enterprise210third?vhost=youinstaginglive.youinsh.cn&auth_key=1556002870-0-0-2949a702a091ba442bd93c8ee5999b24",//obs推流地址
            "stream_name": "15476190290411458enterprise210third?vhost=youinstaginglive.youinsh.cn&auth_key=1556002870-0-0-2949a702a091ba442bd93c8ee5999b24"//obs推流密钥
        },
        "channel_url": {
            "publish_url": "rtmp://pili-publish.live.qiniutest.youinsh.cn/youin-staging/15476189419402735_210_1718/",
            "url_rtmp": "rtmp://pili-live-rtmp.live.qiniutest.youinsh.cn/youin-staging/15476189419402735_210_1718",//rmtp播放地址
            "status": "live_over",//课程状态
            "url_hls": "https://pili-live-hls.live.qiniutest.youinsh.cn/youin-staging/15476189419402735_210_1718.m3u8",//hls播放地址
            "pulish_url": "",
            "url_flv": "https://pili-live-hdl.live.qiniutest.youinsh.cn/youin-staging/15476189419402735_210_1718.flv",//flv播放地址
            "live_channel_id": 2419
        },
        "web_channel": {
            "cdn_domain": "streamvod.youinsh.cn",//web推流域名
            "app_name": "youinsh_live_test",//web推流app名
            "publish_url": "rtmp://streamvod.youinsh.cn/youinsh_live_test/3396e57e195511e9a5ad00163e0035bf?vhost=youinstaginglive.youinsh.cn&auth_key=1556002870-0-0-042c7882ee9ac020b2c3692031cfbfd8",//web推流地址
            "stream_name": "3396e57e195511e9a5ad00163e0035bf?vhost=youinstaginglive.youinsh.cn&auth_key=1556002870-0-0-042c7882ee9ac020b2c3692031cfbfd8"//web推流密钥
        }
    },
    "code": 200,
    "msg": "success"
}
```

### 错误

- 400 参数错误

- 404 用户没有找到

- 500 服务内部错误


## 直播--转成录播

```
POST /api/v1/course/recourd_video/{{id}}/

```

### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`id`|`int`|是|课程id|


#### 请求示例

```json
POST /api/v1/course/recourd_video/{{id}}/

Content-Type: application/json
Authorization: jwt {{token}}
```

### 返回

```json
{
    "code": 200,
    "msg": "success",
    "result": {
    }
}

```


## 用户--注册用户

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


## 用户--修改用户信息

```
POST /api/v1/user/edituserinfo/{{id}}/

```

### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`username`|`string`|是|用户昵称|
|`image`|`string`|是|头像|
|`id`|`int`|是|渠道方系统用户id|


#### 请求示例

```json
POST /api/v1/user/edituserinfo/{{id}}/

Content-Type: application/json
Authorization: jwt {{token}}
{
    "username":"xxx",
    "image":"xxx",
}
```

### 返回

```json
{
    "code": 200,
    "msg": "success",
    "result": {
    }
}

```



## 课程--开启白名单访问

```
POST /api/v1/user/white_list_set/

```

### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`relation_id`|`string`|是|课程id|
|`type_select`|`string`|是|关闭白名单:close_list,开启白名单:white|
|`level`|`string`|否|固定为：course|


#### 请求示例

```json
POST /api/v1/user/white_list_set/

Content-Type: application/json
Authorization: jwt {{token}}
{
    "relation_id":"xxx",
    "type_select":"white",
}
```

### 返回

```json
{
    "code": 200,
    "msg": "success",
    "result": {
    }
}

```


## 添加用户到白名单
```
POST /api/v1/user/add_white_user/
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`level`|`string`|否|固定为：course|
|`relation_id`|`string`|是|课程id|
|`user_id`|`list`|是|有因系统用户id列表: ["23","212"]|


#### 请求示例
```json
POST /api/v1/user/add_white_user/
Content-Type: application/json

{
    "level": "course",
    "relation_id": "1735",
    "user_id": ["408","457"]
}
```
### 返回
```json
{
    "code": 200,
    "msg": "success",
    "result": {}
}
```


## 获取课程白名单列表
```
GET /api/v1/user/list_white_user/{{id}}/?page=1&size=10
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`id`|`int`|是|课程id|
|`page`|`int`|否|当前页|
|`size`|`int`|否|每页显示条数|

#### 请求示例
```json
GET /api/v1/user/list_white_user/{{id}}/
Content-Type: application/json
Authorization:jwt {{token}}

```
### 返回
```json
{
    "next": null,   //下一页地址
    "count": 3,     //总数据条数
    "code": 200,
    "msg": "success",
    "result": [
        {
            "id": 103,    //黑名单ID
            "user_name": "智强企业",    //用户名/昵称
            "relation_id": 1735,      //直播课程id
            "user_id": 91,            //用户ID
            "create_date": "2019-03-12T15:28:01.678472",    //创建时间
            "update_date": "2019-03-12T15:28:01.699027",    //更新时间
            "active": "active"      //是否生效
        },
        {
            "id": 105,
            "user_name": "adam",
            "relation_id": 1735,
            "user_id": 415,
            "create_date": "2019-03-12T16:08:30.362885",
            "update_date": "2019-03-12T16:08:30.368851",
            "active": "active"
        }
    ],
    "previous": null      //上一页
}
```



## 从白名单中移除用户
```
POST /api/v1/user/cancel_white_user/
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`black_white_id`|`list`|是|有因系统用户id列表（int）: [1，2，3，4]|


#### 请求示例
```json
POST /api/v1/user/cancel_white_user/
Content-Type: application/json

{	
	"black_white_id": [10,11,12,13,14,15]
}
```
### 返回
```json
{
    "code": 200,
    "msg": "success",
    "result": {}
}
```



## 播放页面
```
GET /api/v1/user/play_from_channel/?user_id=xx&auth_token=xx&next=/course/details/?id=xx&enterprise_id=xx
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`user_id`|`int`|是|渠道平台用户的ID，此用户必须通过平台已经在有因注册|
|`auth_token`|`string`|是|自定义验证密钥|
|`id`|`int`|是|课程id|
|`enterprise_id`|`int`|否|创建课程返回的enterprise_id|


#### 请求示例
get重定向到观看页面
### 返回
```
嵌入网页播放页面
```



## web直播页面
```
GET /api/v1/course/stream_way/?enterprise_id=xx&course_id=xx&auth_token=xxx
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`course_id`|`int`|是|直播的课程id|
|`enterprise_id`|`int`|是|必填参数，创建直播返回的直播的企业id|
|`auth_token`|`string`|是|鉴权token|

header中必须带入Authorization，此token为appid和appsecret获取到的token
#### 请求示例
```json
GET /api/v1/course/stream_way/?enterprise_id=xx&course_id=xx
Content-Type: application/json
Authorization:jwt {{token}}

```



## 结束直播
```
POST /api/v1/course/stop_live/
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`option`|`string`|是|固定为'forbidden'|
|`course_id`|`int`|是|课程id|


#### 请求示例
```json
POST /api/v1/course/stop_live/
Content-Type: application/json
Authorization:jwt {{token}}

{	
	"option":"forbidden",
    "course_id":xxx
}
```
### 返回
```json
{
    "code": 200,
    "msg": "success",
    "result": {}
}
```


## 文档-根据课程id获取课程所有文档信息
```
GET /api/v1/course/doc_file/{{id}}/?page=xx&size=xx
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`id`|`int`|是|课程id|
|`page`|`int`|否|当前页|
|`size`|`int`|否|每页显示条数|

#### 请求示例
```json
GET /api/v1/course/doc_file/{{id}}/?page=xx&size=xx
Content-Type: application/json
Authorization:jwt {{token}}

```
### 返回
```json
{
    "count": 2,
    "next": null,
    "code": 200,
    "result": [
        {
            "id": 226,      //文档id
            "video_id": "d98f8d10156711e98f3300163e0097a6", //所对应课程的video_id
            "doc_name": "[\"有因直播综合版 .pdf\"]",//文档名称
            "doc_converter_length": 25, //文档的页数
            "status": "disposed",   //是否已经被处理成图片
            "type": "pdf",          //文档格式
            "create_time": "2019-01-11T14:42:43",   //创建时间
            "last_page": 12,        //主持人翻页最后一次所在页
            "in_use": false         //该文档是否正被演示
        },
        {
            "id": 225,
            "video_id": "d98f8d10156711e98f3300163e0097a6",
            "doc_name": "[\"21世纪商业评论 2018年第9期.pdf\"]",
            "doc_converter_length": null,
            "status": "not_dispose",
            "type": "pdf",
            "create_time": "2018-12-10T11:05:26",
            "last_page": 1,
            "in_use": true
        }
    ],
    "msg": "success",
    "previous": null
}
```


## 文档-根据文档id获取文档详细信息
```
GET /api/v1/course/doc_detail/{{id}}/
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`id`|`int`|是|文档id|

#### 请求示例
```json
GET /api/v1/course/doc_detail/{{id}}/
Content-Type: application/json
Authorization:jwt {{token}}

```
### 返回
```json
{
    "msg": "success",
    "result": {
        "id": 226,//文档id
        "video_id": "d98f8d10156711e98f3300163e0097a6",//课程video_id
        "doc_path": "staging/doc/courses/d98f8d10156711e98f3300163e0097a6/pdf_file",//文档oss路径
        "doc_name": "[\"有因直播综合版 .pdf\"]",//文档名
        "doc_control_path": null,
        "doc_converter_length": 2,//文档页数
        "status": "disposed",       //是否被处理转换
        "type": "pdf",              //类型
        "create_time": "2019-01-11T14:42:43",//创建时间
        "image_path": [//图片地址
            "https://stagingcdn.youinsh.cn/staging/doc/courses/d98f8d10156711e98f3300163e0097a6/pdf_file/pdf_image/有因直播综合版 -0.png",
            "https://stagingcdn.youinsh.cn/staging/doc/courses/d98f8d10156711e98f3300163e0097a6/pdf_file/pdf_image/有因直播综合版 -1.png"
        ],
        "incomplete_url": [//oss地址
            "staging/doc/courses/d98f8d10156711e98f3300163e0097a6/pdf_file/pdf_image/有因直播综合版 -0.png",
            "staging/doc/courses/d98f8d10156711e98f3300163e0097a6/pdf_file/pdf_image/有因直播综合版 -1.png"
        ],
        "last_page": 12,//最后所在页数
        "in_use": false//文档是否被演示
    },
    "code": 200
}
```


## 文档-设置当前文档为演示文档
```
POST /api/v1/course/set_doc_index/{{id}}/
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`id`|`int`|是|文档id|


#### 请求示例
```json
POST /api/v1/course/set_doc_index/{{id}}/
Content-Type: application/json
Authorization:jwt {{token}}

```
### 返回
```json
{
    "code": 200,
    "msg": "success",
    "result": {}
}
```


## 文档-设置当前文档当前所翻页数
```
POST /api/v1/course/index_doc/{{id}}/
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`id`|`int`|是|文档id|
|`index_page`|`int`|是|所翻页数|

#### 请求示例
```json
POST /api/v1/course/index_doc/{{id}}/
Content-Type: application/json
Authorization:jwt {{token}}
{
    "index_page":12
}
```
### 返回
```json
{
    "code": 200,
    "msg": "success",
    "result": {}
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


## 访问地址

线上访问地址: 

测试访问地址: https://live.test.youinsh.cn





## 会议系统--有因渠道方web端用户跳转播放
```
GET /api/v1/user/reg_from_channel/?user_id=xx&auth_token=xx&next=xx
```

```
浏览器直接get此地址

user_id:纳爱斯系统用户id
auth_token:当天时间+registuser+user_id组合起来md5加密
        如今天是2019年11月21日，用户ID为100则字符串为 20191121registuser100
next：跳转地址，
如果是邀请参加一起互动则参数为：
/course/webRTCUser/?id=xx&enterprise_id=xx
如果邀请进入观看直播：
/course/details/?id=xx&enterprise_id=xx
其中id为当前直播的id，enterprise_id为企业id，这个id是固定的

```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`user_id`|`int`|是|渠道平台用户的ID|
|`auth_token`|`string`|是|自定义验证密钥：密钥格式请联系有因技术客服|
|`id`|`int`|是|课程id|
|`enterprise_id`|`int`|否|创建课程返回的enterprise_id|


#### 请求示例
get重定向到观看页面直接跳转到直播页面，且用户与纳爱斯关联
### 返回
```
嵌入网页播放页面
```


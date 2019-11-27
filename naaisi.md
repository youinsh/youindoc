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




## 直播数据统计
```
GET /api/v1/analysis/nicesys/watch_detail/{{id}}/?page=xx&size=xx
```
### 参数
|名称|类型|是否必须|描述|
|----|----|----|----|
|`id`|`int`|是|直播课程id|
|`page`|`int`|是|当前页数|
|`size`|`int`|是|每页显示数据条数|


#### 请求示例

### 返回
```
{
    "code": 200,
    "result": {
        "watch_records": [
            {
                "youin_user_id": 386,//有因用户id
                "nice_user_id": null,//纳爱斯用户id
                "last_login": "2019-10-28T14:51:09",//最后登录时间
                "view_count": 15,//观看此课程次数
                "total_view_time": "78.91",//总观看时间
                "avg_duration": "5.260666666666666666666666667",//平均观看时间
                "ip": "223.166.93.99",//ip地址
                "region": "上海",//地区
                "endDate": "2019-04-30T15:17:16",//最后观看时间
                "view_status_type": "仅看直播"//观看类型
            },
            {
                "youin_user_id": 425,
                "nice_user_id": null,
                "last_login": "2019-07-03T17:55:34",
                "view_count": 6,
                "total_view_time": "50.25",
                "avg_duration": "8.375",
                "ip": "223.166.93.99",
                "region": "上海",
                "endDate": "2019-04-29T17:33:15",
                "view_status_type": "仅看直播"
            }
        ],
        "total_apply_count": 2,//总报名人数
        "title": "122112",//课程名称
        "total_real_people": 2,//观看直播人数
        "watch_real_count": 21,//总观看次数
        "browse_real_count": 9//总浏览次数
    },
    "previous": null,
    "count": 2,
    "next": null,
    "msg": "success"
}
```



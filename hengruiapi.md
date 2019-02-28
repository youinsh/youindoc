## 访问地址
线上： https://live.youinsh.com
测试： https://live.test.youinsh.cn


```

## 获取课程观看数据的详情
```
GET /api/v1/analysis/course_watch_detail/{{course_id}}/
```

### 参数


#### 请求示例
```json
GET /api/v1/analysis/course_watch_detail/{{course_id}}/
```
### 返回
```json
HTTP CODE 200
{
    "count": 1,   #一共有多少页
    "next": null, #下一页地址
    "code": 200,  #返回的状态码
    "result": {
        "watch_records": [
            {
                "user_id": 386,   #观看的用户id
                "user_name": "jjjjjjjlk",   #观看的用户昵称
                "tel": "",        #观看用户的手机号码
                "regist_data": "2018-11-01T16:15:48",   #用户注册平台时间
                "last_login": "2019-02-28T11:24:06",    #截止当前时间用户最后一次登陆时间
                "view_count": 3,    #此用户总共观看此课程的次数
                "total_view_time": "25.20",    #用户观看此课程的总时间(秒)
                "avg_duration": "8.40",   #用户平均观看课程是时间（秒）
                "ip": "223.166.94.224",   #用户ip地址
                "region": "上海",   #用户的区域
                "endDate": "2019-01-11T13:20:50"    #用户最后一次观看课程的时间
            }
        ],
        "course_title": "wkejnfjkwenfkj", #课程标题
        "browse_real_count": 21,      #课程被浏览的总次数
        "watch_real_count": 3,        #课程的观看次数
        "total_real_people": 1,       #课程观看人数
        "total_apply_count": 1        ##课程的报名人数
    },
    "msg": "success",   #返回的信息提示
    "previous": null     #上一页的地址
}
```

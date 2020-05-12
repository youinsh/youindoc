## 问卷---平南，点击为某个直播创建/修改问卷
```
GET  /api/v1/questionnaires/pn/create_question/{{id}}/?auth={{auth}}
```
### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|id|`str`|是|直播id|
|auth|`str`|是|秘钥|

### 说明
```
auth鉴权
规则：年月日+createquestion+直播id  字符串md5加密
如：20200509createquestion377
```


## 问卷---有因，点击创建问卷
```
POST  /questionnaires/questionnaires/
```
### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|

### 说明
根据现有接口逻辑，从url获取course_id参数，当获取到之后，添加owners参数，
owners参数为数组，里面存放一个course_id即可

```

#### 请求示例
```json
POST  /questionnaires/questionnaires/

Content-Type: application/json
{
    "title": "test7",
    "description": "test7",
    "owner_user_id": 259,
    "category_id": 12,
    "active": "inactive",
    "answer_type": "one",
    "enterprise_id": "5",
    "owners":[377]
}
```
### 返回
```json
{
    "id": 65,
    "title": "test7",
    "description": "test7",
    "category": {
        "id": 12,
        "name": "教学测验",
        "description": null,
        "parent": 11,
        "root": {
            "parent": null,
            "name": "考试",
            "id": 11,
            "image_url": "",
            "enterprise": null,
            "type": "exam",
            "description": null
        },
        "image_url": "https://stagingcdn.youinsh.cn/staging/static/questionnaire/images/teaching_test.png",
        "type": "exam"
    },
    "owner_user": 259,
    "startDate": null,
    "endDate": null,
    "expire": null,
    "createDate": "2020-05-11T15:55:09.049654",
    "updateDate": "2020-05-11T15:55:09.049840",
    "active": "inactive",
    "enterprise": "5",
    "score": 0,
    "owners": [
        377
    ],
    "share_qrcode_url": ""
}
```


## 问卷---有因，创建题目，加入图片题目
```
POST  /questionnaires/questions/create_question/
```
### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|

### 说明
上传图片到平南oss，成功后获取图片url
当为图片题目，增加一个参数，"image_que"
默认如果不带入此参数，则为0，当图片题目，参数值为1
```

#### 请求示例
```json
POST  /questionnaires/questions/create_question/

Content-Type: application/json
{
    "sort_no": 2,
    "score": 5,
    "options": [
        {
            "content": "a",
            "sort_no": 1,
            "is_correct": true
        },
        {
            "content": "b",
            "sort_no": 2,
            "is_correct": false
        }
    ],
    "question_text": "图片地址",
    "question_type": "single",
    "questionnaire_id": 61,
    "image_que":1
}
```
### 返回
```json
{
    "id": 234,
    "question_type": "single",
    "question_text": "图片地址",
    "description": null,
    "questionnaire": 61,
    "sort_no": 2,
    "required": false,
    "score": 5,
    "english_text": null,
    "options": [
        {
            "id": null,
            "question": 234,
            "content": "a",
            "description": "",
            "is_correct": true,
            "sort_no": 1
        },
        {
            "id": null,
            "question": 234,
            "content": "b",
            "description": "",
            "is_correct": false,
            "sort_no": 2
        }
    ]
}
```
### 编辑完成后，点击提交，调用接口/questionnaires/questionnaires/{{id}}/set_questionnaire_data/成功后返回/questionnaire/examination_show/{{id}}/?enterprise_id=xx










## 回放下载---平南-获取回放下载地址
```
GET  /api/v1/course/record_file_url/{{id}}/
```
### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|id|`str`|是|直播id|

### 返回
```json
{
    "msg": "success",
    "result": {
        "record_url": "https://video.pingnanlearning.com:13000/jingan-jing-e-xue/youin/enterprise5third1588908960.mp4?OSSAccessKeyId=rnRoKW9l6xZJU9w4&Expires=1589269577&Signature=A7UhyZebxAgTrewvIiDfavEQqRI%3D"
    },
    "code": 200
}
```


## 回放---平南-重新上传回放视频
```
POST  /api/v1/course/record_file_url/{{id}}/
```
### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|id|`str`|是|直播id|


#### 请求示例
```json
POST  /api/v1/course/record_file_url/{{id}}/

Content-Type: application/json
{
    "record_url": "https://video.pingnanlearning.com:13000/jingan-jing-e-xue/youin/enterprise5third1588908960.mp4"
}
```
### 返回
```json
{
    "msg": "success",
    "code": 200,
    "result": {}
}
```



## 直播统计数据---平南-直播统计
```
GET  /api/v1/analysis/police_analysis/{{id}}/
```
### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|id|`str`|是|直播id|

### 返回
```json
{
    "code": 200,
    "result": {
        "chat_users": 10,//聊天人数
        "chat_number": 10,//聊天数
        "avg_socre": 76.5,//答题平均分
        "respondents_count": 10,//答题人数
        "user_socre": [
            {
                "id": 870,
                "user": 13328,//答题用户有因id
                "score": 20,//得分
                "createDate": "2020-04-24T14:17:58.258471"
            },
            {
                "id": 871,
                "user": 11551,
                "score": 100,
                "createDate": "2020-04-24T14:21:48.105995"
            },
            {
                "id": 872,
                "user": 264,
                "score": 60,
                "createDate": "2020-04-24T14:33:12.734543"
            },
            {
                "id": 873,
                "user": 6975,
                "score": 50,
                "createDate": "2020-04-24T14:33:41.770245"
            },
            {
                "id": 874,
                "user": 5628,
                "score": 110,
                "createDate": "2020-04-24T15:00:32.269405"
            },
            {
                "id": 875,
                "user": 14058,
                "score": 110,
                "createDate": "2020-04-24T15:00:59.591716"
            },
            {
                "id": 876,
                "user": 3155,
                "score": 35,
                "createDate": "2020-04-24T15:08:19.498575"
            },
            {
                "id": 877,
                "user": 13833,
                "score": 65,
                "createDate": "2020-04-24T15:12:06.238440"
            },
            {
                "id": 878,
                "user": 8147,
                "score": 110,
                "createDate": "2020-04-27T15:23:09.271174"
            },
            {
                "id": 898,
                "user": 13481,
                "score": 105,
                "createDate": "2020-05-01T12:01:52.222336"
            }
        ]
    },
    "msg": "success"
}
```


## 访问地址

接口请求域名: [https://jexzb.gaj.sh.gov.cn](https://jexzb.gaj.sh.gov.cn)

测试地址:https://live.test2.youinsh.cn


## 文档启用，弃用回调接口
```
POST  /api/v1/course/contain_document/{{id}}/
```
### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|id|`str`|是|直播的id|
|doc|`int`|是|是否使用文档，0:弃用文档包括删除，不在前端显示，1:启用文档|


#### 请求示例
```json
POST  /api/v1/course/contain_document/{{id}}/

Content-Type: application/json
{
    "doc":1,
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

## 获取tab页的统计数据接口
```
GET /api/v1/analysis/po_stattistics/{{id}}/
```
### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|id|`int`|是|直播的id|

#### 请求示例

```json
GET /api/v1/analysis/po_stattistics/{{id}}/

Content-Type: application/json

Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

### 返回
```json
{
    "result": {
        "que_count": 0, //问卷答题人数
        "check_in_count": 89,//签到人数
        "chat_count": 88,//聊天人数
        "watch_count": 128//直播观众
    },
    "msg": "success",
    "code": 200
}
```

## 获取当前平均分以及评分人数
```
GET /api/v1/course/result_socre/{{id}}/
```
### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|id|`int`|是|直播的id|

#### 请求示例

```json
GET /api/v1/course/result_socre/{{id}}/

Content-Type: application/json

Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

### 返回
```json
{
    "result": {
        "socre_avg": 3.2,   //平均分
        "socre_count": 5    //总评分的人数
    },
    "msg": "success",
    "code": 200
}
```

## 获取当前用户是否已经评分
```
GET /api/v1/course/socre/{{id}}/
```
### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|id|`int`|是|直播的id|

#### 请求示例

```json
GET /api/v1/course/socre/{{id}}/

Content-Type: application/json

Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

### 返回
```json
{
    "msg": "success",
    "result": {
        "socre": true       //true已经评过分，false还没有评分
    },
    "code": 200
}
```


## 对课程评分
```
POST  /api/v1/course/socre/{{id}}/
```
### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|id|`str`|是|直播的id|
|socre|`int`|是|分数，只能1，2，3，4，5，最大5分最少1分|


#### 请求示例
```json
POST  /api/v1/course/socre/{{id}}/

Content-Type: application/json
{
    "socre":5,
}
```
### 返回
```json
{
    "msg": "success",
    "code": 200,
    "result": {}
}

错误返回
{
    "msg": "已经参与过评分",
    "code": 400,
    "result": {}
}

```


## 问卷--获取问卷类型
```
GET /api/v1/questionnaires/get_category/
```
### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|

#### 请求示例

```json
GET /api/v1/questionnaires/get_category/

Content-Type: application/json

Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

### 返回
```json
{
    "result": [
        {
            "id": 1,
            "name": "测验",
            "sub_category": [
                {
                    "id": 2,//问卷类型id
                    "name": "考评"//问卷类型名称
                },
                {
                    "id": 4,
                    "name": "反馈"
                },
                {
                    "id": 5,
                    "name": "其他"
                }
            ]
        }
    ],
    "msg": "success",
    "code": 200
}
```


## 问卷--创建问卷
```
POST  /api/v1/questionnaires/create_questionnaire/
```
### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|active|`str`|否|是否激活问卷，active：激活，inactive：不激活，此字段不带入默认是激活|
|category_id|`int`|是|问卷类型id|
|title|`str`|是|问卷标题|
|video_id|`int`|是|问卷关联的直播id|
|answer_type|`str`|是|问卷答题类型，one:一题一题回答，many：所有题目一起提交|


#### 请求示例
```json
POST  /api/v1/questionnaires/create_questionnaire/

Content-Type: application/json
{
    "active": "active",
    "category_id": 2,
    "title": "test问卷",
    "video_id":36,
    "answer_type":"one"
}
```
### 返回
```json
{
    "code": 200,
    "msg": "success",
    "result": {
        "id": 17,//创建的问卷id
        "title": "test问卷",//问卷标题
        "owner_user": 2,//创建者id，有因用户id
        "answer_type": "one",//答题类型
        "createDate": "2019-09-11T16:46:44.004245",
        "active": "active",//是否已经激活
        "enterprise": 4,//所属单位id
        "course": 36//所属直播id

    }
}
```


## 问卷--创建问卷的题目（每一道题都需要单独调用一次接口，不允许所有题目一起提交）
```
POST  /api/v1/questionnaires/create_question/
```
### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|question_text|`str`|是|题目标题|
|question_type|`str`|是|题目类型，multiple：多选题，single：单选题，judgment：判断题，short_answer：简答题|
|questionnaire_id|`int`|是|问卷的id|
|sort_no|`int`|是|此题排序，数字越小越靠前，默认第一题为1，依次加1|
|score|`int`|是|此题目设置的分数，默认为0|
|options|`list`|是|题目的答案选项，选择题必须有，当为问答题，此list为空list|
|content|`int`|是|选项内容|
|sort_no|`int`|是|排序，从1开始，默认1为第一个选项依次递增|
|is_correct|`int`|是|此选项是否是正确答案，1:设置为正确答案，0，错误答案，默认为0|

#### 请求示例
```json
POST  /api/v1/questionnaires/create_question/

Content-Type: application/json
{
    "question_text": "单选1",
    "question_type": "single",
    "questionnaire_id": 17,
    "sort_no": 1,
    "score": 15,
    "options":[
    	{"content": "a", "sort_no": 1, "is_correct": 0},
    	{"content": "b", "sort_no": 2, "is_correct": 1},
    	{"content": "c", "sort_no": 3, "is_correct": 0},
    	{"content": "d", "sort_no": 4, "is_correct": 0}
    	]
}
```
### 返回
```json
{
    "code": 200,
    "msg": "success",
    "result": {
                    "77": 0,//选项的人数
                    "78": 1,
                    "79": 0,
                    "80": 0,
                    "all_count": 1//总数
                }

```


## 问卷--获取某个问卷的题目
```
GET /api/v1/questionnaires/questionnaire_question_list/{{id}}/
```
### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|id|`int`|是|问卷id|


#### 请求示例

```json
GET /api/v1/questionnaires/questionnaire_question_list/{{id}}/

Content-Type: application/json

Authorization: jwt xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

### 返回
```json
{
    "result": {
        "id": 23,//问卷id
        "title": "test1",//问卷标题
        "owner_user": 2,//创建者
        "answer_type": "one",//答题方式
        "createDate": "2019-09-16T17:59:44.341630",
        "active": "active",//是否允许使用
        "enterprise": 4,//所属企业
        "course": 36,//所属课程
        "questions_show_list": [//问卷题目
            {
                "id": 42,//题目id
                "question_type": "single",//单选类型
                "question_text": "单选",//问题题目
                "description": null,
                "questionnaire": 23,//所属问卷
                "sort_no": 1,//排序越小越靠前
                "required": false,//是否必填
                "score": 10,//此题目分数
                "english_text": null,
                "answered_yet": true,//此题目是否已经解答
                "options": [//题目的选项
                    {
                        "id": 77,//选项id
                        "question": 42,//所属题目
                        "content": "a",//选项内容
                        "description": "",
                        "is_correct": true,//是否是正确答案
                        "sort_no": 1,//排序越小越前
                        "is_answer": true//此选项本人的解答都是选过
                    },
                    {
                        "id": 78,
                        "question": 42,
                        "content": "b",
                        "description": "",
                        "is_correct": false,
                        "sort_no": 2,
                        "is_answer": false
                    },
                    {
                        "id": 79,
                        "question": 42,
                        "content": "c",
                        "description": "",
                        "is_correct": false,
                        "sort_no": 3,
                        "is_answer": false
                    },
                    {
                        "id": 80,
                        "question": 42,
                        "content": "d",
                        "description": "",
                        "is_correct": false,
                        "sort_no": 4,
                        "is_answer": false
                    }
                ],
                "result_count": {
                    "77": 0,
                    "78": 1,
                    "79": 0,
                    "80": 0,
                    "all_count": 1
                }
            },
            {
                "id": 43,
                "question_type": "multiple",
                "question_text": "多选题",
                "description": null,
                "questionnaire": 23,
                "sort_no": 2,
                "required": false,
                "score": 20,
                "english_text": null,
                "answered_yet": true,
                "options": [
                    {
                        "id": 81,
                        "question": 43,
                        "content": "aa",
                        "description": "",
                        "is_correct": true,
                        "sort_no": 1,
                        "is_answer": false
                    },
                    {
                        "id": 82,
                        "question": 43,
                        "content": "bb",
                        "description": "",
                        "is_correct": true,
                        "sort_no": 2,
                        "is_answer": true
                    },
                    {
                        "id": 83,
                        "question": 43,
                        "content": "cc",
                        "description": "",
                        "is_correct": false,
                        "sort_no": 3,
                        "is_answer": true
                    },
                    {
                        "id": 84,
                        "question": 43,
                        "content": "dd",
                        "description": "",
                        "is_correct": false,
                        "sort_no": 4,
                        "is_answer": false
                    }
                ],
                "result_count": {
                    "81": 0,
                    "82": 1,
                    "83": 0,
                    "84": 0,
                    "all_count": 1
                }

            },
            {
                "id": 44,
                "question_type": "judgment",
                "question_text": "判断题",
                "description": null,
                "questionnaire": 23,
                "sort_no": 3,
                "required": false,
                "score": 15,
                "english_text": null,
                "answered_yet": true,
                "options": [
                    {
                        "id": 85,
                        "question": 44,
                        "content": "对",
                        "description": "",
                        "is_correct": true,
                        "sort_no": 1,
                        "is_answer": true
                    },
                    {
                        "id": 86,
                        "question": 44,
                        "content": "错",
                        "description": "",
                        "is_correct": false,
                        "sort_no": 2,
                        "is_answer": false
                    }
                ],
                "result_count": {
                    "85": 0,
                    "86": 1,
                    "all_count": 1
                }
            },
            {
                "id": 45,
                "question_type": "short_answer",
                "question_text": "简答题",
                "description": null,
                "questionnaire": 23,
                "sort_no": 4,
                "required": false,
                "score": 0,
                "english_text": null,
                "answered_yet": true,
                "is_answer": "简答题答案",
                "options": [],
                "result_count": {
                    "all_count": 1
                }
            }
        ]
    },
    "msg": "success",
    "code": 200
}
```

## 问卷--详细信息统计
```
GET /api/v1/questionnaires/statistics_result/{{id}}/
```

### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|`id`|`int`|是|问卷id|

#### 请求示例

```json
GET /api/v1/questionnaires/statistics_result/{{id}}/

Content-Type: application/json
```
### 返回

```json
{
    "result": {
        "question_statistics": [
            {
                "id": 33,
                "question_type": "single",
                "question_text": "单选1",
                "description": null,
                "questionnaire": 19,
                "sort_no": 1,
                "required": false,
                "score": 10,
                "english_text": null,
                "answer_count": 1,
                "correct_rate": "200.00",
                "option_list": [
                    {
                        "id": 55,
                        "question": 33,
                        "content": "d",
                        "description": "",
                        "is_correct": false,
                        "sort_no": 4,
                        "answer_count": 0,
                        "rate": "0.00"
                    },
                    {
                        "id": 54,
                        "question": 33,
                        "content": "c",
                        "description": "",
                        "is_correct": false,
                        "sort_no": 3,
                        "answer_count": 0,
                        "rate": "0.00"
                    },
                    {
                        "id": 53,
                        "question": 33,
                        "content": "b",
                        "description": "",
                        "is_correct": true,
                        "sort_no": 2,
                        "answer_count": 1,
                        "rate": "100.00"
                    },
                    {
                        "id": 52,
                        "question": 33,
                        "content": "a",
                        "description": "",
                        "is_correct": false,
                        "sort_no": 1,
                        "answer_count": 0,
                        "rate": "0.00"
                    }
                ]
            },
            {
                "id": 34,
                "question_type": "multiple",
                "question_text": "多选",
                "description": null,
                "questionnaire": 19,
                "sort_no": 1,
                "required": false,
                "score": 20,
                "english_text": null,
                "answer_count": 1,
                "correct_rate": 0,
                "option_list": [
                    {
                        "id": 59,
                        "question": 34,
                        "content": "d",
                        "description": "",
                        "is_correct": false,
                        "sort_no": 4,
                        "answer_count": 0,
                        "rate": "0.00"
                    },
                    {
                        "id": 58,
                        "question": 34,
                        "content": "c",
                        "description": "",
                        "is_correct": true,
                        "sort_no": 3,
                        "answer_count": 1,
                        "rate": "100.00"
                    },
                    {
                        "id": 57,
                        "question": 34,
                        "content": "b",
                        "description": "",
                        "is_correct": true,
                        "sort_no": 2,
                        "answer_count": 1,
                        "rate": "100.00"
                    },
                    {
                        "id": 56,
                        "question": 34,
                        "content": "a",
                        "description": "",
                        "is_correct": false,
                        "sort_no": 1,
                        "answer_count": 0,
                        "rate": "0.00"
                    }
                ]
            },
            {
                "id": 35,
                "question_type": "judgment",
                "question_text": "判断",
                "description": null,
                "questionnaire": 19,
                "sort_no": 1,
                "required": false,
                "score": 20,
                "english_text": null,
                "answer_count": 1,
                "correct_rate": "100.00",
                "option_list": [
                    {
                        "id": 61,
                        "question": 35,
                        "content": "错",
                        "description": "",
                        "is_correct": true,
                        "sort_no": 2,
                        "answer_count": 1,
                        "rate": "100.00"
                    },
                    {
                        "id": 60,
                        "question": 35,
                        "content": "对",
                        "description": "",
                        "is_correct": false,
                        "sort_no": 1,
                        "answer_count": 0,
                        "rate": "0.00"
                    }
                ]
            },
            {
                "id": 36,
                "question_type": "short_answer",
                "question_text": "简答",
                "description": null,
                "questionnaire": 19,
                "sort_no": 1,
                "required": false,
                "score": 20,
                "english_text": null,
                "answer_count": 1,
                "correct_rate": "0.00",
                "option_list": []
            }
        ],
        "questionnaire": {
            "id": 19,
            "title": "test问卷1",
            "description": "",
            "category": {
                "id": 2,
                "name": "考评",
                "description": null,
                "parent": 1,
                "root": {
                    "name": "测验",
                    "parent": null,
                    "enterprise": null,
                    "id": 1,
                    "type": "exam",
                    "image_url": "",
                    "description": null
                },
                "image_url": "https://stagingcdn.youinsh.cn/staging/static/questionnaire/images/apply.png",
                "type": "exam"
            },
            "owner_user": 2,
            "startDate": null,
            "endDate": null,
            "expire": null,
            "createDate": "2019-09-11T17:27:35.822988",
            "updateDate": "2019-09-11T17:27:35.823117",
            "active": "active",
            "enterprise": 4,
            "score": 0,
            "owners": [
                36
            ],
            "share_qrcode_url": ""
        },
        "stage_score": {
            "91_100": 0,
            "0_60": 0,
            "71_80": 1,
            "81_90": 0,
            "61_70": 0
        }
    },
    "code": 200,
    "msg": "success"
}
```


## 获取推流地址(智慧教室对接使用)
```
GET /api/v1/course/push_stream_url/{{id}}/?key=xxx
```

### 参数

|名称|类型|是否必须|描述|
|----|----|----|----|
|`id`|`int`|是|课程id|
|`key`|`string`|是|请求密钥|

#### 请求示例

```json
GET /api/v1/course/push_stream_url/33/?key=21604aebb8d97cbb56dd10b1cc0c441b

Content-Type: application/json
```

#### 参数说明
```
id：课程的唯一标识，id是正整型
key：访问接口的签名

签名计算方法：当天日期+streankey+课程id  组成字符串使用md5加密

如今天是2019年9月4日，课程id为33
则组成字符串为20190904streankey33
使用md5加密得到21604aebb8d97cbb56dd10b1cc0c441b
```

### 返回

```json
{
    "msg": "success",//成功返回success，失败返回错误信息
    "code": 200,//成功返回code=200，失败返回400
    "result": {
        "pulish_url": "rtmp://jexlmt.gaj.sh.gov.cn:2935/hls/enterprise4third1567578277",//推流完整地址
        "domain": "rtmp://jexlmt.gaj.sh.gov.cn:2935/hls/",//推流domain
        "stream_name": "enterprise4third1567578277"//流密钥名称
    }
}
```

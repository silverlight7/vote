<!-- aglio -i vote.md -o vote.html -->
<!-- drakov -f ./vote.md -p 3000 -->


hello world

## 消息 [/messages]

### 获取消息 [GET]

+ Response 200 (application/json)
{
  "hello": "world"
}

## 投票 [/vote/v1/get]

### 获取投票详情 [GET]

+ Response 200 (application/json)
{
  "id":"1",
  "title":"闪亮童年，云秀风采",
  "endTime":"2020-09-11T02:09:11.000+0000"
}


## 投票列表 [/vote/v1/get_list]

### 获取投票列表 [POST]

+ Parameters
    + key (string,required) - 关键字搜索,字符串
    + start (numberl,required) - 开始位置, 整型 必填
    + count (numberl,required) - 每页显示条数, 整型  必填

+ Response 200 (application/json)
[
  "content":{
    "id":"1",
    "title":"闪亮童年，云秀风采",
    "endTime":"2020-09-11T02:09:11.000+0000"
  },
  "pageable": {
      "sort": {
          "sorted": false,
          "unsorted": true,
          "empty": true
      },
      "pageNumber": 0,
      "pageSize": 10,
      "offset": 0,
      "paged": true,
      "unpaged": false
  },
  "totalPages": 3,
  "totalElements": 24,
  "last": false,
  "first": true,
  "sort": {
      "sorted": false,
      "unsorted": true,
      "empty": true
  },
  "size": 10,
  "number": 0,
  "numberOfElements": 10,
  "empty": false
]


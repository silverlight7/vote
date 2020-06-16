<!-- aglio -i vote.md -o vote.html -->
<!-- drakov -f ./vote.md -p 3000 -->


投票接口文档

<!-- ## 消息 [/messages]

### 获取消息 [GET]

+ Response 200 (application/json)
{
  "hello": "world"
} -->


## 获取主题 [/vote/v1/get_subjects]

### 获取主题 [GET]

+ Response 200 (application/json)
[{
  "id":"1",
  "name":"默认"
},{
  "id":"2",
  "name":"儿童"
},{
  "id":"3",
  "name":"宠物"
},{
  "id":"4”,
  "name":"爱国"
},{
  "id":"5",
  "name":"中秋"
},{
  "id":"6",
  "name":"春节"
}
]



## 获取配色 [/vote/v1/get_colors]

### 获取配色 [GET]

+ Response 200 (application/json)
[{
  "id":"1",
  "name":"模板-蓝"
},{
  "id":"2",
  "name":"模板-红"
},{
  "id":"3",
  "name":"模板-绿"
},{
  "id":"4”,
  "name":"模板-橘"
},{
  "id":"5",
  "name":"模板-黑金"
},{
  "id":"6",
  "name":"模板-白蓝"
},{
  "id":"7",
  "name":"模板-橘红"
},{
  "id":"8",
  "name":"模板-酒红"
}
]


## 创建投票 [/vote/v1/create]

### 创建投票 [POST]

+ Parameters
  + title (string,required) - 标题,字符串 必填
  + description (string,required) - 描述,字符串
  + medias (string,required) - 媒体元素, 字符串 
  + creatorId (string,required) - 创建人id, 字符串 必填
  + creatorName (string,required) - 创建人名称, 字符串 必填
  + carousels (string,required) - 轮播图, 字符串 必填
  + shareMedias (string,required) - 分享图片, 字符串 
  + subjectId (string,required) - 主题id, 字符串 
  + subjectName (string,required) - 主题名称, 字符串 
  + colorId (string,required) - 配色id, 字符串 
  + colorName (string,required) - 配色名称, 字符串 

  + voteStartTime (long,required) - 投票开始时间, 长整形 必填
  + voteEndTime (long,required) - 投票结束时间, 长整形 必填
  + endTime (long,required) - 截止时间, 长整形 必填

  + joinStartTime (long,required) - 报名开始时间, 长整形
  + joinEndTime (long,required) -  报名结束时间, 长整形

  + requireName (int,required) -  所需名称, 整形（0:必填,1:选填,2:隐藏） 必填
  + requirePhoto (int,required) -  所需图片, 整形（0:必填,1:选填,2:隐藏） 必填
  + requireVideo (int,required) -  所需短视频（90s内）,整形（0:必填,1:选填,2:隐藏） 必填
  + requirePhone (int,required) -  所需手机号, 整形（0:必填,1:选填,2:隐藏） 必填
  + requireWechat (int,required) -  所需微信号, 整形（0:必填,1:选填,2:隐藏） 必填

  + sponsorName (string,required) - 主办方名称, 字符串 
  + sponsorLogo (string,required) - 主办方logo, 字符串 
  + sponsorPhone (string,required) - 主办方联系电话, 字符串 
  + sponsor2Code (string,required) - 主办方二维码, 字符串 

  + voteTimesType (string,required) - 投票类型, 字符串（total，everyday）
  + voteTimes  (int,required) - 投票次数, 整形

  + selectBeginCount  (int,required) - 多选开始数量, 整形
  + selectEndCount  (int,required) - 多选结束数量, 整形

  + limitProvince (string,required) - 限定省, 字符串
  + limitCity (string,required) - 限定市, 字符串
  + limitArea (string,required) - 限定区, 字符串

  + limitIpVoteTimes  (int,required) - 每天同一ip可投次数, 整形
  
  + drawLuck (boolean,required) - 是否发起抽奖, boolean
  + activityNotice (string,required) - 活动公告, 字符串
  


   
+ Request (application/json)
{
  "title":"闪亮童年，云秀风采",
  "description":"",
  "medias":"",
  "creatorId":"",
  "creatorName":"",
  "carousels":"",
  "shareMedias":"",

  "subjectId":"",
  "subjectName":"",
  
  "colorId":"",
  "colorName":"",

  "voteStartTime",0,
  "voteEndTime",0,

  "joinStartTime",0,
  "joinEndTime","",

  "requireName",0,
  "requirePhoto",0,
  "requireVideo",0,
  "requirePhone",0,
  "requireWechat",0,

  "sponsorName","",
  "sponsorLogo","",
  "sponsorPhone","",
  "sponsor2Code","",
  "voteTimesType","",
  "voteTimes",0,

  "selectBeginCount",0,
  "selectEndCount",0,

  "limitProvince","",
  "limitCity","",
  "limitArea","",
  "limitIpVoteTimes",

  "drawLuck",false,
  "activityNotice","",
  
}

+ Response 200 (application/json)
{

}


## 我创建的投票 [/vote/v1/get_my_list]

### 获取我创建的投票列表 [POST]

+ Parameters
  + key (string,required) - 关键字搜索,字符串
  + userId (string,required) - 投票编号,字符串 必填
  + sort (string,required) - 排序,字符串 
  + start (numberl,required) - 开始位置, 整型 必填
  + count (numberl,required) - 每页显示条数, 整型  必填
   
+ Request (application/json)
{
  "key":"",
  "userId":"1",
  "sort": "",
  "start":0,
  "count":10
}

+ Response 200 (application/json)
{
  "content":[
    {
      "id":"1",
      "title":"闪亮童年，云秀风采",
      "endTime":"2020-09-11T02:09:11.000+0000",
      "description":"",
      "medias":"",
      "createTime":"2020-09-11T02:09:11.000+0000"
    },
     {
      "id":"2",
      "title":"闪亮童年，云秀风采",
      "endTime":"2020-09-11T02:09:11.000+0000",
      "description":"",
      "medias":"",
      "createTime":"2020-09-11T02:09:11.000+0000"
    }

  ],
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
}





## 投票 [/vote/v1/get]

### 获取投票详情 [GET]

+ Parameters
  + id (string,required) - 投票id,字符串 必填

+ Response 200 (application/json)
{
  "id":"1",
  "title":"闪亮童年，云秀风采",
  "endTime":"2020-09-11T02:09:11.000+0000",
  "description":"",
  "medias":"",
  "visiteCount":1001232,
  "totalVoteCount":989829,
  "SignUpCount":36
}

## 参与投票列表 [/vote/v1/get_players]

### 获取参与投票列表 [POST]

+ Parameters
  + key (string,required) - 关键字搜索,字符串
  + voteId (string,required) - 投票编号,字符串 必填
  + sort (string,required) - 排序,字符串 
  + start (numberl,required) - 开始位置, 整型 必填
  + count (numberl,required) - 每页显示条数, 整型  必填
   
+ Request (application/json)
{
  "key":"",
  "voteId":"1",
  "sort": "",
  "start":0,
  "count":10
}

+ Response 200 (application/json)
{
  "content":[
    {
      "id":"1",
      "voteId":"1",
      "title":"三（6）班 刘文瀚",
      "description":"",
      "code":"36",
      "medias":"",
      "head":"",
      "voteCount":320
    },
     {
      "id":"2",
      "voteId":"1",
      "title":"三（6）班 李佳琪",
      "description":"",
      "code":"35",
      "medias":"",
      "head":"",
      "voteCount":320
    },
     {
      "id":"3",
      "voteId":"1",
      "title":"三（6）班 张子萱",
      "description":"",
      "code":"34",
      "medias":"",
      "head":"",
      "voteCount":320
    },
     {
      "id":"4",
      "voteId":"1",
      "title":"三（6）班 郝文静",
      "description":"",
      "code":"33",
      "medias":"",
      "head":"",
      "voteCount":320
    }

  ],
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
}






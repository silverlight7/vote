
<!-- aglio -i coupon.md -o coupon.html -->
<!-- drakov -f ./coupon.md -p 3000 -->

优惠券接口文档



## 获取平台优惠券 [/promotion/coupon/v1/get_list]

### 获取平台优惠券 [POST]

+ Parameters
  + start (int,required) - 开始位置, 整型 必填
  + count (int,required) - 每页显示条数, 整型  必填
   
+ Request (application/json)
{
  "start":0,
  "count":10
}

+ Response 200 (application/json)
{
  "content":[
    {
        "id": "89823948204820480242422423",
        "name": "全品九折",
        "description": null,
        "photo": null,
        "code": "c1",
        "type": "Discount",
        "discount": 0.9,
        "price": 0.0,
        "useSingle": false,
        "singleClass": null,
        "singleClassName": null,
        "effectiveTime": {
            "begin": "2020-06-23T06:18:04.339+0000",
            "end": "2020-06-23T06:18:04.339+0000"
        },
        "createTime": "2020-06-23T06:18:04.339+0000"
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



## 领取优惠券 [/promotion/coupon/v1/receive]

### 领取优惠券 [POST]

+ Parameters

  + couponId (string,required) - 优惠券id, 字符串 必填
  + userId (string,required) - 用户id, 字符串 必填
  + userName (string,required) - 用户名称, 字符串 必填

   
+ Request (application/json)
{
  "couponId":"1",
  "userId":"",
  "userName":""
}

+ Response 200 (application/json)
{
}







## 获取我的优惠券 [/promotion/coupon/v1/get_my_list]

### 获取我的优惠券 [POST]

+ Parameters
  + ownerId (String,required) - 用户id, 字符串 必填
  + start (int,required) - 开始位置, 整型 必填
  + count (int,required) - 每页显示条数, 整型  必填
  + status (状态,required) - 状态, 枚举 UnUsed Used
   
+ Request (application/json)
{
  "ownerId":"",
  "start":0,
  "count":10,
  "status":"Used"
}

+ Response 200 (application/json)
{
  "content":[
    {
        "id": "1231313131313",
        "code": "c8989891823",
        "coupon": {
            "id": "89823948204820480242422423",
            "name": "全品九折",
            "description": null,
            "photo": null,
            "code": "c1",
            "type": "Discount",
            "discount": 0.9,
            "price": 0.0,
            "useSingle": false,
            "singleClass": null,
            "singleClassName": null,
            "effectiveTime": {
                "begin": "2020-06-23T06:38:32.685+0000",
                "end": "2020-06-23T06:38:32.685+0000"
            },
            "createTime": "2020-06-23T06:38:32.685+0000"
        },
        "owner": {
            "id": "123",
            "name": "张三"
        },
        "status": "UnUsed",
        "createTime": "2020-06-23T06:38:32.685+0000"
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




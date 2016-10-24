#api 文档:  `/publishes`
======================================================

* [返回目录](/README.md)


- [x] 获取publish列表（热点、滚动、发现）
```
PATH: /publishes?filterKey=     //获取hs热点、sc滚动、ds发现
METHOD: GET

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  pageInfo: {
    page: 1,
    perPage: 20,
    totalNum: 15
  },
  payload: [
    {
      "_id": "580b81e452540a7b2f8010d8",
      "updatedAt": "2016-10-22T15:12:36.013Z",
      "createdAt": "2016-10-22T15:12:36.013Z",
      "type": 21,
      "content": "",
      "uid": "57ec8499a49385392fa36154",
      "__v": 0,
      "commentNum": 0,
      "mediaUrls": [
          "This is a mediaUrl",
          "This is another mediaUrl",
          ...
      ],
      "summary": "",
      "id": "580b81e452540a7b2f8010d8",
      "user": {
        "_id": "57ec8499a49385392fa36154",
        "nickname": "潭老师",
        "headimgurl": "this is a url",
        "id": "57ec8499a49385392fa36154"
      },
      "likeNum": 0,
      "collectNum": 0,
      "forwardNum": 0,
      "likedFlag": false,
      "collectedFlag": false,
      "followedFlag": false
    },
    ......
  ]
}
```
------------------------------------------------------
- [x] 获取publish列表（朋友圈）
```
PATH: /publishes/friendsCircle
METHOD: GET

HEADER：
{
  Authorization:'Bearer ' + token
}

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  pageInfo: {
    page: 1,
    perPage: 20,
    totalNum: 15
  },
  payload: [
    {
      "_id": "580b81e452540a7b2f8010d8",
      "updatedAt": "2016-10-22T15:12:36.013Z",
      "createdAt": "2016-10-22T15:12:36.013Z",
      "type": 21,
      "content": "",
      "uid": "57ec8499a49385392fa36154",
      "__v": 0,
      "commentNum": 0,
      "mediaUrls": [
          "This is a mediaUrl",
          "This is another mediaUrl",
          ...
      ],
      "summary": "",
      "id": "580b81e452540a7b2f8010d8",
      "user": {
        "_id": "57ec8499a49385392fa36154",
        "nickname": "潭老师",
        "headimgurl": "this is a url",
        "id": "57ec8499a49385392fa36154"
      },
      "likeNum": 0,
      "collectNum": 0,
      "forwardNum": 0,
      "likedFlag": false,
      "collectedFlag": false,
      "followedFlag": false
    },
    ......
  ]
}
```
------------------------------------------------------
- [x] 获取publish详情
```
PATH: /publishes/:_id
METHOD: GET

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: {
    "_id": "580b81e452540a7b2f8010d8",
    "updatedAt": "2016-10-22T15:12:36.013Z",
    "createdAt": "2016-10-22T15:12:36.013Z",
    "type": 21,
    "content": "",
    "uid": "57ec8499a49385392fa36154",
    "__v": 0,
    "commentNum": 0,
    "mediaUrls": [
        "This is a mediaUrl",
        "This is another mediaUrl",
        ...
    ],
    "summary": "",
    "id": "580b81e452540a7b2f8010d8",
    "user": {
      "_id": "57ec8499a49385392fa36154",
      "nickname": "潭老师",
      "headimgurl": "this is a url",
      "id": "57ec8499a49385392fa36154"
    },
    "likeNum": 0,
    "collectNum": 0,
    "forwardNum": 0,
    "likedFlag": false,
    "collectedFlag": false,
    "followedFlag": false
  },
}
```
------------------------------------------------------
- [x] 修改publish(移动端不开放给用户)
```
PATH: /publishes/:_id
METHOD: PUT

HEADER：
{
  Authorization:'Bearer ' + token
}
BODY:
{
  updateKey: updateValue,
  ......
}

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: {                             //return updated publish
    "_id": "580b81e452540a7b2f8010d8",
    "updatedAt": "2016-10-22T15:12:36.013Z",
    "createdAt": "2016-10-22T15:12:36.013Z",
    "type": 21,
    "content": "",
    "uid": "57ec8499a49385392fa36154",
    "__v": 0,
    "commentNum": 0,
    "mediaUrls": [
        "This is a mediaUrl",
        "This is another mediaUrl",
        ...
    ],
    "summary": "",
    "id": "580b81e452540a7b2f8010d8",
    "user": {
      "_id": "57ec8499a49385392fa36154",
      "nickname": "潭老师",
      "headimgurl": "this is a url",
      "id": "57ec8499a49385392fa36154"
    },
    "likeNum": 0,
    "collectNum": 0,
    "forwardNum": 0,
    "likedFlag": false,
    "collectedFlag": false,
    "followedFlag": false
  },
}
```
------------------------------------------------------
- [x] 删除publish(ios)
```
PATH: /publishes/:_id
METHOD: DELETE

HEADER：
{
  Authorization:'Bearer ' + token
}

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: {                             //return deleted publish
    [deleted object]
  }
}
```
------------------------------------------------------
- [x] 删除publish(android)
```
PATH: /publishes/:_id/delete
METHOD: POST

HEADER：
{
  Authorization:'Bearer ' + token
}

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: {                             //return deleted publish
    [deleted publish object]
  }
}
```
------------------------------------------------------
- [x] 发布publish
```
PATH: /publishes
METHOD: POST

HEADER：
{
  Authorization:'Bearer ' + token
}
BODY:
{
  title: char,
    //10：小编视频、11：小编文章
    //20：个人视频、21：个人图文、22：个人文章、23：个人转发
  type: Number,
  content: char,
  mediaUrls: [char, char],
  code: char, //股票主题
  scroFlag: boolean, //仅（Admin）用轮播
}

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: {                             //return new created publish
    [new publish object]
  }
}
```
------------------------------------------------------
------------------------------------------------------


##model
- [x] API功能
  详细说明
```
PATH: /auth/weixinLogin  //微信登录
METHOD: GET
Header:
{
  Authorization:'Bearer ' + token
}
BODY：
{
   data: String, //说明
}

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: {
    [object]
  }
}
```
------------------------------------------------------

* [回到顶部](#readme)             [返回目录](/README.md)

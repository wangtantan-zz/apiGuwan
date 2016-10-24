#api 文档:  `/admin`
======================================================

* [返回目录](/README.md)


- [x] 获取publish列表（热点、滚动、发现）
```
PATH: admin/publishes?filterKey=     //获取hs热点、sc滚动、ds发现
PATH: admin/publishes?keyword=关键字&type=     //根据关键字获取hotspot热点、discover发现
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
- [x] 获取publish详情
```
PATH: /admin/publishes/:_id
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
- [x] 修改publish(仅后端管理用)
```
PATH: /admin/publishes/:_id
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
- [x] 删除publish(admin)
```
PATH: /admin/publishes/:_id
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
- [x] 发布publish
```
PATH: /admin/publishes
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

- [x] 获取comment列表
```
PATH: /admin/comments?code=     //获取股票主题的讨论
PATH: /comments?pid=      //获取pid的讨论
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
      "_id": "580d650452540a7b2f8010db",
      "updatedAt": "2016-10-24T01:33:56.529Z",
      "createdAt": "2016-10-24T01:33:56.529Z",
      "pid": "5809da5b52540a7b2f8010c9",
      "content": "腻害了",
      "uid": "57f9b51a3e7f60060366346a",
      "__v": 0,
      "id": "580d650452540a7b2f8010db",
      "user": {
        "_id": "57f9b51a3e7f60060366346a",
        "nickname": "yeah",
        "headimgurl": "http://guwan-sg.oss-cn-hangzhou.aliyuncs.com/publish/image/1477019457484.png",
        "id": "57f9b51a3e7f60060366346a"
      },
      "likeNum": 0,
      "likedFlag": false
    },
    ......
  ]
}
```
------------------------------------------------------
- [x] 删除comment(admin)
```
PATH: /admin/comments/:_id
METHOD: DELETE

HEADER：
{
  Authorization:'Bearer ' + token
}

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: {
    [deleted comment object]
  }
}
```
------------------------------------------------------
- [x] 发表comment
```
PATH: /admin/comments
METHOD: POST

HEADER：
{
  Authorization:'Bearer ' + token
}
BODY:
{
  pid: char,   //基于publish的评论内容
  content: char,
  replyTo: char, //回复uid，可不填
}

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: {
    [new comment object]
  }
}
```
------------------------------------------------------
------------------------------------------------------

- [x] 微信转发
  微信转发需要的参数
```
PATH: /auth/wxConfig?url=
METHOD: GET
Header:
{
  Authorization:'Bearer ' + token
}

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: {
    "timestamp": 1477391655,
    "nonceStr": "e502fc354e79a8ed7ec8ecef0c56780b",
    "url": "1",
    "sign": "c6ef3e47fafdd2eb70435b9575ec49db75b2d1cb"
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

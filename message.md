#api 文档:  `/messages`
======================================================

* [返回目录](/README.md)


- [x] 获取message列表

| 序号 | messageType | 返回字段 | 特有字段 |
| :----: | ------ | ----- | ----- | ----- |
| 1 | getComment | uid,actUser,messageType,publish,content | comment |
| 2 | pubComment | uid,actUser,messageType,publish,content | comment |
| 3 | getLike | uid,actUser,messageType,publish |comment |
```
PATH: /messages?messageType=     //根据类型获取message列表

METHOD: GET

HEADER：
{
  Authorization:'Bearer ' + token
}

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: [
    {
      "_id": "58183836cf1c9d3b2658de92",
      "uid": "57ec96e0a49385392fa36161",
      "updatedAt": "2016-11-01T06:37:42.430Z",
      "createdAt": "2016-11-01T06:37:42.430Z",
      "content": "我是一个好人",
      "messageType": "getComment", //getComment, pubComment, getLike
      "actUser": {
        "headimgurl": "This is an Url",
        "nickname": "Prophet.Wang_10003",
        "_id": "57ff2f33d734987679a300bb"
      },
      "comment": {
        "user": {
          "headimgurl": "This is an Url",
          "nickname": "Prophet.Wang_10003",
          "_id": "57ff2f33d734987679a300bb"
        },
        "replyTo": "57ec96e0a49385392fa36161",
        "content": "",
        "uid": "57ff2f33d734987679a300bb",
        "pid": "57ff2a27dbb1628d5fe1b8f7",
        "createdAt": "2016-11-01T07:08:31.504Z",
        "updatedAt": "2016-11-01T07:08:31.504Z",
        "_id": "58183f6fafda64892601a54e" 
      },
      "publish": {
        "user": {
          "headimgurl": "This is an Url",
          "nickname": "Prophet.Wang_10003",
          "_id": "57ec96e0a49385392fa36161"
        },
        "mediaUrls": [],
        "commentNum": 4,
        "tags": [],
        "__v": 0,
        "uid": "57ec96e0a49385392fa36161",
        "type": 21,
        "title": "搜股",
        "sumary": "summary content",
        "createdAt": "2016-10-13T06:31:03.332Z",
        "updatedAt": "2016-11-01T06:37:42.357Z",
        "_id": "57ff2a27dbb1628d5fe1b8f7"
      },
      "id": "58183836cf1c9d3b2658de92"
    },
    ......
  ]
}
```
------------------------------------------------------
- [x] 删除message(ios)
```
PATH: /messages/:_id
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
- [x] 删除message(android)
```
PATH: /messages/:_id/delete
METHOD: POST

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

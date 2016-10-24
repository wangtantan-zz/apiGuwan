#api 文档:  `/comments`
======================================================

* [返回目录](/README.md)


- [x] 获取comment列表
```
PATH: /comments?code=     //获取股票主题的讨论
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
        "headimgurl": "This is an head image url",
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
- [x] 删除comment(ios)
```
PATH: /comments/:_id
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
- [x] 删除comment(android)
```
PATH: /comments/:_id/delete
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
- [x] 发表comment
```
PATH: /comments
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

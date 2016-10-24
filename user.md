#api 文档:  `/users`
======================================================

* [返回目录](/README.md)


- [x] 获取个人信息
  通过token得到uid，无则根据query得到uid，然后根据uid获取列表
```
PATH: /users/me?uid=  //uid or token is required!
METHOD: GET

HEADER：
{
  Authorization:'Bearer ' + token
}

Return Value:
{
  _id: ObjectID,
  message: char,//状态信息 "ok"表示成功
  payload: [
    {
      "_id": "57ec8499a49385392fa36154",
      "updatedAt": "2016-10-22T10:05:25.770Z",
      "createdAt": "2016-09-29T03:03:53.845Z",
      "unionid": "oPkmxt_tknpaZqFWrAzE24pBYYEI",
      "nickname": "潭老师",
      "headimgurl": "This is an head image url",
      "wechatUser": { } `或` "mobile": "15821788171",
      "__v": 0,
      "city": "香港特别行政区 香港特别行政区",
      "birth": "1990-11-11T00:00:00.000Z",
      "desc": "我问问去",
      "sex": 1,
      "id": "57ec8499a49385392fa36154",
      "followersNum": 2,
      "followingNum": 4,
      "followedFlag": true
    },
    ...
  ],
}
```
------------------------------------------------------
- [x] 修改个人信息（ios）
```
PATH: /users/me
METHOD: PUT

HEADER：
{
  Authorization:'Bearer ' + token
}
BODY：
{
  nickname: char,
  sex: number,  //0女1男
  desc: char,   //个人签名
  birth: char,  //"2016-01-01"
  headimgurl: char,
}

Return Value:
{
  _id: ObjectID,
  message: char,//状态信息 "ok"表示成功
  payload: [
    {
      "_id": "57ec8499a49385392fa36154",
      "updatedAt": "2016-10-22T10:05:25.770Z",
      "createdAt": "2016-09-29T03:03:53.845Z",
      "unionid": "oPkmxt_tknpaZqFWrAzE24pBYYEI",
      "nickname": "潭老师",
      "headimgurl": "This is an head image url",
      "wechatUser": { } `或` "mobile": "15821788171",
      "__v": 0,
      "city": "香港特别行政区 香港特别行政区",
      "birth": "1990-11-11T00:00:00.000Z",
      "desc": "我问问去",
      "sex": 1,
      "id": "57ec8499a49385392fa36154",
      "followersNum": 2,
      "followingNum": 4,
      "followedFlag": true
    },
    ...
  ],
}
```
------------------------------------------------------
- [x] 修改个人信息（android）
```
PATH: /users/me/update
METHOD: POST

HEADER：
{
  Authorization:'Bearer ' + token
}
BODY：
{
  nickname: char,
  sex: number,  //0女1男
  desc: char,   //个人签名
  birth: char,  //"2016-01-01"
  headimgurl: char,
}

Return Value:
{
  _id: ObjectID,
  message: char,//状态信息 "ok"表示成功
  payload: [
    {
      "_id": "57ec8499a49385392fa36154",
      "updatedAt": "2016-10-22T10:05:25.770Z",
      "createdAt": "2016-09-29T03:03:53.845Z",
      "unionid": "oPkmxt_tknpaZqFWrAzE24pBYYEI",
      "nickname": "潭老师",
      "headimgurl": "this is a url",
      "wechatUser": { } `或` "mobile": "15821788171",
      "__v": 0,
      "city": "香港特别行政区 香港特别行政区",
      "birth": "1990-11-11T00:00:00.000Z",
      "desc": "我问问去",
      "sex": 1,
      "id": "57ec8499a49385392fa36154",
      "followersNum": 2,
      "followingNum": 4,
      "followedFlag": true
    },
    ...
  ],
}
```
------------------------------------------------------
- [x] 获取主页的publish列表（个人发布、收藏、点赞、同股人）
  通过token得到uid，无则根据query得到uid，然后根据uid获取列表
```
PATH: /users/profile?uid=        //发布发布
PATH: /users/collect?uid=        //收藏发布
PATH: /users/like?uid=           //点赞发布
PATH: /users/sameStockUser?uid=  //同股人发布
METHOD: GET

Header:
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
- [x] 获取主页的用户列表（粉丝、关注）
  通过token得到uid，无则根据query得到uid，然后根据uid获取列表
```
PATH: /users/following?uid=        //关注列表
PATH: /users/followers?uid=        //粉丝列表
METHOD: GET

Header:
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
      "_id": "57f9b51a3e7f60060366346a",
      "nickname": "yeah",
      "headimgurl": "This is an head image url",
      "id": "57f9b51a3e7f60060366346a"
    },
    ......
  ]
}
```
------------------------------------------------------
- [x] 用户（取消）点赞、（取消）收藏、（取消）关注、（取消）转发

| function | functionName | body |
| :---: | :---- | :---- |
| 点赞评论 | (un)likeComment | targetId=cid |
| 点赞发布 | (un)likePublish | targetId=pid |
| 收藏发布 | (un)collectPublish | targetId=pid |
| 关注用户 | (un)followFollowing | targetId=uid |
| 转发发布 | forwardPublish | targetId=pid&originId:pid |
```
PATH: /users/:_functionName        //
METHOD: POST

Header:
{
  Authorization:'Bearer ' + token
}
BODY:
{
  targetId: uid | pid | cid,
  originId: pid,  //only forwardPublish need this
}

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: {
    funcName: char,
    uid: char,  //token.uid
    targetId: char, //uid | pid | cid
    originId: char,
  },
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

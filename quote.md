#api 文档:  `/quotes`
======================================================

* [返回目录](/README.md)


- [x] 发表反馈
```
PATH: /quotes?market= &version=
METHOD: GET

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: {
    version: Number,//状态信息 "ok"表示成功
    list: ,
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

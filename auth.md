#api 文档:  `/auth`
======================================================

* [返回目录](/README.md)


- [x] 微信登陆
```
PATH: /auth/appWechatLogin
METHOD: POST

Header:
{
  Authorization:'Bearer ' + token
}
BODY:
{
  code: number,
}

Return Value:
{
}
```
------------------------------------------------------
- [x] 短信登陆
```
PATH: /auth/smsLogin
METHOD: POST

Header:
{
  Authorization:'Bearer ' + token
}
BODY:
{
  mobile: number,
  verifyCode: number,
}

Return Value:
{
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

#api 文档:  `/auth`
======================================================

* [返回目录](/README.md)


- [x] 获取验证码
```
PATH: /sendVerifyCode
METHOD: POST
BODY:
{
  mobile: number,
}

Return Value:
{
}
```
------------------------------------------------------
- [x] app参数
  交易隐藏， 缩略图参数
```
PATH: /appConfig
METHOD: GET

Return Value:
{
  listThumbnailStyle: char, //缩略图参数
  hidden: num, //0关1开
}
```
------------------------------------------------------
- [x] 微信转发参数
```
PATH: /wxConfig?url=baidu.com
METHOD: GET

Return Value:
{
  timestamp: 1477365307,
  nonceStr: "ec171720505b3f493ca6eede44f114ff",
  url: "a",
  sign: "dd174eca0842aae91202ed7edc388678905dcc82"
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

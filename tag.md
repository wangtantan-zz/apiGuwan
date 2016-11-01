#api 文档:  `/tags`
======================================================

* [返回目录](/README.md)


- [x] 获取标签列表
```
PATH: /admin/tags
METHOD: GET
Header:

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: ["tag1", "tag2", "tag3"]
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

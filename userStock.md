#api 文档:  `userStocks/`
======================================================

* [返回目录](/README.md)


- [x] 获取自选股列表
```
PATH: /userStocks
METHOD: GET

Header:
{
  Authorization:'Bearer ' + token
}

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: [
    {
      "scode": "SH600004",
      "topFlag": false,
      "rank": 1,
      "eCode": "SH600004",
      "id": null
    },
    ......
  ]
}
```
------------------------------------------------------
- [x] 加自选
```
PATH: /userStocks
METHOD: GET

Header:
{
  Authorization:'Bearer ' + token
}
BODY：
{
   scode: "SH000201", //说明
}

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: ,
}
```
------------------------------------------------------
- [x] (取消)置顶
```
PATH: /userStocks/setTop
PATH: /userStocks/unsetTop
METHOD: GET

Header:
{
  Authorization:'Bearer ' + token
}
BODY：
{
   scode: "SH000201", //说明
}

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: ,
}
```
------------------------------------------------------
- [x] 批量加入自选
```
PATH: /userStocks/bulkSync
METHOD: POST

Header:
{
  Authorization:'Bearer ' + token
}
BODY：
{
  scodes: [{"scode":"xxxx","topFlag":true},...]
}

Return Value:
{
  message: char,//状态信息 "ok"表示成功
  payload: ,
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

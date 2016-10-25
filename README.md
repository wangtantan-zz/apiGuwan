#api 文档
======================================================

| 序号 | 接口（点击进入） | URL |
| :----: | :---------: | :------- |
| 1 | [默认](/index.md) | / |
| 2 | [登陆](/auth.md) | / |
| 3 | [发布](/publish.md) | /publishes |
| 4 | [用户](/user.md) | /users |
| 5 | [评论](/comment.md) | /comments |
| 6 | [管理员](/admin.md) | /admin |
| 7 | [大行情](/quote.md) | /quotes |
| 8 | [反馈](/feedback.md) | /feedbacks |
| 9 | [自选股](/userStock.md) | /userStocks |


##说明
- [x] 报错
```
除了标名不需认证，其他的接口需要在 header中添加 
UserAgent:  token="*****" 
服务器在切面上对所有需认证的接口进行身份认证
Authorization: "Bearer " + accessToken
X-SG-Agent: clientType/clientVersion/deviceID

clientType: andriod, ios, wap
clientVersion: 版本号
deviceID: 硬件可标识ID
return value:
200     认证成功
404     用户不存在
500     未知错误
501      用户未上线

errorCode List:
200     success
```
------------------------------------------------------
- [x] 接口报错返回的数据格式
```
Return Value:
{
  message : char,     //错误信息
  status  : number,   //HTTP状态码
  errtext : char,     //错误信息描述
  more    : obj,      //更多错误信息
}

message有以下类型:{
  paramsError:        //参数错误
  paramsMissing:      //缺少参数
  paramsLengthError:  //参数长度错误

  notFound:           //没找到
  unauthorized:       //token无效
  noUserForThisToken: //这个token没有对应的用户
  nicknameExist:      //这个nickname已经占用

  wrongActionTarget:  //不支持的操作或对象
  jsAPITicketErr:     //公众号ticket获取出错

  illegalActionType:  //非法操作类型
  shouldNotBeHere:    //不该到这里来
  systemError:        //系统错误
  undefinedUnionid:   //微信用户没有unionid

}
```
------------------------------------------------------
------------------------------------------------------

* [回到顶部](#readme)

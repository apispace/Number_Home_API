# APISpace 介绍
**本 API 服务由 [APISpace（apispace.com）](https://www.apispace.com/?utm_source=github&utm_term=shoujihaoguishudi) 提供。**

APISpace 是 Eolink 旗下专业的 API 开放与交易平台，为广大企业以及个人开发者提供多维度、全方位的API接口，覆盖短信验证、天气查询、快递物流、OCR文字识别等海量 API 服务，帮助用户快速获取数据，降低获取数据的成本和难度，提升开发效率。

APISpace 提供15种开发语言的代码示例，分别是：
- Java(OK HTTP)
- HTTP
- cURL
- 微信小程序
- PHP(pecl_http)、PHP(cURL)
- Python(http.client)、Python(Requests)
- JavaScript(Jquery AJAX)、JavaScript(XHR)
- NodeJS(Native)、NodeJS(Request)
- Ruby(Net:Http)
- Shell(Httpie)、Shell(cUrl)

# 手机号码归属地
提供全国移动、联通、电信等手机号码归属地查询，上亿条数据囊括最新的170、166、147等号段，更新及时、准确度高。

**使用该产品前，您需要通过 [https://www.apispace.com/eolink/api/teladress/introduction](https://www.apispace.com/eolink/api/teladress/introduction?utm_source=github&utm_term=shoujihaoguishudi) 申请API服务**

本文档末尾提供了 Python(Requests) 的调用代码示例，可以前往文档末尾查看。

更多代码示例：[https://www.apispace.com/eolink/api/teladress/guidence/](https://www.apispace.com/eolink/api/teladress/guidence/?utm_source=github&utm_term=shoujihaoguishudi)

### 应用场景
#### 1.帮助进行风控评审

手机号码归属地可广泛应用于互联网金融服务、企业管理咨询、贷款、担保、法律服务、物流行业、旅游、保险业务、电商、人力资源、租赁服务、通信服务等各类有需求的企事业单位风控审核环节。

#### 2.用户属性分析

借助手机号(段)归属查询服务，对用户注册预留的手机号码进行归属识别，判别用户所属运营商及大致城市区域，以便为客户提供更好的针对性服务。

#### 3.话费流量充值

话费流量充值应用查询手机号码(段)所属运营商、区域，选择相应运营商充值路由策略，避免错误或未知运营商信息导致充值失败的问题，降低充值失败率。

#### 4.活动推广

业务需求活动针对群体为所属运营商或指定区域的已有用户，借助手机号(段)归属查询服务对符合的用户群体进行推广活动展现。

#### 5.短信发送
短信发送平台查询手机号码(段)所属运营商、区域，选择合适的发送策略通道，避免非合适运营商通道导致的发送异常。

### 返回示例

```
{
    "tradeNo": "988818862110298112",
    "chargeStatus": 1,
    "message": "成功",
    "data": {
        "orderNo": "111",
        "handleTime": "2022-06-21 14:53:08",
        "province": "广东",
        "city": "广州",
        "provinceCode": "020",
        "cityCode": "440100",
        "isp": "联通",
        "mobile": "13286457456",
        "postCode": "510000"
    },
    "code": "200000"
}
```

### 服务保障
![image](https://user-images.githubusercontent.com/36323798/223365050-2a81fcd2-69af-46b9-bb61-1fdc97faf768.png)

### Python(Requests) 调用代码示例

```
import requests

url = "https://eolink.o.apispace.com/teladress/teladress"

payload = {"mobile":""}

headers = {
    "X-APISpace-Token":"",
    "Authorization-Type":"apikey",
    "Content-Type":"application/x-www-form-urlencoded"
}

response=requests.request("POST", url, data=payload, headers=headers)

print(response.text)

```

# Offer API

## 1. Getting started

To get started, make sure that you have requested and been approved 
for an API Key. Or ask your Account Manager to create it for you.

To make a request to the API, simply provide your key as well as the 
Network ID in which your account is registered.

## 2. Request URL

**GET** `/api?chnid={chnid}&key={key}`

Parameters | Description | Required
-- | -- | --
chnid | network id | Yes
key | network key | Yes

_Note: If you don't have `chnid` and `key`, please contact your Account Manager._

## 3. Request Parameters

Parameters | Description | Required
-- | -- | --
page | default value `1` | Yes
pagesize | offers number per page,default value `1000` | Optional
offer_id | offer id | Optional

> Sample:

```
http://[domain]/api?chnid=1&key=API_KEY&page=1&pagesize=100
```

## 4. Response

Fields | Type | Description
-- | -- | --
error | Integer | error code . `0` for no error , `>0` if there's errors.
err_msg | String | error message.
data | Array |
offer_id | String | offer id
offer_name | String | offer name
pricing_model | String | cpi,cpe,cpa
device |  String | phone,tablet
platform | String | android,ios
countries | String | 2-letter country code, more country codes concatenated with `,`
traffic | String | non-incent,incent
price | String | price
notes | String | kpi or terms
daily_click_cap | Integer | daily click cap
daily_cap | Integer | daily cap
cap_timezone | String | timezone
icon | String | app's icon url
app_name | String | app name
app_size | String | app size
app_rate | String | app rate
app_desc | String | app description
package_name | String | app package name
preview_link | String | app store preview link
creatives | Array | creatives
click_url | String | click url/tracking link
allow_s2s | Integer | whether can use server side click or not
pageinfo | Array |
total | Integer | total offers
pagecount | Integer | total page
pagesize | Integer | offers number per page
curpage | Integer | current page

**JSON** Result Sample:

```json
{
    "error": 0,
    "data": [
        {
            "offer_id": "1",
            "offer_name": "Test Offer",
            "pricing_model": "cpi",
            "device": "phone",
            "platform": "android",
            "countries": "AE,AF",
            "traffic": "non-incent",
            "price": "0.01",
            "notes": "test",
            "daily_click_cap": 99999,
            "daily_cap": 100,
            "cap_timezone": "UTC+0",
            "icon": "http:\/\/www.thecchange.net\/cchange.png",
            "app_name": "The Cchange",
            "app_size": "5",
            "app_rate": "",
            "app_desc": "this a app of the cchange",
            "package_name": "the.cchange.com",
            "preview_link": "http:\/\/www.thecchange.net",
            "creatives": [
                "http:\/\/www.thecchange.net\/cchange.png",
                "http:\/\/www.thecchange.net\/cchange2.png",
                "http:\/\/www.thecchange.net\/cchange3.png"
            ],
            "click_url": "http:\/\/app.cctrk.com\/click?oid=1&chnid=1",
            "allow_s2s": 0,
            "time": "1605834386"
        }
    ],
    "pageinfo": {
        "total": 1,
        "pagecount": 1,
        "pagesize": 20,
        "curpage": 1
    }
}
```
## 5. Errors

```
{
    error: 1,
    err_msg: "your account is not available"
}
```

_Note: In most case,If there are any errors, you'll get error number `1`._

## 6. Call Frequency

In order to sync the campaigns/offers in time , we strongly suggest you to make your system call the API every 10 to 15 minutes.

# Click Parameters / Click Url Parameters

CChange base Click Url contains the minimum information required to record the click and redirect the user to download the app.Additional parameters are added to the link after the `?` character to record extra information.

`http://[domain]/click?oid={offer_id}&chnid={network_id}`

The base Click Url includes the `{offer_id}` , which is the Offer ID/Campaign ID of CChange Platform. As well as the network id `{network_id}`. This is the minimum requirement for a Click Url.

## Click Parameters

The following parameters are available for use within the Click Url.

Parameters | Description | Type
-- | -- | -- 
clickid | Unique ID of click | String,max length 400
subid | Sub Publisher ID | String,max length 100
devid | GAID(Google Advertising ID) or IDFA(Apple Identifier) | String
pkgname | Your app's bundle ID/package name | String
c_param1 | extra parameter | String,max length 100
c_param2 | extra parameter | String,max length 100
c_param3 | extra parameter | String,max length 100
c_param4 | extra parameter | String,max length 100
c_param5 | extra parameter | String,max length 100

> Sample:

`http://[domain]/click?oid=1&chnid=1&clickid={YOUR_CLICKID}&subid={YOUR_SUBID}&devid={GAID_or_IDFA}&pkgname={PACKAGE_NAME}`

## Server Side Click Parameters

The following parameters are available for use when `allow_s2s` is equal to `1`.

Parameters | Description | Type
-- | -- | -- 
s2s | whether use server side click or not | Integer `0` or `1`
c_ip | Device/Client's IP address | String
c_ua | Device/Client's User Agent | String 
c_lang | Device/Client's language | String

> Sample:

`http://[domain]/click?oid=1&chnid=1&clickid={YOUR_CLICKID}&subid={YOUR_SUBID}&devid={GAID_or_IDFA}&pkgname={PACKAGE_NAME}&s2s=1&c_ip=127.0.0.1&c_ua=Mozilla%2F5.0%20(Linux%3B%20Android%207.1.1%3B%20CPH1717%3B%20Flow)%20AppleWebKit%2F537.36%20(KHTML%2C%20like%20Gecko)%20Chrome%2F347.0.0.268%20Mobile%20Safari%2F537.36&c_lang=en-US`

## HTTPS

By default,Our Click Url started with `http`,you can replace http with `https` if in needed.

> Sample:

①`http://[domain]/click?oid={offer_id}&chnid={network_id}`

②`https://[domain]/click?oid={offer_id}&chnid={network_id}`

Both ① and ② are valid. 

# Postback/Callback

As a partner , if you want to receive each conversion of offers,please reach out to our account manager to set your postback URL.

The following parameters are available for use within the Postback/Callback Url.

Macros | Description
-- | --
{clickid} | clickid
{subid} | subid
{devid} | devid
{cc_clickid} | CChange's unique Click Id
{payout} | payout
{c_param1} | c_param1
{c_param2} | c_param2
{c_param3} | c_param3
{c_param4} | c_param4
{c_param5} | c_param5

> Sample:

`http://[your_domain]?tid={clickid}`

The following parameters are available for use within the BLOCK Postback/Callback Url.

Macros | Description
-- | --
{blocked_reason} | Blocked Reason
{blocked_sub_reason} | Blocked Sub-Reason

> Sample:

`http://[your_domain]?tid={clickid}&is_reject=1&reject_reason={blocked_reason}&reject_sub_reason={blocked_sub_reason}`

_Note: For details of passing click parameters , refer to
[Click Parameters](click_parameters.md) ._

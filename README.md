Wechat-Sign
==========

Make it easier to get wechat access_token, jsapi_ticket and sign url

## Installation

  `npm install node-wechat-sign`

## Usage

~~~javascript
  import Wechat from 'node-wechat-sign'
  const wechat = new Wechat(config)
  const access_token = await wechat.getAccessToken()
  const jsapi_ticket = await wechat.getTicket()
  const signature = await wechat.sign(url)
~~~

## Configure

~~~javascript
  config = {
    appid,
    secret,
    [tokenApiTemplate,]
    [ticketApiTemplate,]
    [templateVariablePattern,]
    [cacheExpiresInSeconds,]
  }
~~~

#### appid[STRING]

  Your officer account's appid.

#### secret[STRING]

  Your officer account's secret.

#### tokenApiTemplate[STRING]

  Url template of wechat server for access_token.
  Default value:
  `'https://api.weixin.qq.com/cgi-bin/token?grant_type=client_credential&appid=#{appid}&secret=#{secret}'`

#### ticketApiTemplate[STRING]

  Url template of wechat server for jsapi_ticket.
  Default value:
  `'https://api.weixin.qq.com/cgi-bin/ticket/getticket?access_token=#{access_token}&type=jsapi'`

#### templateVariablePattern[REGEXP]

  Pattern to replace above templates with real data.
  Default value:
  `/#\{([^}]*)\}/mg`

#### cacheExpiresInSeconds[NUMBER]

  Seconds to expire the cached access_token and jsapi_ticket.
  Default value:
  `7200`


## Contribute

  Good features and suggestions are welcome. Code here: https://github.com/pplam/wechat-sign.

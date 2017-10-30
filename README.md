# apigateway4

**NOTE: This is a fork created for development purposes, please use the original package in [https://github.com/pahud/apigateway4]() instead.**

AWS API Gateway request signing library



[![npm](https://img.shields.io/npm/v/apigateway4.svg?maxAge=3600?style=flat-square)](https://www.npmjs.com/package/apigateway4) [![npm](https://img.shields.io/npm/dt/apigateway4.svg?maxAge=3600?style=flat-square)]()

[![NPM](https://nodei.co/npm/apigateway4.png)](https://nodei.co/npm/apigateway4/)



# About

apigateway4 is a simple SDK for AWS API Gateway request signing with the [Signature Version4 Signing Process](http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html). 



# Features

- support default API Gateway domain as well as the **[custom domain name](http://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-custom-domains.html)**
- support popular npm modules like [request](https://www.npmjs.com/package/request) and [request-promise](https://www.npmjs.com/package/request-promise)



## Usage

```
var agw4  = require('apigateway4')

var requestOpts = {
	uri: 'https://<apigateway_id>.execute-api.us-west-2.amazonaws.com/v1/auth?name=myname&foo=bar'
}

var signer = new agw4.BuildRequestSigner(requestOpts,credentials)

signer.sign()

// example for 'got'
require('got')(requestOpts.uri, requestOpts)
 .then( (html)=> console.log(html.body))
 .catch( (e) => console.log(e))


// example for 'request-promise'
require('request-promise')(requestOpts)
 .then( (html)=> console.log(html))
 .catch( (e) => console.log(e))
```

see ***[example.js](https://github.com/pahud/apigateway4/blob/master/example.js)*** for more details
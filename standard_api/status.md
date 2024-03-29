# 状态码规范

### 204 No Content

如果更新成功，且客户端属性保持最新，服务器必须返回204 No Content状态码。适用于PUT请求，以及仅调整links，不涉及其它属性的POST, DELETE请求

### 200 OK

如果服务器接受更新，但是在请求指定内容之外做了资源修改，必须响应200 OK以及更新的资源实例，像是向此URL发出GET请求.

### 201 Created

如果服务器需要创建一些资源, 比如创建用户, 创建用户数据, 创建资源, 默认API的create方法返回这个状态码.

### 301 Moved Permanently

被请求的资源已永久移动到新位置, 适用于资源link的变更,服务器做出兼容API.

### 303 See Other

对应当前请求的响应可以在另一个 URI 上被找到，客户端应该使用 GET 方法进行请求, 适用于旧API往新API的兼容.

### 400 Bad Request

请求体包含语法错误, 出现本错误服务端应该向客户端发送出错描述

适用于:
- 发送了无法转化的请求体

### 401 Unauthorized

需要验证用户身份，如果服务器就算是身份验证后也不允许客户访问资源，应该响应 403 Forbidden, 适用于未登录检查

### 403 Forbidden

服务器拒绝执行

适用于:
- 服务到期（比如付费的增值服务等）
- 因为某些原因不允许访问（比如被 ban ）
- 权限不够，403 状态码

### 404 Not Found

找不到目标资源

适用于:
- 需要修改的资源不存在

### 405 Method Not Allowed

不允许执行目标方法，响应中应该带有 Allow 头，内容为对该资源有效的 HTTP 方法

### 406 Not Acceptable

服务器不支持客户端请求的内容格式（比如客户端请求 JSON 格式的数据，但服务器只能提供 XML 格式的数据）

### 409 Conflict

请求操作和资源的当前状态存在冲突

### 410 Gone

被请求的资源已被删除

### 412 Precondition Failed

服务器在验证在请求的头字段中给出先决条件时，没能满足其中的一个或多个。主要使用场景在于实现并发控制

### 413 Request Entity Too Large

POST 或者 PUT 请求的消息实体过大

### 415 Unsupported Media Type

服务器不支持请求中提交的数据的格式

### 422 Unprocessable Entity

请求格式正确，但是由于含有语义错误，无法响应


适用于:
- 发送了非法的资源

### 428 Precondition Required

要求先决条件，如果想要请求能成功必须满足一些预设的条件
适用于:
- 缺少了必要的头信息


### 500 Internal Server Error

服务器遇到了一个未曾预料的状况，导致了它无法完成对请求的处理。

### 501 Not Implemented

服务器不支持当前请求所需要的某个功能。
501 与 405 的区别是：405 是表示服务端不允许客户端这么做，501 是表示客户端或许可以这么做，但服务端还没有实现这个功能

### 502 Bad Gateway

作为网关或者代理工作的服务器尝试执行请求时，从上游服务器接收到无效的响应。

### 503 Service Unavailable

由于临时的服务器维护或者过载，服务器当前无法处理请求。这个状况是临时的，并且将在一段时间以后恢复。如果能够预计延迟时间，那么响应中可以包含一个 Retry-After 头用以标明这个延迟时间（内容可以为数字，单位为秒；或者是一个 HTTP 协议指定的时间格式）。如果没有给出这个 Retry-After 信息，那么客户端应当以处理 500 响应的方式处理它。

###扩展状态码
###	4010 token
token过期或不存在

 
###	4011 member status
会员过期

###4012  Sending times beyond the count
验证码当天的发送次数超过限制次数

###4013 verification_code error
验证码错误

###4014 Request data have been bound
请求数据已绑定

###4015 Request data repetition
数据验证重复

###4016
请求的数据已被注册过 禁止再次注册  The requested data has been registered

###4017 Cache failure
缓存过期失效

###4019 Prohibition of frequent logon
判定登录状态 如果登录次数m次未登录成功 n分钟内禁止登录





适用于: 服务器维护中

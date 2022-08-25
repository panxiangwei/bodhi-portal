# API

#### 是否用户登录
- `url` /api/isLoggedIn
- `type` http post
- `params` access_token - {string} 用户的访问令牌，包含在 cookie.access_token 字段中。
- `return` {Object}

```javascript
{
    success: true,          // 接口请求是否成功。
    isLoggedIn: true,       // 用户是否已登录，仅当接口调用成功时才有值。
    message: '错误消息',     // 接口调用失败时的错误消息。
    userInfo: {             // 用户相关信息。也即用户从门户系统登录后，保存在在 session.user 
                            // 对象中的信息。该信息可能来自用户表，也可能是自定义登录实现时注入的字段。
        id: 'UserId',
        name: '用户名',
        ...
        其他自主定义的业务字段
    }
}
```

#### 注销用户登录
- `url` /api/logout
- `type` http post
- `params` access_token - {string} 用户的访问令牌，包含在 cookie.access_token 字段中。
- `return` {Object} 

```javascript
{
    success: true       // 注销成功或失败。
}
```
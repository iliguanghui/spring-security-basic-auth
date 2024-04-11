## 快速入门：演示Spring Security基础认证

BasicAuthenticationFilter默认使用的是RequestAttributeSecurityContextRepository，认证结果保存在ServletRequest里，每次请求需要携带Authorization首部进行认证。代码里改为HttpSessionSecurityContextRepository，以支持会话认证。

1. 不带用户名密码访问GET /，返回401，提示需要认证
2. 带用户名密码访问GET /，认证成功，返回结果及Cookie，认证结果被保存在HttpSession里，
3. 不带用户名密码访问GET /，由于请求中携带了Cookie，认证成功
4. 删除本地Cookie，不带用户名密码访问GET /，返回401，提示需要认证
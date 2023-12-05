
不光要认证，还要能有过期时间

就是说 认证成功时--后台是知道的---记住这个人上次认证的时间 

如果时间还没到，则 无碍访问
不必是每个请求都 去校验吧？ 那还是放数据库吧， redis当然也可以

（就是说你的每个请求得有一个30天内的token)
或者说不拿token--而是你30天内的approve记录我是有的

已经有答案了：


### 时序图如下：
前端先调接口验证 cookie中存的jwt token是否还有效
	如果有效，则直接进去 - 同时拿到了jwt token中的这个用户的身份信息 来请求接口
	（不要用cookie中的其他值，防止手动修改）
	  （你有谁的token ,就给你谁的信息）
	如果无效，则进入2FA验证页面 需要登录，同时看勾不勾选 remeber 30天， 输入账户和密码后
如果pass了，则进入下一页面/ 或者根据上一步使用的是phone/email来决定是发验证到哪里。 前端则让输PIN码，如果verify ok则后端直接返回 approved + 对应有效期的jwt token. 前端直接拿这个去请求接口 （也就是说 后端的接口除了这几个 其他的都需要校验token ??)


这个就解决啦


**What was worked on since the last update?**
	-Meeting information synchronization and participant tracking -100%
	-Display of scheduled tab -100%
	-Task arrange email -100%
	- Transcript - cadence -100%
	- Meeting charge duration statistics (timer) -100%
	- Control during the meeting -95%
	- Screen sharing - 95%
**What is planned for the next?**
	- start testing
**Are there any blockers than need unblocking to make progress?**
	-None at the moment
**What % of the project is complete before testing can begin?**
	Let's first test the overall process ourselves, and then deploy it to the testing environment to start testing on Friday


---
本周进度：
- 会议信息同步和人员跟踪- 100%
- scheduled tab的展示- 100%
- task arrange email - 100%
- translation转写- cadence - 100%
- 会议收费时长统计 - 100%
- 会中控制 - 95%
- 屏幕共享 - 95%

后续计划：
- 开始测试

是否遇到问题：
 - 暂时没有

整体进度：
  让我们先自行测试一下整体流程，周五再部署到测试环境开始测试
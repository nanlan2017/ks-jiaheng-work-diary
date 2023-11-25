### 怎么追踪？



---
### 会中控制
##### call expert, kick out somebody

应该有rest api 来 邀请别人？ 


邀请人， 然后根据email来对应吧


---

先 参会， 
把 时间加上来


几次arrange都报：task cannot be arranged before compliance approved

密码能不能我自己定啊


我需要一个 不再邀请中的号码 ！！（把 电信的邀请去掉）

#### zoom的event机制是啥啊，怎么感觉会重复发event ??

文档的说明是：没


<span style="background:#fdbfff">schdule都有了--- 成员---进出时间，几次call</span>
<span style="background:#fdbfff">那么就是计算好了</span>

brief_insight ---- 重新设计， 和页面对应
和 time travel 即可
##### 以及 如果能拿到join_url 或者房间号--密码的话？？？ 
那么 未登录人的 入会的识别、另用email zoom账户的识别是个问题

如果不能拿到join_url或password的话， 
那么 invite_link 我要知道回调啊

##### 完全可以把time travel放到 meeting里存起来，不用每次都travel --结果已定


（我成为负责了，我就会 保证那些需求先回）

---
insight需要insight哪些东西？

actual_start_time, actual_end_time, 
meeting status
然后就是participant列表
（每个participant要知道 


包括 instance_insight
和 event vo
conference insight

----

scheduled tab实际展示的  最新的instance里的参会情况
而 每个participant 其实都是有多个call
展示的是 lastest call的结果

actual start time 就是conference start
但timer start则要考虑角色 和中断了

（所以这个页面就差个timer啊）
timer是跨instances, 和calls的 
以及 把event stream展示一下 （不要wrap, 而是 直接new新对象返回）

timer要看到每一个event--以及会议开始时间， 来

#interrupt
twilio有个报 外呼打不出去


### 最差方法--- 用portal页面来中转 ， 就为了 role tracking 
原因： invite link来入会的，竟然不知道 是哪个link过来的，狗日的zoom api
另一方法： registrition ?? 

---
## 不对啊， scheduled tab必须显示 一个instance里的

Sir/Madam的问题 -- 即使我有app,用的是免登记的， 进会后竟然还是就是 指定的username - 卧槽，这不好吧


slack 消息提醒 / consent

外呼电话参会？？？

更新会议：开启录音

---
测一下， 网易邮箱 没受邀，
但他拿到了别的受邀人的 个人链接， 
加入会怎么样？ 直接加入显示？？



---

<span style="background:#d3f8b6">税怎么算， 减免退税怎么回事--很简单</span>
<span style="background:#d3f8b6">退税免除额</span>


做一个 发验证码的服务
以及 验证验证码的服务 


calendar邮件用的loopup
要求 subject 里带project code
要求 calendar里有where显示一键拨入信息

总之这个客户的邮件模板是定制的。

包括： 发给client contact的邮件。 
   当使用twilio时，还会多一种角色client compliance. 那么也是要看到定制的邮件


如果是加定制模板， 
那么就是 content_type = CALENDAR_TO_CONTACT
要加每种bridge的模板 （只有subject不一样）
以及legal to be approved 模板
其实content也会不一样

{这样很蛋疼。 }

还要加一个 content_type = CALENDAR_TO_CLIENT_COMPLIANCE


loopup部分的信息是不一样的啊
其实现在已经能做到 
	client的 - reference id
	某种role的  =  从content_type可以判断
	某种bridge的-- tag

只是模板实在有点多


和麦肯锡的不一样，因为mck的arrange模板里没有会议信息


代码的方式呢，就是手动改，只要是这个客户，  x  -- 还是加模板吧， 也就5个模板

---

### loopup参数要加






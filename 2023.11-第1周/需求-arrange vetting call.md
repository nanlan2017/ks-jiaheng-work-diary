notion: 
https://www.notion.so/capvision/DB-Workflow-Investment-Bank-Client-Type-9485c68aa73a431b8b6b959b05a563dc

---
讨论：
开个思路不容易, 有思路了就一口气干完



---


一部分没看懂，不过可以直接做吧
就是允许安排一个会议嘛，就这么简单，顺便把邮件发出去


---

两个客户的类型<font color="#ff0000"> 改为 投资银行</font>
<font color="#ff0000">投资银行有两种项目： 自己做的， 间接为客户做的</font>


目前是为jefferies硬编码了---chris以为我们的逻辑是写死了client id，
现在要改为：client type=Investment Bank, project type 为

两种类型项目的共同点：
- invoice.
	complete task时选的consultation type应该出现在invoice里
- compliance
	- 好几种可以check
	- <font color="#ff0000">对于两种类型的项目，如果compliance选择了external, 那么 to compliance 的邮件需要：</font>
<font color="#ff0000">		- 带PDF</font>


Consultation项目:
	基本上和现有的流程一致
	唯一的要注意的是compliance部分--- 根据项目设置的compliance规

Investor Call项目：
	- portal: 如何客户选择了专家，slack & 邮件要通知：需要安排vetting call
	- vetting call:
		- 15分钟的vetting call - 类似与screening
			- 目前vetting call不需要compliance批准
			- calendar邮件要修改
				-发给客户的：  vetting call安排了
				- 发给专家的： 一样的
    - compliance: 
	    - vetting call之后， 根据项目选择，一样的 （vetting call就是screening)
	    - 注意，真正的consultation电话是之后由 investment bank方 去安排的。

		```
	对于investment bank的investor call类型的项目，应当有两个arrange操作
	一个是用于安排vetting call的: 无需法务， 用vetting call邮件
	
	
	```


    - complete
    没什么好说的

---


那很简单啊，
arrange vetting call就跟发screening 搞成一样就行了

那么，访谈类型不用说， 就是改下 compliance的check项目和对应邮件就行了

对于investor call， 其实也没啥改动， 就是要多个 arrange vetting call, 而无非就是搞个会议信息发过去。 后续vetting call通过了和正常的继续arrange没什么两样。

---

怎么编码：

arrange vetting call api (投资银行客户+investor call类型的项目)
会议信息不变， ArrangeVettingCallRequest
渲染的邮件使用给的模板
照存照发，跟sq一样搞个状态就行

加在哪里？ task_arrangement 还是新建一个 task vetting call arrangement表 ? (不，还是task arrangement里- 那么一个task就可能有两个有效的arrangement了--类型分别是vetting call和 Common)
那么有个唯一索引： task_id, type, delete_at


##### 现在邮件模板是每种情况都得建立一个模板

现在存在task_investor_call表， 但仅限于toggle status会修改状态时存一条记录

那么既然是sq, 放这里也无可厚非啊？？ arrangement 还是task_investor_call
卧槽， 要都兼容啊，两边都有前端逻辑。

---

回到简单： 应该是什么样？
还是task , 它有extra信息， 
由于是只有部分task有， 可以放在 
放arrangement确实不太好？？ 所以放task_investor_call ??
这个信息包括： 状态信息， 会议安排的信息， 那还是 都放吧！都兼容， 
状态放在investor call, 会议信息放在arrangement . 

---

#refactor

邮件渲染时 光basemodel是不够的，比如loopup信息或一些在页面预览还没进数据库的参数， 那就需要放到context_params,
这个 应该搞成强类型的！


---

calendar怎么发
现在的calendar竟然和schedule是强关联的？？

这个vetting call我打算不进 schedule表和task.start time,end time
那么portal的twilio拨入页面也要适配， 因为这不是consultation拨入， 而是vetting call的拨入

先把calendar发出去，无非是构造一个calendar对象，(时间+location而已)


twilio的会议 的portal显示要调整

（one-click-dial-in其实用不着 存表里）--- loopup才有这个
guest code,
room url
area acess phone number - 都可以直接取到

---



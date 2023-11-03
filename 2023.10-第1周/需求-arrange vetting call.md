notion: 
https://www.notion.so/capvision/DB-Workflow-Investment-Bank-Client-Type-9485c68aa73a431b8b6b959b05a563dc

---
讨论：
开个思路不容易, 有思路了就一口气干完



---


一部分没看懂，不过可以直接做吧
就是允许安排一个会议嘛，就这么简单，顺便把邮件发出去


---

两个客户的类型 改为 投资银行
投资银行有两种项目： 自己做的， 间接为客户做的


目前是为jefferies硬编码了---chris以为我们的逻辑是写死了client id，
现在要改为：client type=Investment Bank, project type 为

两种类型项目的共同点：
- invoice.
	complete task时选的consultation type应该出现在invoice里
- compliance
	- 好几种可以check
	- 对于两种类型的项目，如果compliance选择了external, 那么 to compliance 的邮件需要：
		- 带PDF


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

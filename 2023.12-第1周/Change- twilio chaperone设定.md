
思路： 

beep,   
以及 welcoming的计算
	welcoming的计算的ordinal应该只考虑非chaperone的人员
	不对，如果是chaperone的话，他能听到所有；其他人只能听到非chaperone的。
	你是


### 另外
可能还需要一个单独的 copy chaperone的功能（如果一开始arrange没有添加 client compliance角色？？）

不麻烦，直接加个 conference invitee就好？？（participant不用管，会自动对应上的）--不对，还是要管

（目前不支持 arrange之后 再单独添加 受邀参会者）

#### 测试

#### 1
chaperone先连上，此时expert进入， 会议不应当开始！
直到有另一个非chaperone角色进入

<font color="#ff0000">#### 2</font>
welcoming message的测试

#### 3
beep的测试
Ω
##### 测试方式
本地ngrok, 然后arrange一个带client compliance角色的会议。
expert和advisor分别用手机浏览器和电脑浏览器连接，
然后chaperone角色用zoom电话外拨


 http://gitlab.capvision.us:32080/server/rm-server.git
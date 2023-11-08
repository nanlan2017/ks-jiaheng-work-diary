
![[inquiry-tables.png]]

inquiry代表一份问卷
inquiry_branch代表该问卷的各个版本
inquiry_question与branch是N~1的关系，代表该版本上的具体的问题列表
inquiry_instance与branch也是N~1关系， 代表一次问卷发放，比如某个task发sq, 就对应一条inquiry_instance
inquiry_answer表现在应该是不用了， 现在会把问卷的问题和回答以快照形式 存放在inquiry_instance的对应字段里

![[fmq-sq-decipher.png]]
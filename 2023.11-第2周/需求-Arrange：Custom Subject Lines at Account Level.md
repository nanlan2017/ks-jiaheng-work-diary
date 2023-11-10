
https://www.notion.so/capvision/Arrange-Custom-Subject-Lines-at-Account-Level-c8b5022e429342c5982312a777eecec0

```text
我知道我们已经在美国数据库中具备创建自定义模板的能力，但这很难管理，而且缺少一些要素：

1. 无法将模板应用于帐户并使其成为仅对该帐户有效的默认值，而不影响其他帐户。
2. 无法通过用户界面将邀请模板应用于参与者类型、桥接类型或两者的组合，而不影响其他桥接类型或参与者类型。
3. 无法轻松导航模板，以查看其内容和位置，鉴于命名约定。我在下面的解决方案中提出了“昵称”的概念。
```

1. 其实目前可以解决，只是UI上没显示：后台支持用reference type+id 来绑定具体客户
2. 要能指定bridge&role去关联
3. 要能快速找到，并加个易记的名称


说到底email template的模板功能本身够了，是 association的问题， 即把模板与 客户/bridge/role关联
chris提了一个在account页面添加自定义 subject template的功能：
这样关联都没问题了
而输入的内容只有一个subject, 支持3个变量
这个东西能够 override 默认的模板
可以做的处理是：arrange时，先查这里的subject template, 如果存在自定义的subject template，则用这个否则用默认的。

**问题： 这地方只是自定义subject吗，content会否需要自定义？

bridge的枚举： BridgeType,
role的枚举： ConferenceParticipantRole

**要考虑：

'Pending compliance aporoval - ' 这种conditional的前缀仍要保留
对应placeholder：  PENDING_COMPLIANCE_APPROVAL_PREFIX_IN_SUBJECT

简单的做法：这次新增的subject template也要求加上述placeholder ，
否则只能在 模板占位符之外， 硬编码去决定是否添加这个前缀


其他想法：
arrange时前端同时取到两个template ? subject和content分别用两个template渲染？



